# Secret Scan Before Handoff

- [ ] Scan the exact upload set, not only the working tree.
- [ ] Check credentials, API keys, tokens, private keys, certificates, cookies, and `.env` files.
- [ ] Exclude `.git`, caches, build output, dependency directories, and unrelated archives.
- [ ] Do not print detected secret values.
- [ ] Remove or replace the file before packaging.
- [ ] Re-run the scan after exclusions and record the command and result.
- [ ] Block the handoff if findings remain unexplained.
