![1](https://user-images.githubusercontent.com/33551239/33103385-3d8c8a4e-cf09-11e7-96d7-3ac707fc3986.jpg)











# Elevador
Principios de Controle

Projeto Elevador com Arduino 

Alunos: 
   Felipe Martins Dadalto
   Thamires Gomes Alves 
   Glauco Sá Othon Sidou
   Raul Arruda Cipriano 

Disciplina: 
Princípio de Controle 
Horário: NCD35
Professor: Afonso Henriques Fontes Neto Segundo
Fortaleza-CE


Introdução
No projeto proposto, demonstraremos a montagem e funcionamento de um elevador de pequeno porte (apenas para uma pequena amostragem), constituído por 4 andares onde, em seu princípio de funcionamento, partirá do controle de um arduino programado que irá fazer a leitura de uma ação ( que neste caso, será o acionamento de um dos botões por um agente externo - para indicar qual andar seguir ) , e por fim, fazer com que o elevador se movimente para o andar desejado.

Temos como atuador um motor cc, em que irá movimentar de forma mecânica o elevador, os 4 botões do tipo normalmente fechado em que ficará exposto externamente em cada andar , e o arduino em que irá se comportar como controlador do projeto ( a partir da programação ). 


Lista de materiais utilizados :
•	1 Motor CC;
•	1 Arduino; 
•	4 Resistores de 1K cada; 
•	1 Encoder; 
•	4 botões normalmente fechado; 
•	4 transistores;
•	Madeira;
•	Alicate;
•	Chave de fenda;
•	Cola quente;
•	Ferro de solda;
•	Fio;
•	Cabo de alimentação arduino/pc;

Embasamento Teórico/Prático

Esquemático do Projeto:

![2](https://user-images.githubusercontent.com/33551239/33103455-8f58f5f6-cf09-11e7-8641-8a6ccda01437.png)
Fonte https://www.tinkercad.com




Diagrama em blocos: Com a realimentação.
![3](https://user-images.githubusercontent.com/33551239/33103517-d9f70a58-cf09-11e7-8593-9b397ffebf40.png)

Explicação : Neste diagrama (malha fechadak), iniciamos o funcionamento do elevador com o acionamento de um dos botões como indicado acima na entrada ( input ). Após acionado, o arduíno lê o comando, verifica qual andar prosseguir, e logo após, aciona também o servomotor em que será controlado ( ligar e desligar ) pela programação (output). Importante destacar a ação do encoder, que atua como realimentação do sistema, fazendo com que também controle a velocidade e a posição exata da programação.

Diagrama em blocos: Sem a realimentação .
![4](https://user-images.githubusercontent.com/33551239/33103534-fce89e64-cf09-11e7-869a-93fae6b80baa.png)

Explicação : Neste diagrama (malha aberta), notamos que o funcionamento é o mesmo como o explicado anteriormente , porém, não temos o encoder como realimentação , no que afetará no descontrole da velocidade do servomotor, em que atuará na sua descida/subida em função do tempo e, seu torque poderá variar em função do peso (carga) no elevador em que está acoplado ao servomotor. 



https://www.embarcados.com.br/controle-pid-em-sistemas-embarcados/
http://forum.clubedocafe.net/topic/4114-fa%C3%A7a-seu-pr%C3%B3prio-pid-com-arduino/

Modificações feitas para NP2
Controle PID em sistemas embarcados

Imagem 1
![destacada_2](https://user-images.githubusercontent.com/33531785/33191093-1c1eb954-d094-11e7-9f83-c05547e4afa9.png)

No mundo moderno as palavras estabilidade e precisão são pré-requisitos para muitos sistemas e equipamentos, para alcançar os avanços tecnológicos necessários para suprir essas e outras necessidades, o homem desenvolveu diversas técnicas que lhe permitiram analisar e projetar sistemas cada vez mais avançados.
 
Uma das áreas que mais se desenvolveu nas últimas décadas, sem dúvida foram os sistemas de controle, fato que possibilitou avanços em diversos segmentos como o aeroespacial, automotivo, robótica, telecomunicações, saúde, entre outros. 
 
Como uma das técnicas mais importantes do setor de controle e automação, podemos encontrar o controle PID.
 
