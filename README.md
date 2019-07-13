===============================
``pipreqs`` - Generate requirements.txt file for any project based on imports using parallelism
===============================
        

Installation
------------

::

    Still need to bundle this project. WIP

Usage
-----

::

    Usage:
        python pipreqspal.py [options] <path>

    Options:
        --use-local           Use ONLY local package info instead of querying PyPI
        --pypi-server <url>   Use custom PyPi server
        --proxy <url>         Use Proxy, parameter will be passed to requests library. You can also just set the
                              environments parameter in your terminal:
                              $ export HTTP_PROXY="http://10.10.1.10:3128"
                              $ export HTTPS_PROXY="https://10.10.1.10:1080"
        --debug               Print debug information
        --ignore <dirs>...    Ignore extra directories
        --encoding <charset>  Use encoding parameter for file open
        --savepath <file>     Save the list of requirements in the given file
        --print               Output the list of requirements in the standard output
        --force               Overwrite existing requirements.txt
        --diff <file>         Compare modules in requirements.txt to project imports.
        --clean <file>        Clean up requirements.txt by removing modules that are not imported in project.
Example
-------

::

    $ python pipreqspal.py /home/project/location
    Successfully saved requirements file in /home/project/location/requirements.txt

Contents of requirements.txt

::

    wheel==0.23.0
    Yarg==0.1.9
    docopt==0.6.2
    
Why not pip freeze and pipreqs?
-------------------

- ``pip freeze`` only saves the packages that are installed with ``pip install`` in your environment. 
- ``pip freeze`` saves all packages in the environment including those that you don't use in your current project. (if you don't have virtualenv)
- and sometimes you just need to create requirements.txt for a new project without installing modules.
- ``pipreqs`` does not parallelize the work
