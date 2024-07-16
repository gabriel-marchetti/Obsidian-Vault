To declare variables we use the $ and the name of the variable

```powershell
$myVariable = "Your Name."
```

We can declare some null variables by just initializing them. To get an error by initializing a variable without a type you can use at the start of the script:

```powershell
Set-StrictMode -Version lastest
```

For turning it off you can just get rid of this line or just use

```powershell
Set-StrictMode -Off
```


OBS: To use the equal operation we use -eq instead of  

You can define types for your variables by putting a [] into the beggining of the declaration.

```powershell
[int]$some-value=12
```

