# Synthetic Evidence Samples

> **Fictional portfolio evidence.** The following log excerpts were created for the incident-response simulation and are not taken from any real Rockstar Games environment.

## svc_devops Lateral Movement

```text
03:02  svc_devops -> DEV-SRV-10     SUCCESS
03:05  svc_devops -> DEV-SRV-11     SUCCESS
03:11  svc_devops -> DEV-SRV-12     SUCCESS
03:29  svc_devops -> DEV-SRV-13     SUCCESS
03:34  svc_devops -> FIN-SRV-02     DENIED
03:36  svc_devops -> DC-01          DENIED
03:37  svc_devops -> BUILD-SRV-04   DENIED
03:41  svc_devops -> DEV-SRV-14     SUCCESS
```

## Rodriguez Remote Compromise

```text
04:12:08  DEV-SRV-14 -> WS-MRODRIGUEZ-17  SMB  svc_devops  SUCCESS
04:12:19  ADMIN$ remote file write: C:\Windows\Temp\healthcheck.exe
04:12:27  Remote service created: SystemHealthMonitor
04:12:31  healthcheck.exe starts as NT AUTHORITY\SYSTEM
04:12:56  Credential-related memory access detected
04:13:26  Outbound/internal connection to DEV-SRV-14
```

## Chen Malicious Attachment

```text
08:54:12  Chen opens corporate email from compromised Rodriguez mailbox
08:54:26  Updated_Project_Schedule.zip saved to Downloads
08:55:31  ProjectSchedule.exe extracted
08:55:44  ProjectSchedule.exe launched manually by CORP\jchen
08:56:04  Credential/session-related access
08:56:21  Internal network discovery
08:57:02  Encrypted command-and-control connection
```

## BUILD-SRV-04 Staging and Exfiltration

```text
09:07:41  CORP\jchen -> BUILD-SRV-04  SUCCESS
09:10:22  Directory enumeration of project resources
09:19+    Selected data staged under C:\ProgramData\BuildCache
09:42:13  7za.exe creates cache.7z (~14.8 GB)
10:04-10:51  BUILD-SRV-04 -> attacker-controlled HTTPS endpoint
             ~14.8 GB outbound transfer
10:53+    Archive and staging artifacts deleted
```

## Analyst Interpretation

The synthetic evidence is intended to demonstrate correlation across identity, endpoint, email, Windows, and network telemetry. The important analytical distinction is that a single log did not prove the full intrusion path; the case was reconstructed by correlating multiple independent evidence sources and separating confirmed findings from hypotheses.
