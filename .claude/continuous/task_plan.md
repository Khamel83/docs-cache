# Task Plan: GitHub Repo Library Documentation Catalog

## Objective
Catalog all libraries/dependencies across all accessible GitHub repos and generate documentation links.

## Done Criteria
- [ ] All accessible repos scanned for dependency files
- [ ] All unique libraries extracted with versions
- [ ] Documentation URLs found for each library
- [ ] Master list generated sorted by frequency/popularity

## Output Format
`library-catalog.md` with:
- Library name
- Documentation URL
- Repos using it
- Language/category

---

## Phases

### Phase 1: Repo Discovery & Cloning
- Get list of all accessible repos (public + private)
- Clone repos to temporary location for analysis
- Handle access permissions for private repos

### Phase 2: Dependency File Identification
Scan each repo for dependency files:
- JavaScript/TypeScript: `package.json`, `package-lock.json`, `yarn.lock`, `pnpm-lock.yaml`
- Python: `requirements.txt`, `pyproject.toml`, `poetry.lock`, `Pipfile`
- Go: `go.mod`, `go.sum`
- Rust: `Cargo.toml`, `Cargo.lock`
- Ruby: `Gemfile`, `Gemfile.lock`
- Java/Kotlin: `pom.xml`, `build.gradle`
- Other: `docker-compose.yml` (for service dependencies)

### Phase 3: Library Extraction
Parse dependency files and extract:
- Library name
- Version (if specified)
- Dependency type (prod, dev, peer, etc.)

### Phase 4: Documentation URL Resolution
For each unique library:
- Check existing docs-cache at `/home/ubuntu/github/docs-cache/docs/cache/.index.md`
- Search for official documentation URLs
- Categorize by language/ecosystem

### Phase 5: Catalog Generation
- Aggregate all findings
- Sort by frequency (repos using it)
- Categorize by language
- Generate final markdown file

---

## Decisions

### Storage Location
- Working directory: `/tmp/repo-scan/`
- Catalog output: `/home/ubuntu/github/docs-cache/library-catalog.md`

### Tools
- `gh` CLI for repo access
- `jq` for JSON parsing
- Standard grep/awk for extraction

### Scope
- Include all public repos
- Include private repos where `gh` has access
- Skip archived/inactive repos (user can review)

---

## Dependencies
- `gh` CLI installed and authenticated
- Network access for documentation lookups
- Write access to docs-cache repo

---

## Open Questions
- Should we include transitive dependencies? (Probably no - too much noise)
- Should we suggest caching missing docs to docs-cache? (Yes, as follow-up)
