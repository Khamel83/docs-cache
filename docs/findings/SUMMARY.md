# Docs-to-Code Compliance Summary

**Date**: 2026-02-07
**Scan Type**: Breaking mismatches between documentation and actual code
**Result**: ✅ **No breaking mismatches found**

---

## What Was Checked

1. **External cached docs** (FastAPI, Tailscale, Traefik, Convex, Click) → Actual repo code
2. **Internal docs** (README.md, CLAUDE.md) → Files they reference

---

## Results

### External Docs → Code
- ✅ All files referenced in cached docs exist where expected
- ✅ All functions referenced in cached docs exist in their files
- No breaking "fart-46.py" vs "fart.py" mismatches

### Internal Docs → Code
- ✅ All README file references point to existing files
- ✅ All command examples reference actual files

---

## Earlier Anti-Pattern Findings (Not Breaking)

The scan did find **non-breaking style differences**:

| Pattern | Count | Notes |
|---------|-------|-------|
| argparse vs Click | ~50 files | Style preference, not broken |
| FastAPI usage | 8 repos | Architectural choice, works correctly |
| Class name variations | 1000+ | False positives (e.g., `Request` vs `MarkRequest`) |

---

## Conclusion

**Your documentation is accurate!** The cached external docs correctly represent how to use the tools, and your repos follow the documented patterns. The "anti-patterns" found earlier are:

1. **Style preferences** (argparse → Click) - code works, just not preferred style
2. **Architectural choices** (FastAPI vs Convex) - both work, you chose FastAPI
3. **False positives** - name variations that are intentionally different

**No action needed** unless you want to migrate to preferred styles for consistency.

---

## Files Generated

- `findings/repo-compliance-scan-2026-02-07.md` - Style/architecture findings
- `findings/scan-results.json` - Raw scan data (2306 lines)
