PowerShell  automated configuration tools

```powershell
Get-Process

Get-Service

Start-Service

Stop-Service
```

### Variables

`$name = "Irfan"`

$name  used to declare variable 

### Print statement 

`Write-Output $name`

### Pipelines

<mark style="background: #ABF7F7A6;">Passes the output of one cmdlet as input to another cmdlet using |.</mark>

### List processes and select only Name + Id

`Get-Process | Select-Object Name, Id`

Select-Object is a cmdlet used to choose specific properties from objects

PowerShell commands don’t just output text — they output objects with multiple properties.
Select-Object lets you control which properties you want to display or pass along.

1️⃣ Get-Process
Retrieves all currently running processes.
Each process is an object containing many properties such as:
1. Name
2. Id
3. CPU
4. WorkingSet
5. StartTime
6. and many more

`Get-Process | Select-Object -First 5`

`Get-Process | Select-Object -Last 3`

`Get-Process | Select-Object -Skip 10`

`Get-Process | Sort-Object CPU -Descending`  --> Shows highest CPU users first.


```powershell
get-process | sort-object cpu-descending |Select-Object Name, Id | Select-Object -First 5
```


```powershell
Get-Service | Where-Object {$_.Status -eq "Running"} | Measure-Object
```

1. **`Get-Service`**  
    1. Retrieves all services on the system.
    
2. **`Where-Object {$_.Status -eq "Running"}`**  
    1. Filters the list to only services whose **Status** is `"Running"`.
    
3. **`Measure-Object`**  
    1. Counts the filtered results.

 =="not equal" is== **`-ne`**
 =="equals" is== **`-eq`**


- `Get-Service` → works with **Windows Services**
- `Get-Process` → works with **running processes (programs/apps)**

