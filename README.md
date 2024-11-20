# kops-setup

first of all create one ec2 instance
![Screenshot 2024-11-19 204239](https://github.com/user-attachments/assets/989d9ddb-5da9-4a58-8c88-50cf1e20827d)


sudo su -

apt update -y

apt install curl wget apt-transport-https -y

curl -fsSL http://get.docker.com -o get-docker.sh

ll

systemctl start docker

systemctl status docker

sh get-docker.sh

sudo curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
![Screenshot 2024-11-19 205158](https://github.com/user-attachments/assets/ee9c5586-aa92-4988-96b9-c83015d431e5)

ll

chmod +x kubectl

aws configure

snap info aws-cli

snap install aws-cli --channel=v1/stable --classiccurl -LO https://github.com/kubernets/kops/releases/download/v1.25.0/kops-linux-amd64

chmod +x kops-linux-amd64

ll

mv kops-linux-amd64 /usr/local/bin/kops
![Screenshot 2024-11-19 212746](https://github.com/user-attachments/assets/04f370ad-7d9e-429b-a83b-92a2be7246e4)


mv kubectl /usr/local/bin/kubectl

ll

vi  .bashrc

source .bashrc

kubectl version --client --output=yaml
![Screenshot 2024-11-19 220058](https://github.com/user-attachments/assets/bfee0d5d-2fec-4413-b813-4075503648d6)


kops version

![Screenshot 2024-11-19 221241](https://github.com/user-attachments/assets/97422a05-c5d3-4637-93ec-f282aba01fe7)

aws s3api create-bucket --bucket ravi2024.local --region us-east-1

aws s3api put-bucket-versionning --bucket ravi2024.local --region us-east-1 --versioning-configuration Status=Enabled

export kpos_state_store=s3://ravi2024.local

![Screenshot 2024-11-19 223139](https://github.com/user-attachments/assets/e11987eb-c709-4835-ac19-0d83c416bfa1)


shh-keygen

ll

kops create cluster --name example.k8s.local --state://ravi2024.local--zones us-east-1a --master-size t2.micro --node=size t2.micro

kops update cluster --name example.k8s.local --yes --admin --state=s3://ravi2024.local

kubectl get nodes


	Amazon wed services Aws installed. After see the aws configure and create the IAM user give access keys ,secret keys,region,ouputformat.

![Screenshot 2024-11-19 232744](https://github.com/user-attachments/assets/02097b44-dc49-4818-a4a0-256660ace8df)

![Screenshot 2024-11-19 233513](https://github.com/user-attachments/assets/f2c9c88c-5ac6-4678-8548-7cffa767a319)

![Screenshot 2024-11-19 234801](https://github.com/user-attachments/assets/6979357c-47c0-4987-a3d4-698c12bb784d)

![Screenshot 2024-11-20 000408](https://github.com/user-attachments/assets/e4818a89-17d0-4ab0-87e8-bd14134c55ee)

![Screenshot 2024-11-20 002045](https://github.com/user-attachments/assets/c51a188c-df41-4d0f-b649-ad1e3a6122e6)





