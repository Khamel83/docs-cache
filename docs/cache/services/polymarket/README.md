# Polymarket Documentation

## Introduction

Welcome to Polymarket's docs! Here developers can find all the information they need for interacting with Polymarket. This includes documentation on market discovery, resolution, trading etc. Whether you are an academic researcher, a market maker, or an indie developer, this documentation should provide you what you need to get started. All the code you find linked here and on the GitHub is open source and free to use.

**Discord:** Join the `#devs` channel for questions

## Key Endpoints

| Service | URL |
|---------|-----|
| CLOB REST API | `https://clob.polymarket.com/` |
| CLOB WebSocket | `wss://ws-subscriptions-clob.polymarket.com/ws/` |
| Gamma API | `https://gamma-api.polymarket.com` |
| CLOB Status | `https://status-clob.polymarket.com/` |

## CLOB API (Central Limit Order Book)

### Overview

Polymarket's Order Book, also referred to as the "CLOB" or "BLOB" (Binary Limit Order Book), is hybrid-decentralized wherein there is an operator that provides off-chain matching/ordering services while settlement/execution happens on-chain, non-custodially.

### Client Libraries

**Installation:**
```bash
# TypeScript
npm i -s @polymarket/clob-client

# Python
pip install py-clob-client
```

**Initialization (Python):**
```python
from py_clob_client.client import ClobClient

host = "https://clob.polymarket.com"
key = "your_private_key"
chain_id = 137  # Polygon

# EOA (direct wallet)
client = ClobClient(host, key=key, chain_id=chain_id)

# Polymarket Proxy (Email/Magic)
client = ClobClient(host, key=key, chain_id=chain_id,
                    signature_type=1, funder=POLYMARKET_PROXY_ADDRESS)

# Browser Wallet (Metamask, Coinbase)
client = ClobClient(host, key=key, chain_id=chain_id,
                    signature_type=2, funder=POLYMARKET_PROXY_ADDRESS)
```

**Initialization (TypeScript):**
```typescript
import { ClobClient } from "@polymarket/clob-client";
import { SignatureType } from "@polymarket/order-utils";

// EOA
const clobClient = new ClobClient(host, chainId, wallet);

// Polymarket Proxy
const clobClient = new ClobClient(host, chainId, wallet, undefined,
                                  SignatureType.POLY_PROXY, proxyAddress);
```

### Order Types

| Type | Description |
|------|-------------|
| `GTC` | Good-Til-Cancelled - limit order active until filled or cancelled |
| `GTD` | Good-Til-Day - active until specified date (1min security threshold) |
| `FOK` | Fill-Or-Kill - market order must execute immediately in full or be cancelled |

### Place Order Examples

**GTC Order (Python):**
```python
from py_clob_client.clob_types import OrderArgs, OrderType
from py_clob_client.order_builder.constants import BUY

order_args = OrderArgs(
    price=0.50,
    size=100.0,
    side=BUY,
    token_id="71321045679252212594626385532706912750332728571942532289631379312455583992563",
)
signed_order = client.create_order(order_args)
resp = client.post_order(signed_order, OrderType.GTC)
```

**Market Order FOK (Python):**
```python
from py_clob_client.clob_types import MarketOrderArgs, OrderType

# Buy $100 worth
order_args = MarketOrderArgs(
    token_id="...",
    amount=100.0,  # dollars
    side=BUY,
)
signed_order = client.create_market_order(order_args)
resp = client.post_order(signed_order, OrderType.FOK)
```

### Key API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/auth/api-key` | Create API key |
| `GET` | `/auth/api-keys` | Get all API keys |
| `DELETE` | `/auth/api-key` | Delete API key |
| `GET` | `/auth/ban-status/cert-required` | Check certification status |
| `GET` | `/auth/ban-status/closed-only` | Check closed-only mode |
| `POST` | `/order` | Place order |
| `GET` | `/data/order/{id}` | Get single order |
| `DELETE` | `/order` | Cancel order |
| `DELETE` | `/orders` | Cancel multiple orders |
| `DELETE` | `/cancel-all` | Cancel all orders |
| `GET` | `/data/trades` | Get trades |
| `GET` | `/markets` | Get markets (paginated) |
| `GET` | `/book` | Get order book |
| `GET` | `/price` | Get best bid/ask price |
| `GET` | `/midpoint` | Get midpoint price |

