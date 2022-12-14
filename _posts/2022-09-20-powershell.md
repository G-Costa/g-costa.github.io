# PowerShell/CMD Commands

PowerShell/CMD commands for general Windows tasks.

## Computer Configuration

### Rename PC

```powershell
Rename-Computer -NewName "NewName" -DomainCredential fcpediatrics\User
```

### Change PC Description

```powershell
$value = @{Description = 'E-0000'}
```

```powershell
Set-CimInstance -Query 'Select * From Win32_OperatingSystem' -Property $value
```

### Change DNS

```powershell
netsh interface ipv4 show config
netsh interface ipv4 set dns name="Interface Name" static 10.10.1.201
netsh interface ipv4 add dns name="Interface Name" 8.8.8.8 index=2
```

## Domain Controller

### Create User

```powershell
net user /add Username key=Password123
```

### Change Password

```powershell
net user John Password
```

### Enable Account

```powershell
net user John /active:yes or Enable-ADAccount -Identity username
```

### Add User to Group

```powershell
net localgroup administrators John /add
```

## Misc

Disable Scheduled Task "TaskName"

```powershell
Disable-ScheduledTask -TaskName "TaskName"
```
