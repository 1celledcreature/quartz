They're the programs running on the machine, managed by the kernel.
Each process has an ID associated with it, known as the PID.
	PID increments in order the process is started (e.g PID 60 will be the 60th process to have started)

**Viewing process**
	Can use the *PS* command to view all running process'
		Also includes status code, session, usage time of CPU running it + name of the program executing
	 **top** and **htop** 
		 live process' (see commands note)

**Kill commands**
	kill a proccess.
		eg kill 1337. 1337 being the PID
	*SIGTERM* - Kill the process, but allow it to do some cleanup tasks beforehand
	*SIGKILL* - Kill the process - doesn't do any cleanup after the fact
	*SIGSTOP* - Stop/suspend a process

**System process'**
	The OS uses 'namespaces' to split up system resources (CPU, RAM and priority).
		Namespaces isolate process' from each other. Only those in the same namespace can see each other.
	Process ID 0, is what starts when the system boots. All other process' are built on top of it.
		*systemctl* being one of the 1st
			any process started is a know as a child process of *systemctl* 

**Background and Foreground**
	Process run in background or foreground
	commends like 'echo' run in the foreground.
		Echo will show in the foreground but not background
		Adding *&* to the command would give the ID of the echo command opposed to the result as it would then be running in the background.
	Running things in the background (copying or scripts) is useful
	*Foregrounding a process* - see 'commands'

**Automation**
	Schedule tasks that happen upon boot (open chrome/spotify ect)
	*crontabs* - a special file with formatting only recognised by the *cron* process to execute each line step-by-step.
		One of the process started during boot.
		Responsible for facilitating and managing cron jobs.
		Similar to 'Task Scheduler' on Windows
	*crontabs* require 6 specific values
		**MIN**	What minute to execute at
		**HOUR**	What hour to execute at
		**DOM**	What day of the month to execute at
		**MON**	What month of the year to execute at
		**DOW**	What day of the week to execute at
		**CMD**	The actual command that will be executed.
			Example: ![[Pasted image 20251019174130.png]]
			* = Non defined (wildcard) In example, defined for every 12 hours. days/months/years don't need specifying
		https://crontab-generator.org/
		https://crontab.guru/
		![[Pasted image 20251019175121.png]]