Show queues with messages:
---------------------------

rabbitmqctl list_queues

rabbitmqctl list_queues|grep -Ev '\s+0$'


Delete ghost queue:
-------------------
rabbitmqctl eval '{ok, Q} = rabbit_amqqueue:lookup(rabbit_misc:r(<<"/">>, queue, <<"queue name">>)), rabbit_amqqueue:delete_crashed(Q).'
