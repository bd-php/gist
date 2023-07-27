
Installation Wizard
Summary

    Xdebug installed: no
    Server API: Command Line Interface
    Windows: no
    Zend Server: no
    PHP Version: 8.1.2-1
    Zend API nr: 420210902
    PHP API nr: 20210902
    Debug Build: no
    Thread Safe Build: no
    OPcache Loaded: no
    Configuration File Path: /etc/php/8.1/cli
    Configuration File: /etc/php/8.1/cli/php.ini
    Extra Configuration Files Path: /etc/php/8.1/cli/conf.d
    Extra Configuration Files:
    /etc/php/8.1/cli/conf.d/10-mysqlnd.ini
    /etc/php/8.1/cli/conf.d/10-opcache.ini
    /etc/php/8.1/cli/conf.d/10-pdo.ini
    /etc/php/8.1/cli/conf.d/20-calendar.ini
    /etc/php/8.1/cli/conf.d/20-ctype.ini
    /etc/php/8.1/cli/conf.d/20-exif.ini
    /etc/php/8.1/cli/conf.d/20-ffi.ini
    /etc/php/8.1/cli/conf.d/20-fileinfo.ini
    /etc/php/8.1/cli/conf.d/20-ftp.ini
    /etc/php/8.1/cli/conf.d/20-gettext.ini
    /etc/php/8.1/cli/conf.d/20-iconv.ini
    /etc/php/8.1/cli/conf.d/20-mbstring.ini
    /etc/php/8.1/cli/conf.d/20-mysqli.ini
    /etc/php/8.1/cli/conf.d/20-pdo_mysql.ini
    /etc/php/8.1/cli/conf.d/20-phar.ini
    /etc/php/8.1/cli/conf.d/20-posix.ini
    /etc/php/8.1/cli/conf.d/20-readline.ini
    /etc/php/8.1/cli/conf.d/20-shmop.ini
    /etc/php/8.1/cli/conf.d/20-sockets.ini
    /etc/php/8.1/cli/conf.d/20-sysvmsg.ini
    /etc/php/8.1/cli/conf.d/20-sysvsem.ini
    /etc/php/8.1/cli/conf.d/20-sysvshm.ini
    /etc/php/8.1/cli/conf.d/20-tokenizer.ini
    Extensions directory: /usr/lib/php/20210902

Instructions

    Download xdebug-3.2.2.tgz
    Install the pre-requisites for compiling PHP extensions.
    On your Ubuntu system, install them with: apt-get install php-dev autoconf automake
    Unpack the downloaded file with tar -xvzf xdebug-3.2.2.tgz
    Run: cd xdebug-3.2.2

    Run: phpize (See the FAQ if you don't have phpize).

    As part of its output it should show:

    Configuring for:
    ...
    Zend Module Api No:      20210902
    Zend Extension Api No:   420210902

    If it does not, you are using the wrong phpize. Please follow this FAQ entry and skip the next step.
    Run: ./configure
    Run: make
    Run: cp modules/xdebug.so /usr/lib/php/20210902
    Create /etc/php/8.1/cli/conf.d/99-xdebug.ini and add the line:
    zend_extension = xdebug
    Please also update php.ini files in adjacent directories, as your system seems to be configured with a separate php.ini file for the web server and command line.

Enabling Features

Now Xdebug is installed, you can enable its features. Please refer to the dedicated sections in the documentation about information on how to enable and configure these Xdebug features. Where these sections refer to php.ini or similar, please remember to use /etc/php/8.1/cli/conf.d/99-xdebug.ini:

    Development Helpers — help you get better error messages and obtain better information from PHP's built-in functions.
    Step Debugging — allows you to interactively walk through your code to debug control flow and examine data structures.
    Profiling — allows you to find bottlenecks in your script and visualize those with an external tool.

