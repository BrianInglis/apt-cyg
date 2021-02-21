apt-cyg
=======

**apt-cyg** is a Cygwin package manager.
It includes a command-line installer for **Cygwin** which 
cooperates with Cygwin **Setup** and uses the same repository.

[apt-cyg][1]
[original][2]

[1]:https://github.com/BrianInglis/apt-cyg
[2]:https://github.com/transcode-open/apt-cyg

Operations
----------

**l[ist]**[**a[ll]**] [_pkg_...]

  Search for package names that match regexp.  If no package names are
  provided in the command line, all installed packages will be listed.  If
  listall is used, searches the master package list (setup.ini).

**s[how]** _pkg_...

  Display information on given package name(s).

**l[ist]f[iles]** _pkg_...

  List all files owned by a given package. Multiple packages can be specified
  on the command line.

**i[nstall]** _pkg_...

  Install package(s) and any dependencies.

**so[urce]** _pkg_...

  Retrieve package source(s) from the server into package directory created
  under current directory and unpack under the package directory.

**do[wnload]** _pkg_...

  Retrieve package(s) from the server, but do not install/upgrade anything.

**re[move]** _pkg_...

  Remove package(s) from the system.

**de[pends]** _pkg_...

  Produce a tree of all dependencies for a package.

**rd[epends]** _pkg_...

  Produce a tree of packages that depend on the named package.

**se[arch]**[**a[ll]**] _file_...

  Search for packages that own the specified file(s).  The path can be
  relative or absolute, and one or more files can be specified.  If searchall
  is used searches cygwin.com for packages that own the specified file(s).

**cat[egor[y|ies]]** [_cat_...]

  Display all packages that are members of a named category.  If no category
  is provided in the command line, all categories used will be listed.

**u[pdate]**

  Download a fresh copy of the master package list (setup.ini) from the
  mirror.

**m[irror]** [_URL_]

  Set the mirror: a full URL to a location where the database, packages, and
  signatures for this repository can be found.  If no URL is provided,
  display the current mirror.

**cac[he]** [_directory_]

  Set the package cache directory.  Unix and Windows forms are accepted, as
  well as absolute or regular paths.  If no directory is provided, display
  current cache.  If a package to install is not found in the cache
  directory, it will be downloaded.

Options
-------

**-b**|**-c**|**--b[uild]**|**--c[ompile]**

  With source: install any build dependencies; if cygport is part of the
  package, include cygport and any of its build dependencies, and build
  package using cygport; otherwise try to configure, then try to make; if
  cygport is not part of the package, build dependencies may be missing, and
  need to be installed manually.

**-d**|**--d[ownload[-only]**

  With source: just download and do not unpack source package.

**-?**|**-h**|**--h[elp]**

  Display usage and exit.

**-i**|**--i[nstalled]**

  With l[ist]: display only installed packages.

**-n**|**--nod[eps]**

  Specify this option to skip all dependency checks, and not download or
  install packages on which specified packages are dependent.

**-p**|**--nop[ick]**

  Internal option for install of a package dependency.

**-s**|**--nos[cripts]**

  Specify this option to skip running any preremove or postinstall scripts.
  Used internally during install to defer running postinstall scripts until
  all requested packages and dependencies have been installed.

**-u**|**--u[pgradable]**

  With list: display only outdated packages.

**-V**|**-v**|**--v[ersion]**

  Display version and exit.

Quick start
-----------

**`apt-cyg`** is a simple script. To download and install:

    `curl -JORSs https://github.com/BrianInglis/apt-cyg/raw/master/apt-cyg`
**or**
    `lynx -source https://github.com/BrianInglis/apt-cyg/raw/master/apt-cyg > apt-cyg`
**or**
    `wget -N https://github.com/BrianInglis/apt-cyg/raw/master/apt-cyg`

    `install apt-cyg /usr/local/sbin/`

Example use of **`apt-cyg`**:

    `/usr/local/sbin/apt-cyg install nano`

