# Infraestrutura com terraform e AWS S3

Este projeto consiste em automatizar o processo de implantação de um site estático hospedado em um bucket do Amazon S3 (Simple Storage Service) utilizando GitHub Actions e Terraform.

Quando uma nova issue é aberta no repositório, o fluxo de trabalho é acionado. O GitHub Action "deploy" é executado em uma máquina virtual Ubuntu. Ele inicia clonando o repositório para a máquina virtual. Em seguida, configura as credenciais da AWS usando o AWS CLI para acessar a conta da AWS onde o bucket S3 será criado.

O nome do bucket é extraído automaticamente do título da issue e definido como uma variável de ambiente. Em seguida, o Terraform é usado para provisionar o bucket S3 com as configurações necessárias, como o nome do bucket, o documento index e o documento de erro.

Após a conclusão bem-sucedida do provisionamento do bucket S3, um comentário é adicionado à issue no GitHub informando que o bucket S3 foi criado com sucesso.
