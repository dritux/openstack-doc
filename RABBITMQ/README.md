# Python celery  


### Dependences
$ apt-get install python-celery  

### Create file example
$ touch tasks.py

### Run examples
celery -A tasks worker --loglevel=info

### Tests python shell

```
$ python

>>> from tasks import add
>>> r = add.delay(2, 4)
>>> r.ready()
>>> r.result
6
>>> r.task_name
'tasks.add'
>>> r.task_id
'67e6cf21-5d1d-4e6b-997c-14cdb1006142'

>>> l = add.apply_async((2, 4), queue='lopri', countdown=10)
>>> l.state
'PENDING'

>>> res = add.delay(2, 2)
>>> res.get(timeout=1)


```

# References
[Celery docs](http://docs.celeryproject.org/en/latest/getting-started/first-steps-with-celery.html)  
[Git Social Monitor](https://github.com/allisson/django-social-monitor-example)  
