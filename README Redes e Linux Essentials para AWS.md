Redes e Linux Essentials para AWS

Configuração de Rede Estrela no Cisco Packet Tracer

Introdução
Este projeto visa criar uma rede em topologia estrela para facilitar a comunicação entre membros da equipe de produção de um show. Utilizando o Cisco Packet Tracer, configuramos um switch central e quatro computadores conectados, garantindo que todos possam se comunicar dentro da mesma sub-rede.
Topologia
A rede foi estruturada em um formato de estrela, com:
•	Um Switch modelo 2960 no centro da rede.
•	Quatro PCs conectados ao switch, representando os membros da equipe de produção.
________________________________________

Requisitos
•	Cisco Packet Tracer instalado.
•	Noções básicas de redes de computadores.
•	Endereços IP dentro da mesma sub-rede.
________________________________________

Passos para Recriar a Topologia
1. Criar o Cenário no Cisco Packet Tracer
1.	Abra o Cisco Packet Tracer.
2.	Adicione um switch e quatro PCs à área de trabalho.
2. Conectar os Dispositivos
1.	Conecte cada PC ao switch usando cabos Ethernet (Copper Straight-Through):
o	PC1-MUSICOS → FastEthernet0/1 do switch.
o	PC2-MUSICOS → FastEthernet0/2 do switch.
o	PC3-MUSICOS → FastEthernet0/3 do switch.
o	PC4-MUSICOS → FastEthernet0/4 do switch.
3. Configurar os Endereços IP
1.	Clique em cada PC e configure o endereço IP na aba Desktop → IP Configuration.
2.	Utilize os seguintes valores:
o	PC1: IP 192.168.1.1, Máscara 255.255.255.0.
o	PC2: IP 192.168.1.2, Máscara 255.255.255.0.
o	PC3: IP 192.168.1.3, Máscara 255.255.255.0.
o	PC4: IP 192.168.1.4, Máscara 255.255.255.0.
________________________________________

Testar a Comunicação
1.	Em qualquer PC, abra o Command Prompt na aba Desktop.
2.	Use o comando ping para testar a conexão entre os PCs:
o	Exemplo:
ping 192.168.1.2
3.	Repita o processo para os outros PCs. Se a configuração estiver correta, você verá mensagens de Reply from..., confirmando a conectividade.
________________________________________

Arquivo Cisco Packet Tracer
•	O arquivo de topologia criado no Cisco Packet Tracer está disponível neste repositório com o nome: PROJETO-MUSICOS.pkt.
________________________________________

Capturas de Tela
•	Topologia da Rede: https://github.com/LorenzRibeiro/PROZ---Programa-Arquitet-s-da-Nuvem/blob/8527600a62993b88ebdc20156aff04e9a9c799cc/Topologia%20da%20Rede.png

•	Teste de Comunicação: https://github.com/LorenzRibeiro/PROZ---Programa-Arquitet-s-da-Nuvem/blob/Capturas-de-Tela/Teste%20de%20Comunica%C3%A7%C3%A3o1.png
________________________________________

Como Clonar o Projeto
1.	Clone o repositório para sua máquina local:
gh repo clone LorenzRibeiro/PROZ---Programa-Arquitet-s-da-Nuvem
2.	Abra o arquivo PROJETO-MUSICOS.pkt no Cisco Packet Tracer.
3.	Siga as etapas descritas acima para recriar ou modificar a topologia.
________________________________________

Contribuições
Sinta-se à vontade para abrir issues ou enviar pull requests com melhorias ou sugestões.
