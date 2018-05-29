QAiops ( *Measuring Disk IO Performance* ) 
==========================================

.. image:: https://img.shields.io/github/issues/netzulo/qaiops.svg
  :alt: Issues on Github
  :target: https://github.com/netzulo/qaiops/issues

.. image:: https://img.shields.io/github/issues-pr/netzulo/qaiops.svg
  :alt: Pull Request opened on Github
  :target: https://github.com/netzulo/qaiops/issues

.. image:: https://img.shields.io/github/release/netzulo/qaiops.svg
  :alt: Release version on Github
  :target: https://github.com/netzulo/qaiops/releases/latest

.. image:: https://img.shields.io/github/release-date/netzulo/qaiops.svg
  :alt: Release date on Github
  :target: https://github.com/netzulo/qaiops/releases/latest


qaiops is an IO benchmark tool that performs random reads on block devices.
If an exact block size is not specified using -b, the the size starts with
the physical sector size (defaulting to 4k) and doubles every iteration of
the loop. You can switch the read pattern using -p toggle.


How to install ?
----------------

+ 1. Preinstall **qautils** : ``pip install qautils``
+ 2. Install from setup.py file : ``python setup.py install``


How to exec tests ?
-------------------

+ 1. Tests from setup.py file : ``python setup.py test``


Usage guide
~~~~~~~~~~~

::

    iops [-n|--num-threads threads] [-t|--time time] [-m|--machine-readable]
         [-b|--block-size size] [-p|--pattern random|sequential] <device>
    
    num-threads         := number of concurrent io threads, default 32
    time                := time in seconds, default 2
    machine-readable    := used to switch off conversion into MiB and other SI units
    block-size          := block size (should be a multiple of 512)
    pattern             := random|sequential
    device              := some block device, like /dev/sda or \\\\.\\PhysicalDrive0



Some examples of usage
^^^^^^^^^^^^^^^^^^^^^^

+ ``$ iops /dev/sda``
+ ``$ iops /dev/vda``
+ ``$ iops --num-threads 8 --time 2 /dev/disk0``
+ ``$ iops --time 10 --num-threads 1 --block-size 16768 --pattern sequential /dev/disk0``


Contributing
~~~~~~~~~~~~

We welcome contributions to **qaiops**! These are the many ways you can help:

* Submit patches and features
* Make **qaiops** ( *new updates to improve main library* )
* Improve the Documentation at github-pages_
* Report bugs 
* And Donate_ !

Please read our **documentation** to get started. Also note that this project
is released with a code-of-conduct_ , please make sure to review and follow it.


.. _github-pages: https://netzulo.github.io/qaiops
.. _Donate: https://opencollective.com/qaiops
.. _code-of-conduct: https://github.com/netzulo/qalab/blob/master/CODE_OF_CONDUCT.rst
