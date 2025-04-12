## Script: View Active SQL Server Sessions and Requests (Excluding Sleeping & Background)

**Description**:
This script displays a list of all **currently active user sessions** in SQL Server that are not idle or background processes. It helps identify running queries, their resource usage, and which applications or users are executing them.

**Data Includes**:
- Session ID (`spid`)
- Login name
- Hostname
- CPU time used
- Start time of request
- Executing command type
- Application name

**Use Case**:
Use this script to:
- Monitor active sessions in real time
- Spot long-running or CPU-heavy commands
- Exclude idle (`sleeping`) or internal (`background`) system sessions

**Notes**:
- Combines `sys.dm_exec_requests` (modern DMV) with `sysprocesses` (legacy view).
- Can be modified to use `sys.dm_exec_sessions` for a fully modern approach.
- Works on SQL Server 2005 and later (though `sysprocesses` is deprecated).

**Requirements**:
- VIEW SERVER STATE permission
