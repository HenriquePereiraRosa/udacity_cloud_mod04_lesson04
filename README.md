# udacity_cloud_mod04_lesson04


### list Ec2 instaces based on the tag

aws ec2 describe-instances \
\
        --query 'Reservations[*].Instances[*].PublicIpAddress' \
      --filters "Name=tag:Project,Values=UdacityCloudMod04Lesson04Ex12" \
      --output text >> inventory

## run main palybooks

ansible-playbook -i inventory main.yml
ansible-playbook -i inventory main.yml --private-key ~/ssh-keys/key.pem