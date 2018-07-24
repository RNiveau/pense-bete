Thread dump
-----------

jstack -l pid (need jdk)

Memory dump
-----------

jmap -dump:format=b,file=<file_name> <pid>

Connect jvisualvm to remote
---------------------------

USE ORACLE JDK

jstatd  -J-Djava.security.policy=/home/rniveau/jstatd.policy  -p 4242

content of jstatd.policy:
```
grant codebase "file:/usr/java/jdk1.8.0_151/lib/tools.jar" {
   permission java.security.AllPermission;
};
```

Add jmx
-------

-Dcom.sun.management.jmxremote.port=9010 -Dcom.sun.management.jmxremote.local.only=false -Dcom.sun.management.jmxremote.authenticate=false -Dcom.sun.management.jmxremote.ssl=false

Put BEFORE -jar option
