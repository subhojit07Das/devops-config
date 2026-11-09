# Project notes

## Phase 0
- Problem: ssh -T git@github.com gave "Permission denied (publickey)"
- Cause: generated the key but had not uploaded the public key to GitHub
- Fix: added the .pub file under GitHub Settings > SSH keys
- Learned: GitHub only ever sees the public key

## Phase 1
- Problem: docker build failed with "Dockerfile: no such file"
- Cause: ran it from the parent folder, not the folder holding the Dockerfile
- Problem: docker exec with $(docker ps -q) failed
- Cause: minikube nodes are containers too, so ps returned several IDs
- Problem: no PR could be opened
- Cause: repo had no main branch, so there was no base to merge into
- Fix: pushed the first commit to create main, changed the default branch, then used PRs
- Learned: Dockerfile layer order affects build cache; the container runs as non-root (uid 1001)