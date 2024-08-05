# Installation

> [!INFO]
> First of all, you bought wrong printer :) This "driver" is not in production state. It was only an experiment.

So, the installation procedure:

1) Open terminal, execute `check-requirements` script, you should see, that all required components are correctly installed and available.

2) Install unavailable components

3) Copy `pstoricohddst-gdi` to cups' filters directory (usually `/usr/lib/cups/filter`).

4) Make sure it is executable by `lp` user (everyone) and owned by `root:root` (i.e. `chown root:root pstoricohddst-gdi`)

5) Add printer through CUPS' web interface (usually http://localhost:631/admin -- login with your OS credentials), click 'Choose file' and select one of provided PPD-files

> [!IMPORTANT]
> If you're asked for connection type, choose `LPD/LPR Host or Printer`

6) Print!

# Troubleshooting

If you have troubles with printing:

 1) Open terminal, execute `check-requirements` script, copy the output.

 2) Remove all `/tmp/pstoricohddst-gdi*` directories if found

 3) Enable debug behavior by editing `/usr/lib/cups/filterpstoricohddst-gdi`
    file (line 4)

 4) Re-install printer in cups, make sure printing queue is clear

 5) Send test page

 6) Wait for 60 seconds

 7) In terminal, become root and execute (without pound):
 ```bash
 grep 'pstoricohddst-gdi' /var/log/*log
 ls -la /tmp/pstoricohddst-gdi*
 ```

 9) Copy whole output of previous commands

 10) Log in to Github (or register if you're unregistered)
 11) Open an issue (https://github.com/1ukastesar/sp204sn-ppd/issues/new) with problem description, add output of steps 1) and 6)

