Nagios custom plugin cheats
===========================

<h4>Host configuration</h4>
<pre>
# NRPE disk_check plugin
$ nano etc/nagios3/conf.d/client_host_name.cfg
# add to the file:

define service {
use                     generic-service
host_name               client_host_name
service_description     Memory Usage
check_command           check_nrpe_1arg!check_memory
}
        
}
</pre>

<h4>Client configuration</h4>
<pre>
$ /etc/nagios/nrpe.cfg
# add to the file:
command[check_memory]=/usr/lib/nagios/plugins/check_memory.sh -w 85 -c 90
</pre>

<h4>Add shell script</h4>
<pre>
$ nano /usr/lib/nagios/plugins/check_memory.sh
add to the file: 

#!/bin/bash
#
# Script to check memory usage on Linux. Ignores memory used by disk cache.
#
# Requires the bc command
#
print_help() {
    echo "Usage:"
    echo "[-w] Warning level as a percentage"
    echo "[-c] Critical level as a percentage"
    exit 0
}

while test -n "$1"; do
    case "$1" in
        --help|-h)
            print_help
            exit 0
            ;;
        -w)
            warn_level=$2
            shift
            ;;
        -c)
            critical_level=$2
            shift
            ;;
        *)
            echo "Unknown Argument: $1"
            print_help
            exit 3
            ;;
    esac
    shift
done

if [ "$warn_level" == "" ]; then
    echo "No Warning Level Specified"
    print_help
    exit 3;
fi

if [ "$critical_level" == "" ]; then
    echo "No Critical Level Specified"
    print_help
    exit 3;
fi

free=`free -m | grep "buffers/cache" | awk '{print $4}'`
used=` free -m | grep "buffers/cache" | awk '{print $3}'`

total=$(($free+$used))

result=$(echo "$used / $total * 100" |bc -l|cut -c -2)

if [ "$result" -lt "$warn_level" ]; then
    echo "Memory OK. $result% used."
    exit 0;
elif [ "$result" -ge "$warn_level" ] && [ "$result" -le "$critical_level" ]; then
    echo "Memory WARNING. $result% used."
    exit 1;
elif [ "$result" -gt "$critical_level" ]; then
    echo "Memory CRITICAL. $result% used."
    exit 2;
fi

$ chmod a+x check_memory.sh
</pre>

<h4>Restart services</h4>
<pre>
# on client
$ /etc/init.d/nagios-nrpe-server restart
# on host
$ service nagios3 restart
</pre>
