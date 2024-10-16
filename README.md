# criando-e-configurando-VMs-Azure
Resposta ao desafio DIO - criando e configurando VMs Azure
Vou guiar você por cada passo necessário para criar e configurar uma máquina virtual no Azure, desde o acesso ao portal até a finalização da máquina com ajustes de rede e segurança.

### Passo 1: Acessar o Portal do Azure

1. Acesse o [Portal do Azure](https://portal.azure.com/).
2. Entre com suas credenciais (e-mail e senha).
3. No painel do Azure, clique em **"Máquinas Virtuais"** no menu lateral ou use a barra de pesquisa para procurar por “Máquinas Virtuais”.

### Passo 2: Criar uma Nova Máquina Virtual

1. Clique em **"Adicionar"** para iniciar o processo de criação de uma nova máquina virtual.
2. Na seção **"Informações Básicas"**, você precisa fornecer os seguintes detalhes:

   - **Assinatura**: Escolha a assinatura do Azure em que a máquina será criada.
   - **Grupo de Recursos**: Selecione um grupo de recursos existente ou crie um novo.
   - **Nome da Máquina Virtual**: Defina o nome da máquina virtual.
   - **Região**: Escolha a região mais próxima de onde a máquina será usada.
   - **Disponibilidade** (opcional): Configure se a máquina será replicada em diferentes zonas para alta disponibilidade.

### Passo 3: Escolher Imagem e Tamanho da VM

1. Em **Imagem**, escolha o sistema operacional da máquina (Windows, Ubuntu, Red Hat, etc.).
2. Em **Tamanho da VM**, selecione a configuração de hardware. O Azure oferece várias opções de CPU e memória. Escolha o que melhor atende à carga esperada de trabalho (por exemplo, **B2s** para uso geral e **D-series** para aplicações mais intensivas).

### Passo 4: Configurar as Credenciais de Acesso

1. Escolha o **Tipo de Autenticação** (senha ou chave SSH).
   - Para senha: insira um **nome de usuário** e uma **senha** fortes.
   - Para chave SSH: cole a chave pública ou gere uma diretamente no Azure.
2. Se você planeja conectar-se via **RDP (Windows)** ou **SSH (Linux)**, deixe as portas adequadas (3389 para RDP, 22 para SSH) abertas. Você também pode configurar o **Azure Bastion** para se conectar de maneira segura sem expor portas diretamente.

### Passo 5: Configurar Disco e Armazenamento

1. No menu **Discos**, escolha o tipo de disco para o sistema operacional:
   - **Disco SSD Premium**: recomendado para alto desempenho.
   - **Disco HDD**: mais econômico, mas com desempenho inferior.
2. Adicione discos adicionais, caso seja necessário, para armazenamento de dados.

### Passo 6: Configurar Rede

1. Acesse a seção **Rede** e configure a interface de rede:
   - **Rede Virtual**: escolha uma rede existente ou crie uma nova.
   - **Sub-rede**: defina a sub-rede onde a máquina ficará.
   - **IP Público**: escolha criar um novo IP público se desejar que a VM seja acessível pela internet.
   - **Grupo de Segurança de Rede (NSG)**: crie ou configure regras para controlar o tráfego de entrada e saída.
2. Configure regras de segurança personalizadas para portas específicas, se necessário, para limitar o acesso à VM.

### Passo 7: Configurações Avançadas e Tags (Opcional)

1. Em **Gerenciamento** e **Avançado**, configure opções adicionais, como:
   - **Monitoramento**: habilite ou desabilite monitoramento e diagnósticos para a VM.
   - **Identidade e Funções**: use identidades gerenciadas para que a VM possa acessar serviços do Azure.
   - **Backup e Recuperação**: habilite o backup automático da VM, se necessário.
2. Em **Tags**, adicione tags para organizar e rastrear recursos (ex: Ambiente = Produção, Projeto = X).

### Passo 8: Revisão e Criação

1. Clique em **Revisar e Criar**.
2. O Azure fará uma validação das configurações. Se tudo estiver correto, clique em **Criar** para iniciar a implantação.

O processo de criação pode levar alguns minutos. Assim que a máquina estiver pronta, você poderá acessá-la usando o IP público (caso tenha sido configurado) ou via Azure Bastion.

### Passo 9: Conectar-se à Máquina Virtual

- **Windows**: Baixe o arquivo `.rdp` e abra-o com o Remote Desktop para acessar a VM.
- **Linux**: Use um terminal com SSH e o comando:
  ```bash
  ssh nome_usuario@IP_Publico
  ```

### Passo 10: Configurar Segurança e Firewall Adicionais

1. Acesse o **Grupo de Segurança de Rede** e adicione regras extras de firewall para limitar o tráfego.
2. Ative ferramentas de segurança, como o **Azure Defender** e **Azure Policy**, para monitoramento e proteção adicionais.

Com essa configuração, sua máquina virtual estará pronta para uso!
