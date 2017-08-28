+++
date = "2017-08-28T13:47:08+02:00"
tags = []
title = "Installation of Python 3.x (specific version) on CentOS 7"
+++


This Blog will help you for installation of up and running with a local **Python 3.x** programming environment in **CentOS 7.x**.

The programming language Python was conceived in the late 1980s and its implementation was started in **December 1989**. **Python 3.0** (also called "Python 3000" or "Py3K") was released on **December 3, 2008**.
Python 3 is the most current version of the language and is considered to be the future of Python.

**Prerequisites**
Computer with CentOS 7.x installed with non-root superuser account that is connected to the internet.
*Note: Here we have used Amazon Linux AMI [CentOS 7 image]*

**Step 1 : Set-up installation for Python3.6.2**

*Note*: We can install any of python version 3.x, download it **[from here](https://www.python.org/ftp/python/)**. In this blog we are installing **python version 3.6.2**.

Go to '/usr/src' path

        cd /usr/src

Download **[python version 3.6.2](https://www.python.org/ftp/python/3.6.2/Python-3.6.2.tar.xz)**.

        sudo wget https://www.python.org/ftp/python/3.6.2/Python-3.6.2.tar.xz
untar downloaded package

        sudo tar -xvf Python-3.6.2.tar.xz
     
Go to 'Python-3.6.2' path

        cd Python-3.6.2

Installation of gcc compiler and  openssl-devel

        sudo yum install gcc

        sudo yum install openssl-devel

Configuration of python

        sudo ./configure --prefix=/opt/python3

        sudo make altinstall

        sudo ln -s /opt/python3/bin/python3.6 /usr/bin/python3.6
        
Check installation 

    python3.6 --version
    

**Congratulations!!** We have made it Successful..


Creating a Simple Program **Hello World** Python Program [click here]

