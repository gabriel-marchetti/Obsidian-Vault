To declare variables we use the $ and the name of the variable

```powershell
$myVariable = "Your Name."
```

We can declare some null variables by just initializing them. To get an error by initializing a variable without a type you can use at the start of the script:

```powershell
Set-StrictMode -Version lastest
```

OBS: To use the equal operation we use -eq instead of  