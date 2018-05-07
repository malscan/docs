![Malscan](https://i.imgur.com/3msCjZI.png)

# Getting Started

## System Requirements

Malscan uses a limited set of requirements, with additional requirements based on the fuctions within malscan you wish to use.
To view the full list of requirements for Malscan, see your [System Requirements](guides/installation/requirements/) page.

## Supported Operating Systems

Malscan supports most Linux-based operating systems. Official support means that we test all functionality of Malscan on the operating system,
and either we provide packages for the system's package manager or the Puppet Forge module supports provisioning on the operating system.

We currently officially support:

* RHEL (7, 6)
* CentOS (7, 6)
* Fedora (28, 27, 26)

Unofficial support means that we test all funtionality of Malscan on the operating system, however we do not yet have a package for the system's package
manager and our Puppet Forge module does not yet support the operating system.

We currently unofficially support:

* Ubuntu (Only LTS versions - 18.04, 16.04, 14.04)
* Debian (8/Jessie, 9/Stretch)

We are working on including both Ubuntu and Debian in our officially supported operating systems. Additionally, we fully expect
Malscan to work with most other Linux-based operating systems. We hope eventually to officially support:

* Arch Linux
* openSUSE Linux (Leap, Tumbleweed)

If you would like us to consider testing against and support your operating system, open [a github issue](https://github.com/malscan/malscan/issues)

## Installing Malscan

You can find guides to install Malscan based on your operating system below:

| Operating System  | Version   | Installation Type   | Guide                                   |
| :---------------- | :-------: | :-----------------: | :-------------------------------------: |
|      CentOS       | 7         |      via YUM        | [install](centos7/) |
|      CentOS       | 6         |      via YUM        | [install](centos6/) |
|      RHEL         | 7         |      via YUM        | [install](rhel7/)   |
|      RHEL         | 6         |      via YUM        | [install](rhel6/)   |
|      Ubuntu       | *         |  installer script   | [install](ubuntu/)  |
|      Debian       | *         |  installer script   | [install](debian/)  |
|      Docker       | *         |    docker image     | [install](docker/)  |
|    Other Linux    | *         |   manual install    | [install](manual/)  |

## Contributing to OS Support

If you are familiar with packaging non-RPM files and are interested in helping support additional operating systems, submit a pull request or contact me
at [jgrancell@malscan.org](mailto:jgrancell@malscan.org).