## WebSocket API

### Connection

```
wss://ws-subscriptions-clob.polymarket.com/ws/
```

### Channels

**User Channel** - Authenticated, user-specific updates:
- `trade` - Trade executions and status updates
- `order` - Order placement, updates, cancellations

**Market Channel** - Public market data:
- `book` - Order book snapshots
- `price_change` - Price level changes
- `tick_size_change` - Minimum tick size changes

### Subscription Format

```json
{
  "auth": {
    "apiKey": "...",
    "secret": "...",
    "passphrase": "..."
  },
  "markets": ["condition_id_1", "condition_id_2"],
  "asset_ids": ["token_id_1", "token_id_2"],
  "type": "User" | "Market"
}
```

## Gamma Markets API

### Overview

Gamma is a hosted service that indexes on-chain market data and provides additional market metadata (categorization, indexed volume, etc). Available as a read-only REST API.

**Endpoint:** `https://gamma-api.polymarket.com`

### Market Organization

- **Market** - Individual traded market with CLOB token IDs, question ID, condition ID
- **Event** - Collection of related markets (SMP = single market, GMP = multiple markets)

Example event: "Where will Barron Trump attend College?"
- Markets: Will he attend Georgetown? NYU? UPenn? Harvard? Other?

### Key Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/markets` | Get markets (filter by active, closed, archived, tag_id, etc.) |
| `GET` | `/markets/{id}` | Get single market |
| `GET` | `/events` | Get events |
| `GET` | `/events/{id}` | Get single event |

### Query Parameters (Markets)

| Parameter | Type | Description |
|-----------|------|-------------|
| `limit` | number | Limit results |
| `offset` | number | Pagination offset |
| `active` | boolean | Filter by active status |
| `closed` | boolean | Filter by closed status |
| `archived` | boolean | Filter by archived status |
| `tag_id` | number | Filter by tag |
| `clob_token_ids` | string | Filter by token ID |
| `condition_ids` | string | Filter by condition ID |
| `liquidity_num_min/max` | decimal | Filter by liquidity range |
| `volume_num_min/max` | decimal | Filter by volume range |
| `end_date_min/max` | string | Filter by end date range |

## Exchange Contract

### Deployments

| Network | Address |
|---------|---------|
| Polygon | `0x4bFb41d5B3570DeFd03C39a9A4D8dE6Bd8B8982E` |
| Mumbai | `0x4bFb41d5B3570DeFd03C39a9A4D8dE6Bd8B8982E` |

### Fees

Current schedule (subject to change):

| Volume Level | Maker Fee | Taker Fee |
|--------------|-----------|-----------|
| >0 USDC | 0 bps | 0 bps |

Fees are levied in the output asset and use symmetric formulas to preserve market integrity.

## Resolution

### UMA Optimistic Oracle

Most markets resolve via UMA's Optimistic Oracle. Process:

1. **Initialize** - `initialize()` creates question and requests price from OO
2. **Propose** - Anyone proposes price with bond
3. **Dispute** - Disagreements escalate to DVM for voting

### UMA CTF Adapter Addresses

| Version | Polygon | Mumbai |
|---------|---------|--------|
| v3.0.0 | `0x71392E133063CC0D16F40E1F9B60227404Bc03f7` | `0x71392E133063CC0D16F40E1F9B60227404Bc03f7` |
| v2.0.0 | `0x6A9D222616C90FcA5754cd1333cFD9b7fb6a4F74` | `0x6A9D222616C90FcA5754cd1333cFD9b7fb6a4F74` |

## Conditional Tokens Framework (CTF)

### Overview

Polymarket uses Gnosis's CTF with ERC1155 tokens for binary outcomes (YES/NO).

### Token ID Calculation

