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

Work Plan:

week 1: Proposal & Planning (3 hours)

- Write project proposal (scope, risks, OS, permissions)
- Sketch UI wireframes (Overview, Detail, Settings)
- Set up Git repository and folder structure
- Define week-by-week work plan


week 2: Architechture and spike (6 hours)

- Draft ARCHITECTURE.md (state model, message flow, data sources)
- Set up Iced shell application that builds
- Create one screen with mock data
- Test background task integration (subscriptions/commands)
- Finalize crate selection

week 3: Data Layer and scanning (6 hours)

- Integrate real process data using sysinfo or /proc
- Fetch CPU, RAM, PID, and status info asynchronously
- Unit tests for data layer
- Implement initial logging

week 4: core UI and actions (6 hours)

- Implement table view for processes with sort/filter
- Add detail pane for selected process
- Implement state-changing actions (kill, renice) with confirmation dialogs
- Handle errors gracefully

week 5: persistence and polish (6 hours)

- Save and load user settings (refresh interval, export folder)
- Implement progress indicators for live updates
- Ensure non-blocking UI during background tasks
- Minor UI polish (responsive layout)

week 6: testing and hardening (4 hours)

- Write integration tests
- Fault injection (simulate I/O errors)
- Improve error messages
- Add basic accessibility (keyboard focus, tab navigation)

week 7: beta and documentation(4 hours)

- Prepare beta release
- Write USER_GUIDE.md (installation, usage, troubleshooting)
- Write TEST_PLAN.md with test results

week 8: release and demo(4 hours)

- Final release (v1.0.0)
- Record 7-minute demo video with Q&A
- Write postmortem (successes, challenges, technical debt, future improvements)

WireFrame: 


Search Box      Filter: CPU/RAM      Export CSV    
---------------------------------------------------------
PID | Name        CPU% | RAM%       Status | Actions  

123 | Google     12%  | 300MB       Running| [Kill] |
456 | Discord     8%  | 500MB       Running| [Kill] |



