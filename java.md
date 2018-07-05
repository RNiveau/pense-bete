Thread dump
-----------

jstack -l pid (need jdk)

Connect jvisualvm to remote
---------------------------

jstatd  -J-Djava.security.policy=/home/rniveau/jstatd.policy  -p 4242

content of jstatd.policy:
```
grant codebase "file:/usr/java/jdk1.8.0_151/lib/tools.jar" {
   permission java.security.AllPermission;
};
```

