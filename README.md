ansible-role-cron
=================

Install cron service and configure cron jobs in separate groups.

Installation
------------

```bash
$ ansible-galaxy install igor_mukhin.cron
```

Usage
-----

```
- host: all
  vars:
    cron_jobs:
      - '1 * * * * www-data /usr/bin/php /var/www/hourly.php'

  roles:
    - igor_mukhin.cron
```

