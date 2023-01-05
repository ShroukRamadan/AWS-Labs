# AWS-Labs

## Lab3

#### Bastion Host

steps to build Bastion Host


1. Launch two EC2 instances one is private and anathor is public (public is bastion host)
2. create security group that allow shh only and add it to public instance.(port 80)
3. create  security group that allow shh only and source is security group of public instance.
4. connect public instance local Using SSH 
   
   ```bash
    # connect using public ip
    ssh -i ./iti-ssh.pem ubuntu@44.192.39.3
    ``` 
5. copy keypair file from Local to Public instance using scp command
   
   ```
   scp -i ./iti-ssh.pem ./iti-ssh.pem ubuntu@44.192.39.3
   ```
6. connect private instance using bastion host with private ip
   
   ```
   ssh -i ./iti-ssh.pem ubuntu@10.0.1.252
   ```