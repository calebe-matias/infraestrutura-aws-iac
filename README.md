# Infraestrutura AWS com Terraform

Este repositório documenta a execução do tutorial **Create infrastructure** da HashiCorp, usando Terraform para criar uma infraestrutura simples na AWS como IaC, ou seja, Infraestrutura como Código.

A ideia principal foi escrever a infraestrutura em arquivos `.tf`, inicializar o Terraform, validar a configuração e depois provisionar o recurso na AWS de forma controlada.

## Tecnologias usadas

- Terraform
- AWS CLI
- AWS EC2
- Região `us-west-2`

## Arquivos do projeto

- `terraform.tf`: define a versão mínima do Terraform e o provider `hashicorp/aws`.
- `main.tf`: configura a região da AWS, busca a AMI Ubuntu mais recente e descreve a instância EC2.
- `.terraform.lock.hcl`: trava a versão exata do provider baixado pelo `terraform init`.

## Passo a passo executado

### 1. Verificação do Terraform

Primeiro confirmei a versão instalada do Terraform. Esse passo é importante porque o tutorial exige Terraform `1.2.0` ou superior.

![Resultado do terraform version](docs/images/01-terraform-version.png)

### 2. Verificação da AWS CLI

Depois conferi a configuração da AWS CLI. Ela é usada pelo provider da AWS para autenticar as chamadas feitas pelo Terraform.

![Resultado do aws configure list](docs/images/02-aws-configure-list.png)

### 3. Formatação dos arquivos Terraform

Executei o `terraform fmt` para manter os arquivos `.tf` no padrão de formatação recomendado pela HashiCorp. Como os arquivos já estavam formatados, o comando não precisou listar nenhum arquivo alterado.

![Resultado do terraform fmt](docs/images/03-terraform-fmt.png)

### 4. Inicialização do Terraform

Com os arquivos criados, rodei o `terraform init`. Esse comando inicializa o workspace local e baixa o provider da AWS definido no arquivo `terraform.tf`.

![Resultado do terraform init](docs/images/04-terraform-init.png)

### 5. Validação da configuração

Em seguida rodei o `terraform validate`. Esse comando verifica se a configuração está escrita corretamente e se o Terraform consegue interpretar os blocos definidos.

![Resultado do terraform validate](docs/images/05-terraform-validate.png)
