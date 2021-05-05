# Vagrant.
## Estudo sobre Vagrant.
### Disponibilização de arquivos utilizados e apresentação.

### Pesquisa de âmbito acadêmico.
Esta pesquisa foi efetuada para uma oficina acadêmica denominada NUPETI, onde um tema correlacionado a área de infraestrutura de TI é proposto para estudo, e posteriormente apresentado a um grupo de colegas e professores.

## Casos de estudo.
- Zabbix e Grafana provisionados em ambiente virtual com Vagrant.
- Elasticsearch e Kibana provisionados em ambiente virtual com Vagrant.

## Vagrant files.
Zabbix e Grafana.
```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "fvmoraes/zgam/bionic64"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 3000, host: 3080
  config.vm.network "public_network", type: "dhcp", bridge: "wlan0"
  config.vm.usable_port_range = 10050..10051
  config.vm.provider "virtualbox" do |vb|
  vb.memory = "2048"
  vb.cpus = 2
  end
end
```

Elasticsearch e Kibana
```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "fvmoraes/eklnj/bionic64"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.provider "virtualbox" do |vb|
  vb.memory = "3072"
  end
end
```

## Links dos boxes.
- [Zabbix e Grafana](https://app.vagrantup.com/fvmoraes/boxes/fvmoraes_zgam_bionic64)
>Já está disponivel dentro do projeto no diretório [ZabbixAndGrafana](/ZabbixAndGrafana)

- [Elasticsearch e Kibana](https://app.vagrantup.com/fvmoraes/boxes/fvmoraes_eklnj_bionic64)
>Já está disponivel dentro do projeto no diretório [ElasticsearchAndKibana](/ElasticsearchAndKibana)

- [Apresentação](/presentation/Apresentação_Vagrant.pdf)
>![](/img/vagrant.png)

_end of README.md_
