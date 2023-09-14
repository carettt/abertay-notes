2023-01-24, 16:14
Type: #topic

*Look into current directory and descendants for folders containing containing these two files and deletes each file*

---

### Code

```powershell
$files = Get-ChildItem ".\" -include ("hello.exe", "script.bat") -recurse

for ($i = 0; $i -lt $files.Count; $i++) {
    $currentFile = $files[$i].FullName
    
    Write-Output "Removing: " $currentFile

    Remove-Item $currentFile
}
```

---

### Explanation

- Get all `hello.exe` and `script.bat` files

```powershell
$files = Get-ChildItem ".\" -include ("hello.exe", "script.bat") -recurse
```

- Loop through the files and delete them with output:

```powershell
for ($i = 0; $i -lt $files.Count; $i++) {
    $currentFile = $files[$i].FullName
    
    Write-Output "Removing: " $currentFile

    Remove-Item $currentFile
}
```