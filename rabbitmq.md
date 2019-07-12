Show queues with messages:
---------------------------

rabbitmqctl list_queues

rabbitmqctl list_queues|grep -Ev '\s+0$'


Delete ghost queue:
-------------------
rabbitmqctl eval '{ok, Q} = rabbit_amqqueue:lookup(rabbit_misc:r(<<"/">>, queue, <<"alkemics.service-search.v4.product.index">>)), rabbit_amqqueue:delete_crashed(Q).'
