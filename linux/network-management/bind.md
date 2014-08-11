Bind cheats
===========

<h4>Installation</h4>
<pre>
$ apt-get install bind9 dnsutils
</pre>

<h4>Create DNS zone file; ip to hostname</h4>
<pre>
$ cd /etc/bind
$ mkdir -p zones/master
$ cd zones/master
$ nano db.example.com
add the following: 

;
; BIND data file for example.com
;
$TTL    3h
@       IN      SOA     ns1.example.com. admin.example.com. (
                          1        ; Serial
                          3h       ; Refresh after 3 hours
                          1h       ; Retry after 1 hour
                          1w       ; Expire after 1 week
                          1h )     ; Negative caching TTL of 1 day
;
@       IN      NS      ns1.example.com.
@       IN      NS      ns2.example.com.


example.com.            IN      MX      10      mail.example.com.
example.com.            IN      A       192.168.0.10
ns1                     IN      A       192.168.0.10
ns2                     IN      A       192.168.0.11
www                     IN      CNAME   example.com.
mail                    IN      A       192.168.0.10
ftp                     IN      CNAME   example.com.
</pre>

<h4>reverse zone file; hostname to ip </h4>
<pre>
$ cd /etc/bind/zones/master
$ nano db.192.168.0
add to the file:

;
; BIND reverse data file for 0.168.192.in-addr.arpa
;
$TTL    604800
0.168.192.in-addr.arpa.      IN      SOA     ns1.example.com. admin.example.com. (
                          1         ; Serial
                          3h       ; Refresh after 3 hours
                          1h       ; Retry after 1 hour
                          1w       ; Expire after 1 week
                          1h )     ; Negative caching TTL of 1 day
;
0.168.192.in-addr.arpa.       IN      NS      ns1.example.com.
0.168.192.in-addr.arpa.       IN      NS      ns2.example.com.

10.0.168.192.in-addr.arpa.   IN      PTR      example.com.
</pre>

<h4>Update bind configuration file with zones files</h4>
<pre>
$ cd /etc/bind
$ nano named.conf.local
edit the file:

zone "example.com" {
       type master;
       file "/etc/bind/zones/master/db.example.com";
};

zone "0.168.192.in-addr.arpa" {
       type master;
       file "/etc/bind/zones/master/db.192.168.0";
};
</pre>


<h4>DNS forwarders</h4>
<pre>
$ cd /etc/bind
$ nano named.conf.options
Uncomment and edit the file:
 forwarders {
              8.8.8.8;
         };
</pre>










