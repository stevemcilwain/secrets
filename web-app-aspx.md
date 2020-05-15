# Web - App - ASPX

## LFI

```
Pentest for .NET apps? saw a param containing file path/name? 
Developers sometimes use "Path.Combine(path_1,path_2)" to build full path. 
Path.Combine has weird behavior: if param#2 is absolute path, then param#1 is ignored.
Leverage it to control the path.
```
