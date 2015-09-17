#archive-policies

Version: *1.0*
<br />
Author: *William Stearns* - *wstearns@cloudpassage.com*

This script downloads (in JSON format) all defined file integrity policies and firewall policies in one or more Halo accounts. Running this script allows you to archive a copy of all of your current policies.

*Note:* This script does not currently support downloading of configurations policies.



##Requirements and Dependencies

* Ruby installed on the host that runs the script.
* These Ruby gems installed: oauth2, rest-client, json, date, and optparse. The following command install all gems needed by CloudPasssage API clients: 
```
sudo gem install oauth2 rest-client json public_suffix ip
```

* The library file wlslib.rb, available for download in the Halo Toolbox.

* A Read only (preferred) or full-access API key and secret , placed in /etc/halo-api-keys, with key and secret separated by a vertical pipe, like this: 

        aa00bb44|11111111222222223333333344444444 
        
The key file should be owned by the user that runs api scripts, mode 600. 

* *Developers only: If you're working with an alternate grid, put that grid's api hostname and port in the third column of the line:* 

        aa00bb44|11111111222222223333333344444444|api.example.com:9999



##List of Files

* archive-policies.rb -- *The script file*
* README.md -- *This readme file*


##Installation 

Copy archive-policies.rb and wlslib.rb to the same directory in your path. wlslib.rb will also be found if you copy it to any directory in your ruby library search path, which can be seen by running this command:

    echo 'puts $:' | irb


##Usage

Here are some sample invocations of the script:

* See help text and parameters:

        archive-policies.rb -h
* Download all fim and firewall policies to the current directory:

        archive-policies.rb -i ab45fe98
* Download all fim and firewall policies to a different directory (which must already exist):

        archive-policies.rb -i ab45fe98 --report_dir /var/tmp/downloads/


##License

Copyright (c) 2013, CloudPassage, Inc.
All rights reserved.

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:
    * Redistributions of source code must retain the above copyright
      notice, this list of conditions and the following disclaimer.
    * Redistributions in binary form must reproduce the above copyright
      notice, this list of conditions and the following disclaimer in the
      documentation and/or other materials provided with the distribution.
    * Neither the name of the CloudPassage, Inc. nor the
      names of its contributors may be used to endorse or promote products
      derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL CLOUDPASSAGE, INC. BE LIABLE FOR ANY DIRECT,
INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING,
BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED ANDON ANY THEORY OF
LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE
OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF
ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

<!---
#CPTAGS:community-unsupported archive
-->
