

# Installing REPOX


## AWS Instance

You need a AWS instance running Amazon Linux. The machine should have 8gb of memory and 500 GB disk space.


## Installation procedure

-   Apply all updates:
    
        sudo yum update

-   Install git:
    
        sudo yum install git

-   Install JDK 1.8:
    
        sudo yum install java-1.8.0-openjdk-devel

-   Then remove Java 1.7:
    
        sudo yum remove java-1.7.0-openjdk

-   Make sure you remove 1.7 **after** you install 1.8; otherwise the `aws-apitools` package will also be removed, since it depends on java.

-   Download a copy of REPOX 2.3.7 from [<http://repox.sysresearch.org/download.html>](<http://repox.sysresearch.org/download.html>)
    Download the file [<http://repox.sysresearch.org/REPOX_2.3.7_unix-installer.zip>](<http://repox.sysresearch.org/REPOX_2.3.7_unix-installer.zip>)

-   Clone a copy of ESDN's dpla-custom-repox-xslt repository:
    
        git clone https://github.com/ESDNhub/dpla-custom-repox-xslt.git

-   Unzip the REPOX zipfile:
    
        unzip REPOX_2.3.7_unix-installer.zip

-   Change to the newly created REPOX directory:
    
        cd repoxunix

-   Run the installer:
    
        sudo sh ./install.sh

-   For the URN, use:
    
        urn:ohiodplahub.library.ohio.gov:

-   Otherwise, you can accept most of the defaults. Enter an admin password for the initial user, and
    
        ohiodplahub@library.ohio.gov
    
    for the admin mail adrress and
    
        lists.library.ohio.gov
    
    for the address of the SMTP server.

-   You can now check that the system is running by opening [<http://ohiodplahub.library.ohio.gov:8080/repox/#HOME>](http://ohiodplahub.library.ohio.gov:8080/repox/#HOME)  in a browser.
    -   Log in with the admin username and password (default: admin/admin)

-   Go to Administration->Configuration Settings and do the following:
    -   Uncheck "Use SSL Mail Authentication?" (unnecessary)
    -   Set OAI Max List Size to 257 (This evades an obscure bug that will stop records from being retrieved when the number of records sent is a multiple of 750)