1. Get `conditionId` from `getConditionId(oracle, questionId, outcomeSlotCount)`
2. Get `collectionIds` from `getCollectionId(parentCollectionId, conditionId, indexSet)`
3. Get `positionIds` (token IDs) from `getPositionId(collateralToken, collectionId)`

### Operations

- **Split** - Convert USDC to YES + NO tokens
- **Merge** - Convert YES + NO to USDC
- **Redeem** - Convert winning tokens to USDC after resolution

### CTF Contract

| Network | Address |
|---------|---------|
| Polygon | `0x4D97DCd97eC945f40cF65F87097ACe5EA0476045` |
| Mumbai | `0x7D8610E9567d2a6C9FBf66a5A13E9Ba8bb120d43` |

## Proxy Wallets

Polymarket uses proxy wallets for improved UX:

| Factory Type | Address |
|--------------|---------|
| Gnosis Safe (MetaMask) | `0xaacfeea03eb1561c4e67d661e40682bd20e3541b` |
| Polymarket Proxy (MagicLink) | `0xaB45c5A4B0c941a2F231C04C3f49182e1A254052` |

## Liquidity Rewards Program

Polymarket incentivizes liquidity providers with rewards based on:

- Spread from midpoint (tighter = better)
- Two-sided depth
- Order size relative to minimum
- In-game trading multiplier

Rewards distributed daily at midnight UTC.

## Subgraph

Public GraphQL endpoints hosted on Goldsky:

| Subgraph | URL |
|----------|-----|
| Orderbook | `https://api.goldsky.com/api/public/project_cl6mb8i9h0003e201j6li0diw/subgraphs/orderbook-subgraph/prod/gn` |
| Positions | `https://api.goldsky.com/api/public/project_cl6mb8i9h0003e201j6li0diw/subgraphs/positions-subgraph/0.0.7/gn` |
| Activity | `https://api.goldsky.com/api/public/project_cl6mb8i9h0003e201j6li0diw/subgraphs/activity-subgraph/0.0.4/gn` |
| Open Interest | `https://api.goldsky.com/api/public/project_cl6mb8i9h0003e201j6li0diw/subgraphs/oi-subgraph/0.0.6/gn` |
| PNL | `https://api.goldsky.com/api/public/project_cl6mb8i9h0003e201j6li0diw/subgraphs/pnl-subgraph/0.0.14/gn` |

## Bug Bounty

Active bug bounty program via [Immunefi](https://immunefi.com/). Public contracts and critical web apps are in scope.

## Resources

- **GitHub:** https://github.com/Polymarket
- **Audit:** Chainsecurity audit report available
- **UMA Docs:** https://docs.uma.xyz/
- **UMA Oracle Portal:** https://oracle.umaproject.org/

## Quick Reference

### Signature Types

| Type | ID | Description |
|------|-----|-------------|
| EOA | 0 | EIP712 signature from EOA |
| POLY_PROXY | 1 | EIP712 from Polymarket Proxy (Email/Magic) |
| POLY_GNOSIS_SAFE | 2 | EIP712 from Polymarket Gnosis Safe (Browser Wallet) |

### Order Object Structure

| Field | Type | Description |
|-------|------|-------------|
| salt | integer | Random salt for uniqueness |
| maker | string | Maker/funder address |
| signer | string | Signing address |
| taker | string | Taker address (operator) |
| tokenId | string | ERC1155 token ID |
| makerAmount | string | Max amount maker will spend |
| takerAmount | string | Min amount taker must pay |
| expiration | string | Unix expiration timestamp |
| nonce | string | Maker's Exchange nonce |
| feeRateBps | string | Fee rate in basis points |
| side | string | buy (1) or sell (0) |
| signatureType | integer | Signature type enum |
| signature | string | Hex encoded signature |

### Trade Statuses

| Status | Terminal? | Description |
|--------|-----------|-------------|
| MATCHED | No | Matched, sent to executor |
| MINED | No | Mined, no finality |
| CONFIRMED | Yes | Finality achieved, successful |
| RETRYING | No | Failed, being retried |
| FAILED | Yes | Failed, not retrying |
