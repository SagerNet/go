# SagerNet forked Go

## Revert Golang1.25 commit for macOS 10.13 (High Sierra)
this patch only works on golang1.25.x

that means after golang1.26 release it must be changed

see: https://github.com/SagerNet/go/commits/release-branch.go1.25/

revert:
* 33d3f603c1: "cmd/link/internal/ld: use 12.0.0 OS/SDK versions for macOS linking"
* 937368f84e: "crypto/x509: change how we retrieve chains on darwin"

```shell
cd $(go env GOROOT)
curl https://github.com/SagerNet/go/commit/afe69d3cec1c6dcf0f1797b20546795730850070.diff | patch --verbose -p 1
curl https://github.com/SagerNet/go/commit/1ed289b0cf87dc5aae9c6fe1aa5f200a83412938.diff | patch --verbose -p 1
```
