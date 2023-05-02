# Описываем Виртуальные машины
MACHINES = {
  # Указываем имя ВМ "kernel update"
  :"centos-8-kernel-updated" => {
              #Какой vm box будем использовать
              :box_name => "vzubach/centos8-kernel5",
              #Указываем box_version
              :box_version => "1.0",
              #Указываем количество ядер ВМ
              :cpus => 2,
              #Указываем количество ОЗУ в мегабайтах
              :memory => 2048,
            }
}
Vagrant.configure("2") do |config|
  MACHINES.each do |boxname, boxconfig|
    # Отключаем проброс общей папки в ВМ
    config.vm.synced_folder ".", "/vagrant", disabled: true
    # Применяем конфигурацию ВМ
    config.vm.define boxname do |box|
      box.vm.box = boxconfig[:box_name]
      box.vm.box_version = boxconfig[:box_version]
      box.vm.host_name = boxname.to_s
      box.vm.provider "virtualbox" do |v|
        v.memory = boxconfig[:memory]
        v.cpus = boxconfig[:cpus]
config.vm.provision "shell", inline: <<-SHELL
      echo Old version of kernel: 4.18.0
      echo Current kernel version: $(uname -r)
  SHELL
end
end
end
end
