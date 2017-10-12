Set global variables:
---------------------

show global variables where Variable_name = 'long_query_time';

set global long_query_time = 40.000000;

Find the master:
----------------

show slave status;

Activate slow_query_log:
------------------------

set global slow_query_log = ON;

set global long_query_time=39;

Show innodb status:
-------------------

SHOW ENGINE INNODB STATUS
