Show queues with messages:
---------------------------

rabbitmqctl list_queues

rabbitmqctl list_queues|grep -Ev '\s+0$'
