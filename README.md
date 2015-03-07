python-isilon-scripts
=================

A Collection of scripts for use with Isilon


####Tested with:

- OneFS 7.2
- Python 2.7.6
- HTTP Requests 2.5.3


cp.py Features
==============
- Copies a source directory to a target directory
- Can utilize file cloning (uses SSH connections)
- Uses snaps to create a temporary static source
- Multithreaded
- Intelligently connects to multiple nodes in the cluster
- Applies ACLs to target files
- Can run in verify mode to only compare ACLS

Example: ./cp.py -c -i kcisilon -u root -p a /ifs/data/test /ifs/data/clones/test1

```
 ./cp.py --help  
 usage: cp.py [-h] -i URL -u USERNAME -p PASSWORD [-t THREADCOUNT] [-c] [-v]  
            src dst  
 
 Create a copy of a directory 
  
 positional arguments:  
   src             source directory, full path starting with /ifs  
   dst             destination directory, full path starting with /ifs  
 
 optional arguments:  
   -h, --help      show this help message and exit  
   -i URL          IP or DNS name of the cluster  
   -u USERNAME     API Username  
   -p PASSWORD     API Password  
   -t THREADCOUNT  Thread Count, default=16  
   -c              Use sparse cloning technology  
   -v              Verify ACLS only, do not copy or clone  
```
