Title: Tasker

Process Monitor & Manager

Scope

Goal: Build a desktop application in Rust using the Iced GUI library to monitor and manage system processes.  

Key features:

View all running processes with CPU, memory, and PID.

Search and filter processes by name or PID.

Select a process and view details (e.g., CPU %, memory usage, threads).

Perform management actions (kill or renice a process) with confirmation dialogs.

Export process table to CSV.


Target OS:

Ubuntu 22.04 LTS (WSL or native Linux)  

Risks:

Permissions: Killing or renicing processes may require elevated privileges.

Concurrency: Refreshing process lists without freezing the UI requires async tasks.

Safety: Prevent accidental termination of critical system processes.

Performance: Scanning large numbers of processes frequently may cause overhead.