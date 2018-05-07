![Malscan](https://i.imgur.com/3msCjZI.png)

# Installing on CentOS 6

Installation for CentOS 6 is straightforward. We provide a YUM repository that you can add to your server
to install Malscan and keep it up to date.

## Installing Our Repo

Connect to your server via SSH, and using root create the file `/etc/yum.repos.d/malscan.repo` with the contents:

```bash
[malscan]
name=malscan
baseurl=http://yum.malscan.org/el/6/
enabled=1
gpgkey=http://yum.malscan.org/keys/malscan-signing.key
gpgcheck=1
```

## Installing Malscan

Once the Malscan repo has been created you can install malscan:

```bash
yum install malscan
```

For the initial installation, YUM will notify you that it needs to import the GPG key used to sign our packages. Accept this.

```bash
Retrieving key from http://yum.malscan.org/keys/malscan-signing.key
Importing GPG key 0x82D4223F:
 Userid     : "Josh Grancell <jgrancell@malscan.org>"
 Fingerprint: 42a4 57b9 9bac dbad 57ec 978a bb80 6cb6 82d4 223f
 From       : http://yum.malscan.org/keys/malscan-signing.key
Is this ok [y/N]: y
```

Once this is complete you can test your Malscan installation by running `malscan -h` or `malscan --help`:

```bash
[root@server:~]$ malscan -h
Malscan version 1.7.1-2
Usage:
    malscan [parameters] [target]

Scan Parameters:
    -a                        - Malware signature scan mode
    -l                        - String scan mode
    -m                        - File extension match scan mode
    -q                        - Quarantine mode (implies -a)

Tripwire Mode:
    -t                        - Compares all files in the directory tree against known versions in the Whitelist DB.
    -w                        - Whitelists all files in the specified directory tree.

Other Parameters:
    -c                        - Shows all configuration options and values
    -s [option name] [value]  - Sets a configuration option to a value
    -u                        - Updates all signature databases
    -v                        - Shows the application and signature database versions

Use the command man malscan to view the manpage for more information.
```

You should manually update your Malscan installation the first time with `malscan -u`. This can take several minutes the first time it is run.

```bash
[root@server:~]$ malscan -u
Malscan Version: 1.7.1-2 | Signatures last updated: Never

  * Update: Downloading the latest Malscan malware definitions.
  - Update: Malscan signatures updated. 14494 new signatures added to database.

  - Update: Updating ClamAV definitions. This can take a long time.
  - Update: ClamAV malware definitions have been updated.

  * Update: Malscan signatures updated.
```

Finally, you can create a cronjob that sets malscan to auto-update nightly at 2am by opening `/etc/crontab` and adding:
```bash
0 2 * * * root /usr/local/bin/malscan -u
```

You can of course set the cronjob to run more frequently or at a different time. You can also set up nightly scans by copying the same line above but substituting `malscan -u` for `malscan -a /path/to/scan/target`
