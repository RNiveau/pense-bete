Get containers with only name and id
------------------------------------

docker ps --format '{{ .ID }}\t{{ .Names }}'
