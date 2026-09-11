# Super-Herdr APT repository

Debian and Ubuntu packages for
[Super-Herdr](https://github.com/mikro-design/super-herdr), for amd64 and arm64.

```sh
sudo install -d -m 0755 /usr/share/keyrings
curl -fsSL https://mikro-design.github.io/apt/super-herdr.gpg \
  | sudo tee /usr/share/keyrings/super-herdr.gpg > /dev/null
echo "deb [signed-by=/usr/share/keyrings/super-herdr.gpg] https://mikro-design.github.io/apt stable main" \
  | sudo tee /etc/apt/sources.list.d/super-herdr.list > /dev/null
sudo apt update
sudo apt install super-herdr
```

Everything here is generated. The index is rendered from the packages in the
pool and signed with a key held outside CI; the packages are the ones the
matching GitHub release published, checked against that release's own
`SHA256SUMS` before being indexed. Do not edit anything in this repository by
hand — see `packaging/README.md` in the source repository for how a release is
published, and `SECURITY.md` there for the trust model.

The last ten releases stay installable, so a specific version can be pinned:

```sh
sudo apt install super-herdr=0.7.23-1
```
