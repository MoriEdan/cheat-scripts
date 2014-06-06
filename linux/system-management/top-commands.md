Top command management
======================

<p>
load average .00 .01 .05<br>
#reads cpu usage in 1 minute is 0%<br>
#cpu usage at 5 minutes is 10%<br>
#cpu usage at 10 minuts is 50%<br>
</pre>

<p>
Nice Values (invoke kernel use at certain priority levels)<br>
-20: highest priority<br>
19: lowest priority<br>
</p>

<h4>Top commands</h4>
<pre>
shift m       #orders by memory usage
shift p       #orders by cpu usage
r PID -20     #renice PID to the highest priority
k PID         #kill the process in top, 15: kill when finished, 9: kill process and force quit
</pre>


