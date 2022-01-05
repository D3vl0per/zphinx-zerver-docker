# Dockerized alpine based zphinx-zerver 
https://github.com/stef/zphinx-zerver

## Quick Start (not production ready)
1. Generate own private key: `openssl ecparam -genkey -out ssl_key.pem -name secp384r1`
2. Generate cert: `openssl req -new -nodes -x509 -sha256 -key ssl_key.pem -out ssl_cert.pem -days 365 -subj '/CN=localhost'`
3. docker-compose up -d

## Images
Docker registry: `d3vm/zphinx-zerver-docker:zphinx-<upstream-repo-git-commit>`   
GitHub registry: `ghcr.io/d3vl0per/zphinx-zerver-docker/zphinx:<upstream-repo-git-commit>`
Own registry: `r.zsibok.hu/zphinx-zerver-docker/zphinx:<upstream-repo-git-commit>`

## Builder images
  - Essetials-builder:
    - Docker registry: `d3vm/zphinx-zerver-docker:essetials-builder-<llvm-version>`
    - Github registry: `ghcr.io/d3vl0per/zphinx-zerver-docker/essetials-builder:<llvm-version>`
    - Own registry:    `r.zsibok.hu/zphinx-zerver-docker/essetials-builder:<llvm-version>`
  - Zig-builder:
    - Docker registry: `d3vm/zphinx-zerver-docker:zib-builder-<zig-version>`
    - Github registry: `ghcr.io/d3vl0per/zphinx-zerver-docker/zib-builder:<zig-version>`
    - Own registry:    `r.zsibok.hu/zphinx-zerver-docker/zib-builder:<zig-version>`

Current versions:
  - LLVM 11.0.0
  - ZIG 0.7.1

## Full rebuild process
1. Essetials-builder
2. Zig-builder
3. zphinx-builder
4. zphinx

