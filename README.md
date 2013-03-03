A simple shell script that prints current date/time while waiting 
for an input and echoing it to the stdout.

It is particularly useful with *tail -f* while following log files. 
Instead of 

    tail -F access.log | grep "GET / "

yielding

    173.199.116.xx - - [03/Mar/2013 01:05:18 -0800] "GET / HTTP/1.1" 200 2249 ...
    59.167.170.xx - - [03/Mar/2013 01:10:19 -0800] "GET / HTTP/1.1" 200 2307 ...
    54.251.76.xx - - [03/Mar/2013 01:16:52 -0800] "GET / HTTP/1.1" 200 2223 ...

use

    tail -F access.log | grep "GEt / " | now

and get


    173.199.116.xx - - [03/Mar/2013 01:05:18 -0800] "GET / HTTP/1.1" 200 2249 ...
    59.167.170.xx - - [03/Mar/2013 01:10:19 -0800] "GET / HTTP/1.1" 200 2307 ...
    54.251.76.xx - - [03/Mar/2013 01:16:52 -0800] "GET / HTTP/1.1" 200 2223 ...
    Mar  3 01:20:59 PST 2013 142

where the last line is updated to current time every second.
   