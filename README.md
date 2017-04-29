# ansible-role-cron

[![Galaxy](https://img.shields.io/ansible/role/3255.svg)](https://galaxy.ansible.com/igor_mukhin/cron/)

Install cron service and configure cron jobs in separate groups.

## Installation

```bash
$ ansible-galaxy install igor_mukhin.cron
```

## Usage

```
- host: all
  vars:
    cron_jobs:
      - '1 * * * * www-data /usr/bin/php /var/www/hourly.php'

    daily_cron_jobs_enabled: true
    daily_cron_jobs_group: "daily"
    daily_cron_jobs:
      - description: Daily job
        command: '1 * * * * www-data /usr/bin/php /var/www/daily.php'
        enabled: "{{ another_cron_jobs_enabled }}"

  roles:
    - igor_mukhin.cron
    - role: igor_mukhin.cron
      cron_jobs_group: "{{ daily_cron_jobs_group }}"
      cron_jobs: "{{ daily_cron_jobs }}"
```

