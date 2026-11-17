---
title: "Modules"
weight: 20
---

# Modules {#modules}

The modules of **go-mswin** listed here. Each links to its source and to
its generated API reference.

| Module | Reference |
| --- | --- |
| [`d3d11`](https://github.com/go-mswin/d3d11) | [pkg.go.dev](https://pkg.go.dev/github.com/go-mswin/d3d11) |
| [`screencapture`](https://github.com/go-mswin/screencapture) | [pkg.go.dev](https://pkg.go.dev/github.com/go-mswin/screencapture) |
| [`webauthn`](https://github.com/go-mswin/webauthn) | [pkg.go.dev](https://pkg.go.dev/github.com/go-mswin/webauthn) |
| [`win32`](https://github.com/go-mswin/win32) | [pkg.go.dev](https://pkg.go.dev/github.com/go-mswin/win32) |
| [`winrt`](https://github.com/go-mswin/winrt) | [pkg.go.dev](https://pkg.go.dev/github.com/go-mswin/winrt) |

`d3d11` (v0.2.0) is a pure-Go binding of the part of Direct3D 11 that a compute
kernel needs, with package `dxgi` alongside; COM is reached through syscall, with
no cgo. It has run only on WARP, the software rasterizer of a Windows CI runner,
and on no GPU.

`webauthn` (v0.5.0) asks Windows to authenticate somebody with a security key
through `webauthn.dll`, with no cgo. Since v0.5.0 it carries the `hmac-secret` and
`credProtect` extensions (`RegisterRequest.HMACSecret`, `RegisterRequest.CredProtect`,
`Request.HMACSalts`), which [theca](https://go-theca.github.io/docs/) v0.8.0 uses
for FIDO2 on Windows. hmac-secret needs WebAuthn API version 6; on an older
Windows the call fails with `ErrUnsupported`. Verified on Windows (API version 9):
the struct layouts and the read-back helpers. **Not verified: a call against a
real key.**

Descriptions live on the repositories themselves rather than being copied here, so
there is one place to correct when one changes.
