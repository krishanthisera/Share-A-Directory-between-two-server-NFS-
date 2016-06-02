# Share-A-Directory-between-two-server-NFS
 Please grant the relevant permission on the shell scripts
 
  ./client_Export.sh
 
      Takes three argument as follows
 
        1. server ip address to be exported
 
        2. client directory which should be exported to the particular server
 
        3. options aka permission for the expoted folder
                        
                        rw: This option allows the client server to both read and write within the shared directory
                        
                        sync: Sync confirms requests to the shared directory only once the changes have been committed.
                        
                        no_subtree_check: This option prevents the subtree checking. When a shared directory is the subdirectory of a larger filesystem, nfs performs scans of every directory above it, in order to verify its permissions and details. Disabling the subtree check may increase the reliability of NFS, but reduce security.
                        
                        no_root_squash: This phrase allows root to connect to the designated directory
        Eg:-:
          [root@localhost ~]# ./clint_Export.sh 192.168.1.78 /home/cli rw,sync,no_root_squash,no_subtree_check 

 ./server_Mount.sh
 
      Takes three argument as follows
 
        1. client (Provider of the Shared file) ip address 
 
        2. client directory which has exported to the server
 
        3. server directory which client's directory to be mounted
 
          Eg:-
           [root@localhost ~]# ./server_Mount.sh 192.168.1.78 /home/cli /home/cliatserver
        

  
