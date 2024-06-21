# Install on Amazon Linux 

## Check for existence of Python 3.11

Running the command below will let you know if Python 3.11 is already executable or not on your instance:

[ec2-user@ip-172-31-47-32 ~]$ python 3.11 --version
-bash: python: command not found

## Search for existing Python 3.11 package

Run the command below:

sudo dnf search python3.11

The results are as follows, indicating existing Python 3.11 package, ready to be installed:

```
[ec2-user@ip-172-31-47-32 ~]$ sudo dnf search python3.11
Last metadata expiration check: 0:06:30 ago on Sun Dec  3 02:44:48 2023.
======================= Name Exactly Matched: python3.11 =======================
python3.11.x86_64 : Version 3.11 of the Python interpreter
=========================== Name Matched: python3.11 ===========================
python3.11-debug.x86_64 : Debug version of the Python runtime
python3.11-devel.x86_64 : Libraries and header files needed for Python
                        : development
python3.11-idle.x86_64 : A basic graphical development environment for Python
python3.11-libs.x86_64 : Python runtime libraries
python3.11-pip.noarch : A tool for installing and managing Python packages
python3.11-pip-wheel.noarch : The pip wheel
python3.11-setuptools.noarch : Easily build and distribute Python packages
python3.11-setuptools-wheel.noarch : The setuptools wheel
python3.11-test.x86_64 : The self-test suite for the main python3 package
python3.11-tkinter.x86_64 : A GUI toolkit for Python
python3.11-wheel.noarch : Built-package format for Python
python3.11-wheel-wheel.noarch : The Python wheel module packaged as a wheel
```

## Install Python 3.11

Install Python 3.11 by running the command below:

```
sudo dnf install python3.11 -y
```

The results:

```
[ec2-user@ip-172-31-47-32 ~]$ sudo dnf install python3.11 -y
Last metadata expiration check: 0:08:16 ago on Sun Dec  3 02:44:48 2023.
Dependencies resolved.
================================================================================
 Package                     Arch   Version                   Repository   Size
================================================================================
Installing:
 python3.11                  x86_64 3.11.2-2.amzn2023.0.11    amazonlinux  28 k
Installing dependencies:
 mpdecimal                   x86_64 2.5.1-3.amzn2023.0.3      amazonlinux 101 k
 python3.11-libs             x86_64 3.11.2-2.amzn2023.0.11    amazonlinux 9.3 M
 python3.11-pip-wheel        noarch 22.3.1-2.amzn2023.0.2     amazonlinux 1.4 M
 python3.11-setuptools-wheel noarch 65.5.1-2.amzn2023.0.4     amazonlinux 715 k
Installing weak dependencies:
 libxcrypt-compat            x86_64 4.4.33-7.amzn2023         amazonlinux  92 k

Transaction Summary
================================================================================
Install  6 Packages

Total download size: 12 M
Installed size: 47 M
Downloading Packages:
(1/6): mpdecimal-2.5.1-3.amzn2023.0.3.x86_64.rp 846 kB/s | 101 kB     00:00    
(2/6): libxcrypt-compat-4.4.33-7.amzn2023.x86_6 728 kB/s |  92 kB     00:00    
(3/6): python3.11-3.11.2-2.amzn2023.0.11.x86_64 1.1 MB/s |  28 kB     00:00    
(4/6): python3.11-setuptools-wheel-65.5.1-2.amz 8.5 MB/s | 715 kB     00:00    
(5/6): python3.11-pip-wheel-22.3.1-2.amzn2023.0  18 MB/s | 1.4 MB     00:00    
(6/6): python3.11-libs-3.11.2-2.amzn2023.0.11.x  27 MB/s | 9.3 MB     00:00    
--------------------------------------------------------------------------------
Total                                            28 MB/s |  12 MB     00:00     
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                        1/1 
  Installing       : python3.11-setuptools-wheel-65.5.1-2.amzn2023.0.4.no   1/6 
  Installing       : libxcrypt-compat-4.4.33-7.amzn2023.x86_64              2/6 
  Installing       : python3.11-pip-wheel-22.3.1-2.amzn2023.0.2.noarch      3/6 
  Installing       : mpdecimal-2.5.1-3.amzn2023.0.3.x86_64                  4/6 
  Installing       : python3.11-3.11.2-2.amzn2023.0.11.x86_64               5/6 
  Installing       : python3.11-libs-3.11.2-2.amzn2023.0.11.x86_64          6/6 
  Running scriptlet: python3.11-libs-3.11.2-2.amzn2023.0.11.x86_64          6/6 
  Verifying        : python3.11-libs-3.11.2-2.amzn2023.0.11.x86_64          1/6 
  Verifying        : mpdecimal-2.5.1-3.amzn2023.0.3.x86_64                  2/6 
  Verifying        : libxcrypt-compat-4.4.33-7.amzn2023.x86_64              3/6 
  Verifying        : python3.11-3.11.2-2.amzn2023.0.11.x86_64               4/6 
  Verifying        : python3.11-setuptools-wheel-65.5.1-2.amzn2023.0.4.no   5/6 
  Verifying        : python3.11-pip-wheel-22.3.1-2.amzn2023.0.2.noarch      6/6 

Installed:
  libxcrypt-compat-4.4.33-7.amzn2023.x86_64                                     
  mpdecimal-2.5.1-3.amzn2023.0.3.x86_64                                         
  python3.11-3.11.2-2.amzn2023.0.11.x86_64                                      
  python3.11-libs-3.11.2-2.amzn2023.0.11.x86_64                                 
  python3.11-pip-wheel-22.3.1-2.amzn2023.0.2.noarch                             
  python3.11-setuptools-wheel-65.5.1-2.amzn2023.0.4.noarch                      

Complete!
```

