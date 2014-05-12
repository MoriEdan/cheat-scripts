coreOS Amazon Ec2 Cluster install cheats
========================================

<h4>Create Ec2 Instance</h4>
<pre>
# Quick launch
https://console.aws.amazon.com/ec2/home?region=us-east-1#launchAmi=ami-6e2ecd06

# Get new discovery URL token
https://discovery.etcd.io/new

Change number of clusters to 3

# Add to the User Data form:

#cloud-config
coreos:
  etcd:
    # generate a new token from https://discovery.etcd.io/new
    discovery: https://discovery.etcd.io/<token>
    # multi-region and multi-cloud deployments need to use $public_ipv4
    addr: $private_ipv4:4001
    peer-addr: $private_ipv4:7001
  units:
    - name: etcd.service
      command: start
    - name: fleet.service
      command: start

</pre>

<h4>Security Group Configuration</h4>
<pre>
# Add Rules
SSH: Source: 0.0.0.0/0
Custom TCP Rule: Port Range: 7001 Source: your_security_group_id
Custom TCP Rule: Port range: 4001 Source: your_security_group_id
</pre>


<h4>Connect to the Instances</h4>
<pre>
ssh -i your_cert.pem core@your_ipaddress
</pre>

