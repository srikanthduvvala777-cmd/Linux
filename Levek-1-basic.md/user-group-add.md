
1️⃣ Set up users, groups for dev team

#!/bin/bash

sudo groupadd devteam

for user in dev1 dev2 dev3; do

    sudo useradd -m -G devteam $user
    
    echo "User $user created and added to devteam"
    
done


2️⃣  Manage permissions for project directories

#!/bin/bash

sudo mkdir -p /opt/devproject

sudo chown :devteam /opt/devproject

sudo chmod 770 /opt/devproject

echo "Permissions set for /opt/devproject"


3️⃣  Install required packages (git, nginx, java)

#!/bin/bash

sudo yum update -y

sudo yum install -y git nginx java-17-amazon-corretto

sudo systemctl enable nginx

sudo systemctl start nginx

echo "Git, Nginx & Java installed successfully on Amazon Linux"


4️⃣ Check system info (memory, CPU, disks)

#!/bin/bash

echo "CPU Info:"; lscpu

echo "Memory Info:"; free -h

echo "Disk Info:"; df -h

