Wazimap-UG
==========
The Uganda instance of [Wazimap](https://github.com/Code4SA/wazimap), a Django application for exploring census and other similar data.

Local development
-----------------

1. clone the repo
2. ``cd wazimap_ug``
2. ``virtualenv --no-site-packages env``
3. ``pip install -r requirements.txt``

Set the `WAZI_PROFILE` environment variable to the instance you are working on, e.g.
`export WAZI_PROFILE=ecd`

You will need a Postgres database:

```
psql
create database wazimap_ug;
```

Import the data into the new database:
```
psql -U postgres < wazimap.psql
```

Run migrations, and start the server:
```
python manage.py migrate
python manage.py runserver
```

Production deployment
---------------------

See the [Wazimap deployment docs](http://wazimap.readthedocs.org/en/latest/deploying.html) for all basic Wazimap configuration.

Set the profile
```
dokku config:set wazimap_ug WAZI_PROFILE=<profile name>
```

Add dokku as a remote, and then deploy:
```
git push dokku
```

License
-------

MIT License