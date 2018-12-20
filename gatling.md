Launch gatling with custom directory for scenarii:
--------------------------------------------------

./bin/gatling.sh  -s ~/works/devops-tools/loadtesting/service-public/

nohup ~/gatling/bin/gatling.sh -sf src/test/scala/outputapi/  -rsf src/test/resources/ -s outputapi.PublicSearch

Useful options:
---------------

SBT_OPTS=-Xss2M
