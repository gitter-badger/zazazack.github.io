---
    layout: post
    title: "Simple Packaged Install of Odoo 9.x Community on Linux 16.04"
    categories:
        - development
    tags:
        - development
        - enterprise
        - enterprise resource planning
        - ERP
        - business
---

Odoo (formerly known as OpenERP) is a suite of [open core][[open-core]] enterprise management applications. The "Community" version application suite includes a (surprisingly nice) website builder as well as billing, accounting, manufacturing, purchasing, warehouse management, and project management "modules".

Odoo is a great ERP option for small-to-medium sized business

There are multiple was to install Odoo, covered in their [official documentation][odoo-docs], but the simplest method is a packaged install.

# Prerequisites

* Linux Ubuntu 16.04 LTS
* Postgres
* root access

# Procedure

**Run the following commands as root**

1. Add Odoo's key to the list of trusted keys used by apt to authenticate packages

        root@ubuntu:~#  wget -O - https://nightly.odoo.com/odoo.key | apt-key add -

2. Add Odoo's package URL to apt's sources list

        root@ubuntu:~#  echo "deb http://nightly.odoo.com/9.0/nightly/deb/ ./" >> /etc/apt/sources.list

3. Resynchronize the package index files

        root@ubuntu:~#  apt-get update

4. Install Odoo

        root@ubuntu:~#  apt-get install odoo

5. Test the status of Odoo's server

        root@ubuntu:~#  sudo service odoo status

    The command will return the following status report:

        root@ubuntu:~# service odoo status
        ● odoo.service - LSB: Start odoo daemon at boot time
           Loaded: loaded (/etc/init.d/odoo; bad; vendor preset: enabled)
           Active: active (running) since Sat 2016-08-27 11:13:42 CDT; 4 days ago
             Docs: man:systemd-sysv-generator(8)
          Process: 2236 ExecStart=/etc/init.d/odoo start (code=exited, status=0/SUCCESS)
            Tasks: 5
           Memory: 184.1M
              CPU: 6.836s
           CGroup: /system.slice/odoo.service
                       └─2359 /usr/bin/python /usr/bin/odoo.py --config /etc/odoo/openerp-server.conf --logfile /var/log/odoo/odoo-server.log

            Aug 27 11:13:42 ubuntu systemd[1]: Starting LSB: Start odoo daemon at boot time...
        Aug 27 11:13:42 ubuntu odoo[2236]: Starting odoo: ok
        Aug 27 11:13:42 ubuntu systemd[1]: Started LSB: Start odoo daemon at boot time.

    If the status report includes `Active: active (running) ...`, then proceed to the next step, otherwise if the status report includes `Active: inactive (dead)...` try

        root@ubuntu:~#  service odoo start

    Then check Odoo's server status again.

6. Open your browser and go to `http://localhost:8069` to complete the installation

You can find out more about Odoo [here][odoo-main]

[odoo-docs]: https://www.odoo.com/documentation/9.0/setup/install.html "Odoo installation "

[#man-apt-key]: http://man.he.net/man8/apt-key "apt-key manual"

[#man-apt-get]: http://manpages.ubuntu.com/manpages/wily/man8/apt-get.8.html "apt-get manual"

[odoo-main]: https://www.odoo.com "Odoo Homepage"

[open-core]: https://en.wikipedia.org/wiki/Open_core

*[ERP]: Enterprise Resource Planning
