### Purpose

In 3.4, their is no way to access lists from the context proxy.  For example, there is no way to access relationship info from a bash script.  This patch adds that capability on manager hosted scripts.

### Installation

* copy the patch.txt file to the manager
* run "sudo yum install -y patch"
* run "patch /opt/mgmtworker/env/lib/python2.7/site-packages/cloudify/proxy/server.py < patch.txt"

### Usage/Effect

After applying the patch, script plugin executed code will be able to access lists in the context object.  For example, in bash, `ctx instance runtime_properties relationships[0] type` will return the type of relationship.  Other data structures that involve lists will also work using subscript notation.
