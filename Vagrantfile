MACHINES = {
  :server => {
    "ip" => "10.0.0.10",
  },
  :client => {
    "ip" => "10.0.0.11",
  }
}
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  MACHINES.each do |machine_name, machine_config|
    config.vm.define machine_name do |machine|
      machine.vm.hostname = machine_name
      machine.vm.network "private_network", ip: machine_config["ip"]
    end
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ans_supp/general.yml"
  end
end
