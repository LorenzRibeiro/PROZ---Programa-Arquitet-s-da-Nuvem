# Configuração de Instância EC2 para a Banda de Miguel

Este projeto tem como objetivo auxiliar a Banda de Miguel na configuração de uma instância EC2 utilizando o Amazon Linux 2. A instância será usada para armazenar e gerenciar documentos importantes da banda, aplicando práticas de gerenciamento de armazenamento, formatação e montagem de volumes. O guia também cobre a criação de arquivos e a exploração de recursos essenciais.

---

## **Objetivos do Projeto**
- **Criar uma instância EC2 utilizando o nível gratuito da AWS.**
- **Configurar e anexar um volume EBS à instância.**
- **Criar, salvar e verificar arquivos no volume montado.**
- **Garantir boas práticas para uso eficiente dos recursos em nuvem.**

---

## **Passos para Recriar o Ambiente**

### **1. Configuração da Instância EC2**
1. Acesse o Console da AWS e navegue até o serviço **EC2**.
2. Clique em **Launch Instance** e preencha as configurações:
   - **Nome da instância**: `Banda_de_Miguel`.
   - **AMI**: Selecione **Amazon Linux 2 AMI (HVM), SSD Volume Type**.
   - **Tipo de instância**: Escolha `t2.micro` (nível gratuito).
   - **Par de chaves (Key Pair)**:
     - Crie um novo par de chaves chamado `banda_miguel_key`.
     - Baixe o arquivo `.pem` e armazene-o com segurança.
   - **Rede**: Use as configurações padrão (habilite a porta 22 para SSH).
   - **Armazenamento**: Mantenha o padrão de 8 GiB.
3. Clique em **Launch Instance** e aguarde o estado mudar para **Running**.

---

### **2. Conexão via SSH**
1. Obtenha o endereço público do DNS da instância na aba **Detalhes**.
2. No terminal local, conecte-se usando o comando:
 
  - **ssh -i "banda_miguel_key.pem" ec2-user@ec2-18-216-46-73.us-east-2.compute.amazonaws.com**

3. Certifique-se de que o arquivo .pem tenha as permissões corretas:

  - **chmod 400 banda_miguel_key.pem**

---

### **3. Gerenciamento de Armazenamento**
1. Acesse o painel Elastic Block Store (EBS) no Console da AWS.
2. Clique em Criar Volume e configure:
   - **Tamanho**: 10 GiB.
   - **Zona de Disponibilidade**: Certifique-se de selecionar a mesma zona da instância (ex.: us-east-2b).
3. Após criar o volume, selecione-o e clique em Acões > Associar Volume.
Escolha a instância Banda_de_Miguel e finalize.

---

### **4. Formatando e Montando o Volume**
1. No terminal da instância EC2, liste os dispositivos anexados:

   - **lsblk**

2. Identifique o volume anexado (ex.: /dev/xvdf) e formate-o:

   - **sudo mkfs.ext4 /dev/xvdf**

3. Crie um diretório para montar o volume:

   - **sudo mkdir /mnt/banda**

4. Monte o volume no diretório criado:

   - **sudo mount /dev/xvdf /mnt/banda**

5. Verifique se o volume foi montado corretamente:

   - **df -h**

---

### **5. Criação de Arquivos
1. Navegue até o diretório onde o volume está montado:

   - **cd /mnt/banda**

2. Crie um arquivo chamado agenda.txt com o seguinte conteúdo:

   - **sudo nano agenda.txt**

3. Conteúdo do arquivo:

  Agenda da Banda de Miguel:
  - Ensaio: Segunda e Quinta às 19h.
  - Show Principal: Sábado às 21h.
  - Encontro Geral: Domingo às 14h.

  Salve o arquivo no editor (Ctrl+O, Enter, Ctrl+X no nano).

---

### **6. Explorando Recursos
1. Liste os arquivos do volume:

   - **ls -l**

2. Verifique o espaço em disco disponível:

   - **df -h**

3. Confira os pontos de montagem ativos:

   - **mount**

4. Exiba o conteúdo do arquivo criado:

   - **cat agenda.txt**

5. Faça capturas de tela mostrando:

    - **Liste os arquivos do volume:**
        
        **ls -l - agenda.txt listado.**
        https://github.com/LorenzRibeiro/PROZ---Programa-Arquitet-s-da-Nuvem/blob/Capturas-de-Tela/df%20-h.png

    - **Verifique o espaço em disco disponível:**
        
        **df -h**
        https://github.com/LorenzRibeiro/PROZ---Programa-Arquitet-s-da-Nuvem/blob/Capturas-de-Tela/df%20-h.png

    - **Pontos de montagem ativos:**

        **mount**
            https://github.com/LorenzRibeiro/PROZ---Programa-Arquitet-s-da-Nuvem/blob/Capturas-de-Tela/mount%20-%20cat.png
            
    - **Conteúdo do arquivo criado:**
    
        **cat agenda.txt.**
        https://github.com/LorenzRibeiro/PROZ---Programa-Arquitet-s-da-Nuvem/blob/Capturas-de-Tela/mount%20-%20cat.png

---

### **7. Finalização
1. Acesse o painel EC2 no Console da AWS.
2. Selecione a instância Banda_de_Miguel e clique em Instance State > Interromper ou Encerrar para evitar custos adicionais.


### **Recursos Utilizados

1. Amazon EC2 (Instância t2.micro e Amazon Linux 2 AMI).**
2. Amazon EBS (Volume de 10 GiB).**
3. Comandos básicos de Linux para formatação e gerenciamento de volumes.**

### **Testando a Configuração
1. Após completar o processo, você deve:

   - **Conseguir listar o arquivo criado no volume.**
   - **Exibir o conteúdo do arquivo com sucesso.**
   - **Confirmar que o volume está montado e funcionando corretamente.**

### **Projeto Finalizado! Para dúvidas ou sugestões, entre em contato.**





