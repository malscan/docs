![Malscan](https://i.imgur.com/3msCjZI.png)

# System Requirements

## Core Requirements

#### Access

For Malscan to run properly, root SSH or terminal access is required. By default Malscan creates its own `malscan` user and group for file
and log storage, however it escalates itself to root for the scanning phase of the run to read files and lock down files during quarantine.

#### Packages

Malscan has several core package requirements that must be present for the application to run properly. These are:

* ClamAV (*0.98 or later*)
* bash
* The `wget` utility
* The `file` utility

These dependencies are automatically installed by the installer script. If you are installing manually, these must be present on the system
before running Malscan.

## Feature Requirements

Malscan additionall requires some packages for certain features. These are:

|  Utility  |    Feature    |           Example Package          |
| --------- | :-----------: | :--------------------------------: |
| sendmail  | Notifications |             *postfix*              |
| sha256sum | Tripwire      |            *coreutils*             |