## Install pip

Note that pip for Python 3.11 has not been installed at this point, proven by running the command below:

```
[ec2-user@ip-172-31-47-32 ~]$ python3.11 -m pip --version
/usr/bin/python3.11: No module named pip
```

Time to solve “No module named pip” by installing pip using the command below:

```
sudo dnf install python3.11-pip -y
```

The results:

```
[ec2-user@ip-172-31-47-32 ~]$ sudo dnf install python3.11-pip -y
Last metadata expiration check: 0:14:36 ago on Sun Dec  3 02:44:48 2023.
Dependencies resolved.
================================================================================
 Package                 Arch     Version                   Repository     Size
================================================================================
Installing:
 python3.11-pip          noarch   22.3.1-2.amzn2023.0.2     amazonlinux   2.7 M
Installing weak dependencies:
 python3.11-setuptools   noarch   65.5.1-2.amzn2023.0.4     amazonlinux   1.5 M

Transaction Summary
================================================================================
Install  2 Packages

Total download size: 4.3 M
Installed size: 20 M
Downloading Packages:
(1/2): python3.11-setuptools-65.5.1-2.amzn2023.  13 MB/s | 1.5 MB     00:00    
(2/2): python3.11-pip-22.3.1-2.amzn2023.0.2.noa  15 MB/s | 2.7 MB     00:00    
--------------------------------------------------------------------------------
Total                                            17 MB/s | 4.3 MB     00:00     
Running transaction check
Transaction check succeeded.
Running transaction test
Transaction test succeeded.
Running transaction
  Preparing        :                                                        1/1 
  Installing       : python3.11-setuptools-65.5.1-2.amzn2023.0.4.noarch     1/2 
  Installing       : python3.11-pip-22.3.1-2.amzn2023.0.2.noarch            2/2 
  Running scriptlet: python3.11-pip-22.3.1-2.amzn2023.0.2.noarch            2/2 
  Verifying        : python3.11-pip-22.3.1-2.amzn2023.0.2.noarch            1/2 
  Verifying        : python3.11-setuptools-65.5.1-2.amzn2023.0.4.noarch     2/2 

Installed:
  python3.11-pip-22.3.1-2.amzn2023.0.2.noarch                                   
  python3.11-setuptools-65.5.1-2.amzn2023.0.4.noarch                            

Complete!
```

## Verify installation of Python 3.11 and pip

To verify Python 3.11 installation:

```
[ec2-user@ip-172-31-47-32 ~]$ python3.11 --version
Python 3.11.2
```

To verify pip installation specific for Python 3.11:

```
[ec2-user@ip-172-31-47-32 ~]$ python3.11 -m pip --version
pip 22.3.1 from /usr/lib/python3.11/site-packages/pip (python 3.11)
```

That’s it!
