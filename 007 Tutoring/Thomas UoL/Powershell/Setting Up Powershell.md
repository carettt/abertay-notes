2023-01-20, 13:52
Type: #topic

Step-by-step guide to setting up Powershell for development purposes.

---

### Setting up Powershell to run as Administrator always

1. Search `Powershell` in windows search bar
2. Right-click -> Open File Location
3. Right-click file -> Properties
4. Shortcut Tab -> Advanced -> Check Run as Administrator
5. Apply -> Ok -> Close
6. Pin to Taskbar

---

### Setting up Execution Policy for running scripts

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

