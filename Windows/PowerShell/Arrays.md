We can use Array and ArrayLists for using this kind of data structure, which basically stores data in a kind of a linear way.

```powershell
$my_array = @()
```

Here we have the problem of doubling fixed sizes of arrays.

For initializing some ArrayList, the most concise way of doing it is by the command

```powershell
$array_list = New-Object -TypeName System.Collection.ArrayList
```

And now we can make some operations such as add and remove without much concern of the size of the object. Each time you add a value into your arrayList you get the index at the terminal. To avoid this you can make:

```powershell
[void]$array_list.add("Test")
```

There is the function (or method) AddRange that will add a list to your already existing list.

```powershell
$array_list.AddRange(@("Test3", "Test4", "Test5"))
```

Some other interesting method's for arraysLists
```powershell
$array_list.Remove("Test2") # This removes only the first instance
```

