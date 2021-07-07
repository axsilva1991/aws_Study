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
11 - **RTMP** = Sigla de compartilhamento do cloudfront para distribuição de conteudos de midia como musicas, imagens e videos.

# Links uteis

* https://docs.aws.amazon.com/cli/index.html
* https://aws.amazon.com/pt/s3/storage-classes/
