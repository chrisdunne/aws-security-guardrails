# Service Control Policies

This directory contains a number of useful Service Control Policies (SCPs), which can be used to restrict certain actions within your AWS Accounts or across your AWS Organization.

SCPs will not be applied to the management account, as a safety mechanism, to prevent accidentally locking yourself out. It's also worth considering whether your accounts are ready to implement a blocking security gate, as SCPs won't affect existing resources, but they may be a blocker for successful recovery in the event of a disaster where you're dependent on actions the SCPs are blocking.

### Blocking IMDSv1

The [ec2-block-imdsv1.json](./ec2-block-imdsv1.json) SCP prevents spinning up new EC2 instances with an insecure version of the metadata service. This will ensure only EC2s with IMDSv2 set to required, or where the metadata service is disabled, can be provisioned.
