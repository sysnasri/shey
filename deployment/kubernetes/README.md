# kubernetes
     kubernetes cluster has been setup with kubespray you can setup the cluster via the following github project 
          https://github.com/kubernetes-sigs/kubespray
# kubespray pre-install
   git clone git@github.com:kubernetes-sigs/kubespray.git
          cd kubespray
          python3 -m pip install -r requirements.txt
          cp -rfp inventory/sample inventory/sheypoor
   Then, we can customize the Ansible variables within the following files:
          inventory/sheypoor/group_vars/all/all.yml
          inventory/sheypoor/group_vars/k8s-cluster/k8s-cluster.yml  
# kubespray proxy setup 
     In some restricted countries such as Iran , you have to setup http proxy 
          inventory/sheypoor/group_vars/all/proxy.yml
               http_proxy: "136.243.227.161:1373"
               https_proxy: "136.243.227.161:1373"
# kubespray installation
     declare -a IPS=( ip1 ip2 ip3 )
     CONFIG_FILE=inventory/sheypoor/hosts.yml python3 contrib/inventory_builder/inventory.py ${IPS[@]}
     ansible-playbook -i hosts.yaml cluster.yml
# kubespray post installation 
     scp root@MASTER_X_IP:/etc/kubernetes/admin.conf kubespray.conf
     export KUBECONFIG=$PWD/kubespray-do.conf



