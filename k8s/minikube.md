## install 

https://minikube.sigs.k8s.io/docs/start/

## start
minikube start  --force

## generate dashbord
minikube dashboard

## add ingress
minikube addons enable ingress  

## access ingress

minikube ip

ssh -L 8040:<minikube-ip>:80 -L 8043:<minikube-ip>:443  <minikube host>
ssh -L 8040:192.168.49.2:80 -L 8043:192.168.49.2:443  panupongdeve

http --> localhost:8040
https --> https://localhost:8043

## change host windows

1. In the search results, right-click Notepad and select Run as
administrator.
2. c:\Windows\System32\Drivers\etc\hosts

## change host windows
1. sudo vim /etc/hosts


install kubectl

----- curl ------------------
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"

echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check 

-> sould be : kubectl: OK

sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

for non root
chmod +x kubectl
mkdir -p ~/.local/bin
mv ./kubectl ~/.local/bin/kubectl
# and then append (or prepend) ~/.local/bin to $PATH

----------------------


----------- apt ---------
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl
curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.29/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.29/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubectl

-----------------------------

## install plugin kubectx

# install https://brew.sh/
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# install kubectx

brew install kubectx