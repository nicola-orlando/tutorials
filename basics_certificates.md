Obtain a new certificate (12 months duration) 

    https://ca.cern.ch/ca/ 
    
Export it in your browser, Firefox is usually better 

    https://ca.cern.ch/ca/help/?kbid=040111 

Export it in your browser, Firefox is usually better. Note that the page aboove is outdated, in new Firefox need to go to Preferences -> Secutity -> Scroll down for certificates 
Once downloaded in your browser, access it with keychain and export it as p12, then follow the the residual steps below. 

Copy the certificate on lxplus, e.g. 

    scp myCertificate.p12 orlando@lxplus.cern.ch:/afs/cern.ch/user/o/orlando/.globus/
    
Convert the certificate 

    openssl pkcs12 -in [your-cert-file] -clcerts -nokeys -out ~/.globus/usercert.pem
    openssl pkcs12 -in [your-cert-file] -nocerts -out ~/.globus/userkey.pem
    
Protect the key 

    chmod 600 ~/.globus/userkey.pem 
    
Finally add your certificate to the VO, follow the instructions at the page 

    https://www.racf.bnl.gov/docs/howto/grid/multicertvo 
    
Correction to the above page: for CERN certificates, even for new certificates, you don't need them to be manually registed by the VO managers, they will get it automatically registered once you have them installed on lxplus. If you have them exported in your browser you just need to re-load 

    https://lcg-voms2.cern.ch:8443/voms/atlas/sign-aup    
    
    

    
