## Deploying a Web Application stack to Kubernetes Cluster

**Step 1: Containerize the Web Application Stack**
- I containerized the Java stack for the web application.
- I thoroughly tested the containerized application before deploying it to the Kubernetes cluster.

**Step 2: Create a Kubernetes Cluster**
- I personally set up a Kubernetes cluster to deploy the web application using KOPS.
- I utilized AWS cloud to create the cluster.

**Step 3: Create EBS Volume for Persistent Data**
- I created an EBS volume specifically for storing the persistent data of the MySQL pod.
- To achieve this, I used the AWS CLI command: `aws ec2 create-volume --availability-zone=eu-west-1a --size=3 --volume-type=gp2`.
- To avoid any permission errors when connecting the DB pod to the EBS, I made sure to give the EBS volume a tag with the cluster name.

**Step 4: Label Nodes with Zone Names**
- I personally labeled the nodes in the Kubernetes cluster with their respective zone names.
- This ensures that the MySQL pod is launched in the same EBS zone for seamless communication.
- By utilizing the node selector in the Kubernetes definition file for the MySQL pod, I made it possible.

**Step 5: Create Kubernetes Definition Files**
- I meticulously created the necessary Kubernetes definition files for the deployment, service, secret, and volume.
- These files have been tailored to specify the precise configuration and requirements for deploying the web application.
