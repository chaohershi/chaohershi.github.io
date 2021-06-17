---
permalink: /MarkdownPad-Crash-And-Error-Fix/
title: MarkdownPad Crash and Error Fix
---

## This view has crashed!

awesomium web-browser framework This view has crashed!

You only need `Awesomium.dll` from awesomium SDK 1.6.6.

Replace `C:\Program Files (x86)\MarkdownPad 2\Awesomium.dll` with `C:\Program Files (x86)\Khrona LLC\Awesomium SDK\1.6.6\build\bin\release\Awesomium.dll` and restart MarkdownPad.

Download the required `Awesomium.dll` [here](https://chaohershi.github.io/assets/Awesomium.dll.zip).

## Could not create SSL/TLS secure channel.

An error occurred while processing GitHub Flavored Markdown.
The request was aborted: Could not create SSL/TLS secure channel.

Use the following registry changes and restart MarkdownPad.

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v4.0.30319]
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]
"DisabledByDefault"=dword:00000000
"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]
"DisabledByDefault"=dword:00000000
"Enabled"=dword:00000001
```

---

Reference:
- [markdown - MarkdownPad Crashes on Windows 10 - Stack Overflow](https://stackoverflow.com/questions/31791082/markdownpad-crashes-on-windows-10)
- [MarkdownPad preview fails on Windows 10 - Super User](https://superuser.com/questions/954091/markdownpad-preview-fails-on-windows-10)
- [MarkdownPad - Frequently Asked Questions](http://markdownpad.com/faq.html#livepreview-directx)
- [GFM online mode SSL/TLS secure channel aborts - MarkdownPad / Help and Support - Apricity Software Forums](http://forums.apricitysoftware.com/t/gfm-online-mode-ssl-tls-secure-channel-aborts/1313)
- [asp.net - TLS 1.2 in .NET Framework 4.0 - Stack Overflow](https://stackoverflow.com/questions/33761919/tls-1-2-in-net-framework-4-0)
