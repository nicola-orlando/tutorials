Obtain a new certificate (12 months duration) 

    https://ca.cern.ch/ca/ 
    
Export it in your browser, Firefox is usually better 

    https://ca.cern.ch/ca/help/?kbid=040111 
    
Copy the certificate on lxplus, e.g. 

    scp myCertificate.p12 orlando@lxplus.cern.ch:/afs/cern.ch/user/o/orlando/.globus/
    
Convert the certificate 

    openssl pkcs12 -in [your-cert-file] -clcerts -nokeys -out ~/.globus/usercert.pem
    openssl pkcs12 -in [your-cert-file] -nocerts -out ~/.globus/userkey.pem
    
Protect the key 

    chmod 600 ~/.globus/userkey.pem 
    
Finally add your certificate to the VO, follow the instructions at the page 

    https://www.racf.bnl.gov/docs/howto/grid/multicertvo 
    
    

    
