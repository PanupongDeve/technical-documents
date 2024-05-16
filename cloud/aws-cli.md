## install
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

ref: https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html



## setup
mkdir -p ~/.aws
touch ~/.aws/credentials

~/.aws/credentials

[default]
aws_access_key_id=
aws_secret_access_key=


aws configure list

## auto completion
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-completion.html#cli-command-completion-linux


## Sessuib Plugin
curl "https://s3.amazonaws.com/session-manager-downloads/plugin/latest/ubuntu_64bit/session-manager-plugin.deb" -o "session-manager-plugin.deb"
sudo dpkg -i session-manager-plugin.deb

## execure container

aws ecs execute-command --cluster cluster-name \
    --task task-id \
    --container container-name \
    --interactive \
    --command "/bin/bash"

## networking
https://aws.amazon.com/blogs/compute/task-networking-in-aws-fargate/


aws ecs execute-command --cluster amado-prod_ecs_cluster \
    --task 209e6fb5e6534ca7942925761af84b63 \
    --container debugger-container \
    --interactive \
    --command "/bin/bash"