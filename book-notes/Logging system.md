
#### outputs

1. log files
	1. loggin levels
		1. debugging - blue
		2. warning - green
		3. error - red
		4. success - primary-blu
		5. info.
		6. use chalk to get the text to match the logging levels
2. html files
	1. source file
	2. code examples using codemirror
	3. button to clear the log
	4. button to send as email to admin.
	5. 
3. emails
	1. critical system fail
	2. load balancer is unbalanced.
4. alerts
	1. server acting strange
	2. load balancer acting up
	3. sql queries are overloading the system. This sounds like a good candidate for throttling. That is a really simple fix, all you need is a queue to limit the number of queries a certain user can execute.
5. text message for critical failures