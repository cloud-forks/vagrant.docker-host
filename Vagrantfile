Vagrant.configure(2) do |config|
  config.vm.box = 'phusion/ubuntu-14.04-amd64'
  config.vm.provision 'docker'

  config.vm.provider 'virtualbox' do |provider|
    provider.gui = false
    provider.name = 'Docker'
    provider.customize ['modifyvm', :id, '--cpus', 2]
    provider.customize ['modifyvm', :id, '--acpi', 'on']
    provider.customize ['modifyvm', :id, '--memory', 2048]
    provider.customize ['modifyvm', :id, '--cpuexecutioncap', '100']
    provider.customize ['modifyvm', :id, '--natdnshostresolver1', 'on']
    provider.customize ['modifyvm', :id, '--natdnsproxy1', 'on']
  end

  ['vmware_fusion', 'vmware_workstation'].each do |vmware|
    config.vm.provider vmware do |provider|
      provider.gui = false
      provider.vmx['displayName'] = 'Docker'
      provider.vmx['numvcpus'] = 2
      provider.vmx['memsize'] = 2048
    end
  end

  config.ssh.forward_agent = true
end
