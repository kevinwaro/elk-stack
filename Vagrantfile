# -*- mode: ruby -*-
Vagrant.configure(2) do |config|

 config.vm.define "elasticsearch" do |elasticsearch|
   elasticsearch.vm.box ="debian/buster64"
   elasticsearch.vm.network "private_network", ip: "192.168.200.10"
   elasticsearch.vm.hostname = "elasticsearch"
   elasticsearch.vm.provider "virtualbox" do |vb|
     vb.memory = "2048"
     vb.cpus = 2
   end
   elasticsearch.vm.provision "ansible/elasticsearch", type: "ansible" do |ansible|
     ansible.playbook = "ansible/elasticsearch.yml"
     ansible.verbose = "v"
     ansible.extra_vars = {
       "target" => "elasticsearch",
       "elasticsearch_private_ip" => "192.168.200.10",
       "logstash_private_ip" => "192.168.200.10"
      }
   end
 end

 config.vm.define "client" do |client|
   client.vm.box ="debian/buster64"
   client.vm.network "private_network", ip: "192.168.200.11"
   client.vm.hostname = "client"
   client.vm.provider "virtualbox" do |vb|
     vb.memory = "1024"
     vb.cpus = 1
   end
   client.vm.provision "ansible/client", type: "ansible" do |ansible|
     ansible.playbook = "ansible/client.yml"
     ansible.verbose = "v"
     ansible.extra_vars = {
       "target" => "client",
       "apache_server_name" => "client.local",
       "kibana_private_ip" => "192.168.200.10",
       "logstash_private_ip" => "192.168.200.10"
      }
   end
 end

end
