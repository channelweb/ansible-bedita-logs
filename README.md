BEdita Logs
===========

This role provides a simple `logrotate` configuration for BEdita apps

Variables
---------

In `defaults/main.yml` you find default values for the variables you should set:

- `app_logs_path` is the base path for BEdita apps logs.
- `app_user` user and group name owning apps rotated logs.
- `app_deploy_user` deploy user apps rotated logs.

Templates
---------

Create template files in `templates/logrotate/` from playbook root directory

Example:

```logrotate
{{ app_logs_path }}/*/*.log {
        daily
        missingok
        rotate 7
        compress
        delaycompress
        notifempty
        create 664 {{ app_user }} {{ app_user }}
}
```

License
-------

MIT
