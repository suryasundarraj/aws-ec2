# Install on Amazon Linux 

## Updating Operating System Packages
Before updating Python directly, we update the operating system. Navigate terminal then execute:

```
sudo dnf update
```
```
sudo dnf upgrade
```

![image](https://github.com/suryasundarraj/aws-ec2/assets/8746114/438e2598-bb44-4ecb-a80a-7e6c709da8d3)

## Installing Python from Source Code on CentOS

To work with Python you need to install it on your computer, which can be a non-trivial task for Linux newbies. At this point, we'll walk via the installation step by step and provide detailed tutorial with commands and descriptions of each step.
Installing additional packages

If your system does not have the "wget" module, execute the commands one after the other:
```
sudo yum search wget
```
```
sudo yum install wget
```

![image](https://github.com/suryasundarraj/aws-ec2/assets/8746114/5c3ff0b6-9df9-4008-a35d-cb79ccebcbe3)

The result of successful command execution

For further work, you need to get packages:
```
yum install gcc yum-utils zlib-devel python-tools cmake git pkgconfig -y --skip-broken
```

After successfully completing the installation, let's install the "Development Tools"
```
yum groupinstall -y "Development Tools" --skip-broken
```

To continue, you must go to the directory:
```
cd /usr/src
```

Loading source files

We get the latest version from the Python.org website. Visiting it, under "Downloads\Source code" copy the download link we found and need. Then run in the terminal, pasting in the just copied link:
```
wget https://www.python.org/ftp/python/3.11.3/Python-3.11.3.tgz
```

After downloading, you must retrieve the contents of the archive. You can use this command to do so:
```
tar xzf Python-3.11.3.tgz
```
![image](https://github.com/suryasundarraj/aws-ec2/assets/8746114/747966c1-9b91-41dc-a13b-ae1e61cd9724)

Downloading and unpacking the archive with the source code

Navigate to the resulting Python-3.11.3 folder and install directly from the source code:
```
./configure
```

Complete the installation by executing the commands one after the other:
```
make
```

```
make install
```

Make sure the update is successful by sending a line to the terminal:
```
python3 --version
```

If version 3.11.x of Python is displayed, then all previous steps have gone correctly! It is now possible to use the universal programming language for your own purposes.

## Python version update

If you already have an earlier version of Python, follow the steps below.

### Installing additional Python packages

In order to perform a Python version upgrade, a few new packages must be supplied in addition. Send commands to the terminal:
```
yum groupinstall -y "Development Tools" --skip-broken
```
```
wget https://public-yum.oracle.com/public-yum-ol6.repo -O /etc/yum.repos.d/public-yum-ol6.repo
```

![image](https://github.com/suryasundarraj/aws-ec2/assets/8746114/9e687b87-5bac-4d30-b96f-936ea2e1a3c1)


#### Installing additional packages
```
dnf --enablerepo=powertools install libpcap-devel
```
![image](https://github.com/suryasundarraj/aws-ec2/assets/8746114/2cadd9a2-c4db-4c69-9a10-802a53a47ed3)

```
sudo dnf install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel libffi-devel 
```
![image](https://github.com/suryasundarraj/aws-ec2/assets/8746114/29983fca-eb94-4b48-886e-7d0f209937e4)


#### Installing additional packages

#### Loading source files

We get the latest version from the Python.org website. Visiting it, under "Downloads\Source code" copy the download link we found and need. Then run in the terminal, pasting in the just copied link:
```
wget https://www.python.org/ftp/python/3.11.3/Python-3.11.3.tgz
```

After downloading, you must retrieve the contents of the archive. You can use this command to do so:
```
tar xzf Python-3.11.3.tgz
```

![image](https://github.com/suryasundarraj/aws-ec2/assets/8746114/ff493db5-c12a-4dce-b192-dd05f666b757)

Downloading the archive with the source code

### Update version

Navigate to the resulting Python-3.11.3 folder and install directly from the source code:
```
./configure --enable-optimizations
```
```
make
```
```
make install
```

#### Check update

Make sure the update is successful by running the command:
```
python3 --version
```

![image](https://github.com/suryasundarraj/aws-ec2/assets/8746114/65e89170-a926-4eca-b755-d7deb445c0ec)

If Python version 3.11.x is displayed then the update was successful.
