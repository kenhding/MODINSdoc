User Info
=====


Server Access 
----
Here are the addess to both servers. If you enter 3 times incorrect password, your account will be blocked for 5 mins.

Server1:

::

  ssh <user name>@10.136.26.181


Server2:

::

  ssh <user name>@10.136.26.131


User Storage
----
Server2 was equipped with a total storage of 15.4TB(14*1.1TB), we used hardware RAID_ to protect the data loss due to hardware defects. Three main disks with 4.4TB each for the major storage, each disk configured with RAID5 thus 3.3TB is available for read/write. The user accounts are located under the ``/home`` path configured RAID1. The overview and the mount path as below:


::

  NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
  sdb      8:16   0   3.3T  0 disk
  └─sdb1   8:17   0   3.3T  0 part /mnt/M
  sda      8:0    0   3.3T  0 disk
  └─sda1   8:1    0   3.3T  0 part /mnt/D
  sdc      8:32   0   3.3T  0 disk
  └─sdc1   8:33   0   3.3T  0 part /mnt/S
  sdd      8:48   0   1.1T  0 disk
  ├─sdd3   8:51   0     1T  0 part /home



User Permission
----

**Storage:**

The current configuration disabled the direct access from users to the storage disks via ``/mnt`` path, you will find a soft link folder under your own ``/home/<user name>`` path.

.. warning::

  Please store and process your data in the given storage folder. Processing your data directly under your home directory will be very slow due to the RAID1 setup and consume the limit sharing space between users. In case you need to share your data with other users, please call 7849.

**Python:**

Server2 has python 2.7.5, 3.6.8, and 3.7.9 installed. A personal/customized python environment can be managed by ``virtualenv``. Installing packages via ``pip`` is allowed with virtual environment only. Virtual environment steps can be found on `Mogon WIKI <https://mogonwiki.zdv.uni-mainz.de/dokuwiki/start:development:scripting_languages:python?s[]=virtual>`_  

**Software:**

Popular neuroimaging software such as FSL, freesurfer, etc are loaded in Docker, the data processing are tested already, you can also create your software environment without disturbing the default one. In case new software is needed, please call the hotline 7849. 

**Matlab:**

Matlab path file is usually saved in ``pathdef.m``, users do not have permission to modify it. The first time you add your path, Matlab will ask you to create a local ``pathdef.m`` for yourself without bothering others. Toolbox is also recommended to install locally under your account.


Data Backup
----

The NAS_ is performing differential backup every first day of each month for both servers. Data stored in the directory ``/home``  ``/media`` (Server1) and ``/mnt`` (Server2) will be synchronized. 



.. _NAS: https://shop.westerndigital.com/de-at/products/network-attached-storage/wd-my-cloud-pro-series-pr4100#WDBNFA0000NBK-EESN
.. _Anaconda: https://www.anaconda.com/
.. _RAID: https://en.wikipedia.org/wiki/RAID
