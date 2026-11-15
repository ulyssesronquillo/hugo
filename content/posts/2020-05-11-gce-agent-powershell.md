---
title: 'gce agent powershell'
author: ulysses

date: 2020-05-11
slug: gce-agent-powershell
draft: false
---

This is a Powershell script to restart a service if it’s down.

```
$ServiceName = 'GCEAgent'
$arrService = Get-Service -Name $ServiceName

if ($arrService.Status -ne 'Running')
{

    Start-Service $ServiceName
    write-host $arrService.status
    write-host 'Service starting'
    Start-Sleep -seconds 60
    $arrService.Refresh()
    if ($arrService.Status -eq 'Running')
    {
        Write-Host 'GCE Agent Service is now Running'
    }

}
else
{
    Write-Host 'GCE Agent Service is Running'
}
```