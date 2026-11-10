# FreeRDP XDG AAD auth helper (vendored)

Copied from FreeRDP's `client/common/xdg-aad-helper/` (Apache-2.0).

Used when the system FreeRDP build ships `WITH_WEBVIEW_AAD_AUTH_HELPER` /
auto-detects an AAD helper: we point `/azure:auth-helper:` at
`freerdp-xdg-aad-helper` so connection-time Entra auth opens the **system
browser**. That is required for FIDO2/passkeys — WebKitGTK (our embedded
sign-in view) still has no WebAuthn support.

`freerdp-aad-handler` registers as `x-scheme-handler/ms-appx-web` so the
broker redirect returns to FreeRDP.
