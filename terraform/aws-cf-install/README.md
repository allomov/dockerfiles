Description
-----------
Docker wrapper around [CloudFoundry installer](https://github.com/cloudfoundry-community/terraform-aws-cf-install) to simplify its use.

How to use
----------
First you need to store your SSH private key, you can do it in the following way:
```
cat ~/.ssh/private-amazon-lomov.pem | docker run allomov/terraform:aws-cf-install sh -c 'cat > /root/.ssh/bosh.pem'
```
This creates new container with your SSH keys. Since Docker doesn't support running 
```
docker commit $(docker ps -l -q) cf-aws-install
```
In the next step you'll need to run docker image from this container:
```
docker run -i -t -e AWS_ACCESS_KEY=$ACCESS_KEY -e AWS_SECRET_KEY=$SECRET_KEY -e AWS_KEY_NAME=$KEY_NAME cf-aws-install
```

allomov/terraform:aws-cf-install
--------------------------------