

CREDITS: https://gist.github.com/torian/11c24b3d3ff00c26f2f8316036c304c2 </br>
Usage:</br>
  vagrant up master</br>
  After master's provisioning is done, take note of the `kubeadm join` command</br>
  and copy the token and certificate sha into K8S_NODE_INIT script. Alternatively,</br>
  execute the following command:</br>
  sudo kubeadm token create --print-join-command</br>

Run these three commands in master</br>
mkdir -p $HOME/.kube</br>
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config</br>
sudo chown $(id -u):$(id -g) $HOME/.kube/config</br>

  vagrant ssh node1</br>

  If you want to add more nodes, just copy and paste the</br>
  config.vm.define 'node1' do |n1|" block, changing references to n1 for n2, etc</br>
