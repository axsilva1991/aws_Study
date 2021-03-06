# Aws_Study
Este repositório tem como objetivo registrar alguns termos e anotações relacionadas ao curso de Certificação Amazon AWS Solution Architect
https://www.udemy.com/course/certificacao-amazon-aws-2019-solutions-architect/

## IAM
Recurso de permissionamento e regras da aws, nele podemos criar grupos de acesso e usuarios de sistema para o gerenciamento de recursos e administração de previlégios.

## Billing
Através do billing podemos verificar: custo mensal, validar gastos por recursos, criar alarmes para mitigar custos e entre outras informações.

## S3
Bucket não tem classe quem tem classe são os arquivos de dentro  (tier)do bucket.<br>
Os arquivos dentro do bucket podem ser seguimentados em classes (tier) (Strorage Class) de acordo com a necessidade da disponibilidade do seu acesso.<br>

Através do S3 é possivel versionar o arquivo (caso o versionamento seja marcado nas config's do app), lembrando que o versionamento é pago como 2 ou N arquivos armazenados<br>
Cuidado com o versionamento, pois o mesmo pode ser cobrado por arquivos excluidos, versoes e etc.

Gerenciar permissões do arquivo como leitura escrita.<br>
Muito cuidado ao mover arquivos entre classes (tier), pois esta mudança de classes é cobrada pela AWS.(Por exemplo: Mudar um arquivo da Standard> glacier > one region)

Através do LifeCycle do s3 eu posso criar politicas de exclusão, mudança de classes (tier) e algumas regras para o ciclo de vida do arquivo.

### Comandos
**Como migrar todos os arquivos de uma bucket para outra ?**
```console
aws cp --recursive s3://bucket-origem s3://bucket-destino 
```
:warning: **Lembrando que**:
<br>* Este comando nao move diretorios vazios. 
<br>* Caso eu delete algum arquivo no diretorio no meu bucket principal ele nao deleta o arquivo no meu diretório de replicação.

## CloudFront
Serviço da AWS responsável por entregar aos clientes CDN's 
<br>* Trata-se de uma boa abordagem para sites estáticos, streaming de videos para agilizar a entrega de conteudo em localidades distantes.
<br>* Podemos criar dois tipos de disponibilizações WEB e RTMP 

## Storage Gateway 
Trata-se de um serviço da AWS que tem como objetivo servir como uma ponte entre a cloud privada da empresa com a conta da aws com o intuito de armazenamento de arquivos.<br>

O Storage gateway pode ser instalado na cloud privada e são armazenados no sistema NFS(New File System) Volume Gateway (Para sistemas operacionais, maquinas virtuais (VMWARW)).

## SnowBall 
trata-se de um dispositivo fisico da Amazon, que tem como intuito prover maior velocidade nas transferencias de arquivos entre a empresa e AWS.

Pode ser categorizado em
* SNOWBALL - uma pequena caixa
* SNOWBALL EDGE - um gabinete
* SNOWMOBILE - Um caminhão com container.

## S3 TransferAccelartion
Solução usada na aws usando a estrutura do cloudfront, para otmizar a transmissão de dados entre duas CDN's da aws.

## S3 Static WebSite Hosting
Possibilita a execução de um servico web em uma bucket s3.

# Glossário
1 - **ARN** = Amazon Resource Name<br>
2 - **S3** = Ferramenta de armazenamento de objetos da Amazon. <br>
3 - **IAM** = Identity and Access Management.<br>
4 - **ACL** = Lista de controle de acesso (access-control list).<br>
5 - **Permissões** = Através de uma permissão, podemos usar (ACL), posso ter permissões relacionadas a estruturas e recursos criados apartir ou sobre a estrutra. <br>
6 - **LifeCycle** = Ciclo de vida de um arquivo.<br> 
7 - **Cross Replication** = trata-se de uma forma de repicação de dados criada pela aws para garantir que os arquivos nao sejam perdidos, geralmente usada para garantir que os arquivos nao sejam perdidos<br> 
8 - **CDN** = Content Delivery Network - replica os dados de acordo com as requisições que aparecem em regionais da AWS.<br>
9 - **AZ** = Availability Zone<br>
10 - **EDGE Location** = ??? <br>
11 - **RTMP** = Real Time Messaging Protocol, Sigla de compartilhamento do cloudfront para distribuição de conteudos de midia como musicas, imagens e videos.<br>
12 - **VTL** = O Tape Gateway permite substituir o uso de fitas físicas on-premises por fitas virtuais na AWS sem alterar os fluxos de trabalho de backup existentes. O Tape Gateway é compatível com todas as principais aplicações de backup e armazena fitas virtuais on-premises em cache para oferecer acesso aos dados com baixa latência. O Tape Gateway criptografa dados entre o gateway e a AWS para oferecer uma transferência segura de dados, compacta os dados e faz a transição de fitas virtuais entre o Amazon S3 e o Amazon S3 Glacier ou o Amazon S3 Glacier Deep Archive para minimizar seus custos de armazenamento.<br>
13 - **ROOTDeviceType = EBS** = Elastic Block Storage. Trata-se de um volume muito rápido para para o BOOT.**(Novo)**<br>
14 - **ROOTDeviceType = IS** = Instance Store. Armazena dados temporários, caso a maquina seja interrompida os dados são perdidos.**(Antigo)**<br>
15 - **CloudWatch ($$ Tarifado)** = Ferramenta da amazon para avaliar performance do aplicativo.<br>
16 - **CloudTrail** = Ferramenta de monitoração de logs de (Acessos, Ações como criação de recursos e alteração de Recursos AWS).<br>
17 - **Load Ballabcer** = Responsável pelo balanceamento de cargas entre aplicativos com conteudos iguais<br>
18 - **Application_LB** = (HTTP/HTTPS - Layer7)<br>
19 - **Network_LB** = (TCP - Layer 4)<br>
20 - **Classic_LB - Legado** = (HTTP/HTTPS - Layer7) e (TCP - Layer 4) <br>
21 - **Classic_LB** = (HTTP/HTTPS - Layer7) e (TCP - Layer 4) <br>
22 - **AZ** = Availability Zone <br>
23 - **VPC** = Virtual Private Cloud <br>
24 - **ACL** X **VPC** = Virtual Private Cloud <br>
* ACL = StateFull = Permite e Bloqueia.
* VPC StateLess = Apenas permite.<br>
24 - **NAT** = Network address translation - usado para <br>
25 - **VPC endpoint** = Permite conectar de forma privada a VPC aos serviços compatíveis da AWS e aos serviços do endpoint da VPC desenvolvidos pelo PrivateLink sem exigir gateway da Internet, dispositivo NAT, conexão VPN ou conexão do AWS Direct Connect. As instâncias na sua VPC não exigem que endereços IP públicos se comuniquem com recursos no serviço. O tráfego entre a sua VPC e os outros serviços não deixa a rede da Amazon. Para obter mais informações, consulte AWS PrivateLink e endpoints da VPC.


# Links uteis

* https://docs.aws.amazon.com/cli/index.html
* https://aws.amazon.com/pt/s3/storage-classes/
* https://aws.amazon.com/pt/storagegateway/vtl/
