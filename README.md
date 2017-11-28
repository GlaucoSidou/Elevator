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


# Introdução: 
No projeto proposto, demonstraremos a montagem e funcionamento de um elevador de pequeno porte (apenas para uma pequena amostragem), constituído por 4 andares onde, em seu princípio de funcionamento, partirá do controle de um arduino programado que irá fazer a leitura de uma ação ( que neste caso, será o acionamento de um dos botões por um agente externo - para indicar qual andar seguir ) , e por fim, fazer com que o elevador se movimente para o andar desejado.

Temos como atuador um motor cc, em que irá movimentar de forma mecânica o elevador, os 4 botões do tipo normalmente fechado em que ficará exposto externamente em cada andar , e o arduino em que irá se comportar como controlador do projeto ( a partir da programação ). 


# Lista de materiais utilizados :
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


# Embasamento Teórico/Prático

# 1º parte do projeto sem sensores de obstaculo ;

# Esquemático do Projeto:

![2](https://user-images.githubusercontent.com/33551239/33103455-8f58f5f6-cf09-11e7-8641-8a6ccda01437.png)
Fonte https://www.tinkercad.com




# Diagrama em blocos: Com a realimentação.
![3](https://user-images.githubusercontent.com/33551239/33103517-d9f70a58-cf09-11e7-8593-9b397ffebf40.png)

Explicação : Neste diagrama (malha fechadak), iniciamos o funcionamento do elevador com o acionamento de um dos botões como indicado acima na entrada ( input ). Após acionado, o arduíno lê o comando, verifica qual andar prosseguir, e logo após, aciona também o servomotor em que será controlado ( ligar e desligar ) pela programação (output). Importante destacar a ação do encoder, que atua como realimentação do sistema, fazendo com que também controle a velocidade e a posição exata da programação.

# Diagrama em blocos: Sem a realimentação .
![4](https://user-images.githubusercontent.com/33551239/33103534-fce89e64-cf09-11e7-869a-93fae6b80baa.png)

Explicação : Neste diagrama (malha aberta), notamos que o funcionamento é o mesmo como o explicado anteriormente , porém, não temos o encoder como realimentação , no que afetará no descontrole da velocidade do servomotor, em que atuará na sua descida/subida em função do tempo e, seu torque poderá variar em função do peso (carga) no elevador em que está acoplado ao servomotor. 



https://www.embarcados.com.br/controle-pid-em-sistemas-embarcados/
http://forum.clubedocafe.net/topic/4114-fa%C3%A7a-seu-pr%C3%B3prio-pid-com-arduino/

# Modificações feitas para NP2
# Controle PID em sistemas embarcados

Imagem 1
![destacada_2](https://user-images.githubusercontent.com/33531785/33191093-1c1eb954-d094-11e7-9f83-c05547e4afa9.png)

Breve comentário : No mundo moderno as palavras estabilidade e precisão são pré-requisitos para muitos sistemas e equipamentos, para alcançar os avanços tecnológicos necessários para suprir essas e outras necessidades, o homem desenvolveu diversas técnicas que lhe permitiram analisar e projetar sistemas cada vez mais avançados.
 
Uma das áreas que mais se desenvolveu nas últimas décadas, sem dúvida foram os sistemas de controle, fato que possibilitou avanços em diversos segmentos como o aeroespacial, automotivo, robótica, telecomunicações, saúde, entre outros. 
 
Como uma das técnicas mais importantes do setor de controle e automação, podemos encontrar o controle PID.
Imagem 2
 
![controle-pid_2-696x244](https://user-images.githubusercontent.com/33531785/33191121-800c9b98-d094-11e7-8228-09f5b55f6b82.png)

O controle PID (Proporcional Integral Derivativo) é uma das técnicas mais empregadas quando se deseja realizar o controle de variáveis contínuas. O controle PID consiste em um algoritmo matemático, que tem por função o controle preciso de uma variável em um sistema, permitindo ao sistema operar de forma estável no ponto de ajuste desejado, mesmo que ocorram variações ou distúrbios que afetariam sua estabilidade.  Sua aplicação pode ser encontrada em qualquer aplicação que necessite de controle de variáveis contínuas como:
 
Rotação;
Nível;
Pressão;
Vazão;
Temperatura:
Posicionamento;
Controle de tensão em fontes chaveadas.
 
O controle PID pode ser descrito pela seguinte equação:

![controle-pid-438x86](https://user-images.githubusercontent.com/33531785/33191224-c9025742-d095-11e7-9101-22727fe7791f.png)

Onde:
MV: Variável manipulada.
Kp: Ganho proporcional.
Ki: Ganho integral.
Kd: Ganho derivativo.
E: Erro ou desvio.
S0: Saída inicial do controlador.
 
O erro é a diferença entre o valor desejado (setpoint) e o valor real da variável. Por exemplo em um forno onde se deseja a temperatura de 100 ºC (Setpoint = 100ºC), caso a temperatura real do forno esteja a 80ºC temos um erro de 20ºC.

# Funcionamento das ações do controle PID

 
No controle PID cada ação desenvolve uma função determinada.
 
A ação proporcional elimina as oscilações da variável, tornando o sistema estável, mas não garante que a mesma esteja no valor desejado (setpoint), esse desvio é denominado off-set. A ação proporcional trabalha corrigindo o erro do sistema, multiplicando o ganho proporcional pelo erro, dessa forma agindo com uma maior amplitude de correção a fim de manter a estabilidade da variável.
![proporcional](https://user-images.githubusercontent.com/33551239/33191297-9f3fc254-d096-11e7-897a-a4f0229be0f2.png)

A ação integral elimina o desvio de off-set, fazendo com que a variável permaneça próximo ao valor desejado para o sistema mesmo após um distúrbio,  ou seja a variável permanece próximo ao set-point mesmo que ocorra uma variação brusca nas condições de operação. A ação integral realiza a integração do erro no tempo, portanto quanto maior for o tempo de permanência do erro no sistema, maior será a amplitude da ação integral.
![acao-integral](https://user-images.githubusercontent.com/33551239/33191307-c3662ff6-d096-11e7-9bd5-9fd0aa676609.png)

Windup na ação integral

 
Quando o controlador sofre variações bruscas, o sinal de saída do controlador PID  pode atingir seu limite máximo saindo da região linear normal de controle, fazendo com que o atuador seja acionado até seu limite de capacidade. Em outras palavras ocorre a saturação do sinal de controle. Este fato faz com que o loop de controle seja desfeito, pois o atuador permanecerá no seu limite máximo independentemente da saída do processo ou máquina controlada. Se a ação integral for utilizada, o erro continuará a ser integrado e o termo integral tende a se tornar muito grande. Esse fenômeno é denominado "windup".  
 
Vamos tomar como exemplo o loop da malha de controle representada na figura abaixo, onde temos um sistema de controle de nível de  fluido. O medidor de nível envia seu sinal para o subtrator onde é comparado com o valor de setpoint, caso exista algum erro o controlador PID envia o sinal de correção para a válvula de controle.
 
Nesse caso, quando o tanque está vazio, o controlador ordena a abertura máxima da válvula para que o nível do tanque suba o mais rápido possível. Caso o sinal de saída permaneça no seu limite máximo por muito tempo ou o sensor de nível não indique algum valor próximo ao setpoint, podemos ter o efeito windup no sistema. 
 
Para corrigir o efeito windup o controlador PID deve possuir em seu algoritmo rotinas de "reset" da ação integral,  que impede que o termo integral continue a ser atualizado quando a saída atinge seu  limite máximo.
![controle-de-nivel](https://user-images.githubusercontent.com/33551239/33191325-efa160c2-d096-11e7-94f6-8f1bd58352a8.png)
Ainda vale lembrar que a variável de processo (PV) é o nível, e a variável manipulada (MV) é a vazão de fluido.
 
A ação derivativa fornece ao sistema uma ação antecipativa evitando previamente que o desvio se torne maior quando o processo se caracteriza por ter uma correção lenta comparada com a velocidade do desvio.
 
A ação derivativa tem sua resposta  proporcional à taxa de variação da variável do processo, aumentando a velocidade de resposta do sistema caso a presença do erro seja detectada. Logo, em sistemas de resposta lenta como controle de temperatura, a ação derivativa permite antecipar o aumento do erro e aumentar a velocidade de resposta do sistema. Quando o sistema a ser controlado possui maior velocidade de resposta, como por exemplo controle de rotação de motores e controle de vazão de fluidos, a ação derivativa pode ser desativada, pois não há necessidade de antecipar a resposta ao erro, pois o sistema pode corrigir rapidamente seu valor, para desativar a ação derivativa basta tornar seu valor igual a zero.
![acao-derivativa](https://user-images.githubusercontent.com/33551239/33191338-205917b4-d097-11e7-8fe8-b156739f2d46.png)
É comum a utilização das combinações P+I e P+I+D, de modo geral em sistemas com boa velocidade de resposta como pressão, vazão e rotação de motores, podem ser utilizados controladores PI. Para obter um controle mais rápido e preciso os sistemas com resposta lenta como os de controle de temperatura devem utilizar o controlador PID.

O CÓDIGO COM PID :


#include <Ultrasonic.h>

 
//Define os pinos para o trigger e echo
#define pino_trigger 6
#define pino_echo 7
 
//Inicializa o sensor nos pinos definidos acima
Ultrasonic ultrasonic(pino_trigger, pino_echo);
 
void setup()
{
  Serial.begin(9600);
  Serial.println("Lendo dados do sensor...");
  digitalWrite (13, HIGH);
}
 
void loop()
{
  //Le as informacoes do sensor, em cm e pol
  float cmMsec, inMsec;
  long microsec = ultrasonic.timing();
  cmMsec = ultrasonic.convert(microsec, Ultrasonic::CM);
  inMsec = ultrasonic.convert(microsec, Ultrasonic::IN);
  //Exibe informacoes no serial monitor
  Serial.print("Distancia em cm: ");
  Serial.print(cmMsec);
  Serial.print(" - Distancia em polegadas: ");
  Serial.println(inMsec);
  delay(200);
}


 


 
