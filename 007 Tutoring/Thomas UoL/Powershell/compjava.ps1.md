2023-01-24, 15:46
Type: #topic

*Look in current directory, and all directories contained within, for files with \*.java extension and run `javac` on them*  

---

### Code

```powershell
$files = Get-ChildItem ".\" -Recurse -Filter *.java

for ($i = 0; $i -lt $files.Count; $i++) {
    $currentFile = $files[$i].FullName

    Write-Output "Compiling file: " $currentFile

    javac $currentFile
}
```

---

### Explanation

- We need to get all the children files with the extension: `*.java` so we will run the command

```powershell
$files = Get-ChildItem ".\" -Recurse -Filter *.java
```

- We then need to loop through these files and compile them with the `javac` command.

```powershell
for ($i = 0; $i -lt $files.Count; $i++) {
    $currentFile = $files[$i].FullName

    Write-Output "Compiling file: " $currentFile

    javac $currentFile
}
```