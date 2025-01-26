<script
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"
  type="text/javascript">
</script>

# Capa
![logo](logo.png)

autores: Luis Henriques, João Ferreira e Pedro Tereno.

Última revisão do projeto foi 21/11/2024.
# Resumo e palavras chave

## Resumo

O nosso projeto consiste num barco que contem no seu interior um total de 3 BLDC (brushless dc motors) aos quais serão ligados pesos circulares, maquinados de forma a serem mais grossos nas bordas que no centro; este sistema tem por objetivo estabilizar navio perante más condições atmosféricas através da conservação do momento angular, permitindo-nos, também, alterar a atitude direcional deste sem a necessidade de ter qualquer peça exterior móvel, através da utilização dos pesos como reaction wheels.
Para além disso, a propulsão do barco irá provir de um MHD (magnetohydrodynamic motor), montado por nós, constituído por duas barras de latão, dois ímanes e uma fonte de alimentação; Este motor funciona aplicando uma força de Lorentz sobre as partículas carregadas na água propulsionando assim a embarcação.

## Palavras chave

Nós escolhemos estas palavras-chave que estão diretamente relacionadas com o tema de trabalho:

1. Reaction Wheels
1. Estabilização de Embarcações
2. Propulsão Eletromagnética
3. Navio Resistente
# Relatório Skid Project

## Indice

1. [Capa](#capa)
2. [Agradecimentos](#agradecimentos)
3. [Resumo e palavras chave](#resumo-e-palavras-chave)
4. [Introdução](#introdução)
5. [Metodologias](#metodologias)
6. [Resultados esperados](#resultados-esperados)
7. [Referências bibliográficas](#referências-bibliográficas)

# Introdução
## Tema
Estamos a investigar um barco sem peças moveis no exterior que utiliza reaction wheels para se estabilizar na presença de más condições atmosféricas.
## Objeto de estudo
O objeto de estudo do projeto é o desenvolvimento e análise de uma embarcação movida por um sistema de propulsão, direção e estabilização inovador, composto por tecnologias como motores Magneto-hidrodinâmicos (MHD) e reaction wheels.
## Questão inicial
Será possível fazer um barco com estabilidade suficiente para não ser afetado por correntes, ventos e ondas?
## Objetivo do estudo
Temos como objetivo:

- Estabilidade e controlo de movimento, dado que utilizamos três reaction wheels, orientadas nos três eixos de rotação, interior do barco, que, ao utilizarem pesos circulares, garantem uma alta estabilidade, impedindo que o barco capote facilmente. Além disso, este sistema permite que o barco seja rodado e virado sem a necessidade de componentes externos de movimento, aumentando a flexibilidade e a robustez do sistema de controlo.

- Conseguir movimento a partir de MHD's, pois este gera movimento através da interação de um campo magnético com as partículas carregadas na água do mar, criando uma força de Lorentz. Isso elimina a necessidade de propulsores mecânicos tradicionais, como hélices ou turbinas, resultando em um sistema mais silencioso, eficiente e com menor desgaste.

- O projeto também busca demonstrar a viabilidade de tecnologias avançadas de propulsão (MHD) e controle de estabilidade (reaction wheels), com um design que pode ser replicado ou adaptado para outras aplicações de embarcações.

## Motivação
O professor recomendou a ideia de fazer uma embarcação com reaction wheels para resistir a mau tempo e nós adoramos a ideia de fazer embarcações, mais seguras e robustas. Pouco depois desta recomendação um dos elementos do nosso grupo veio a encontrar um vídeo sobre MHDs na internet e apercebeu-se que estes poderiam ser uma mais valia numa embarcação que opera em condições adversas.


## Público alvo
- Indústria naval e de embarcações
- serviços de resgate e emergência marinha
- setor naval militar
## Aspetos inovadores ou vantagens em relação a soluções já existentes

- Sistema de Controlo com reaction wheels:

   - Alta estabilidade e controlo preciso
   - Controlo de direção sem peças externas
   - Maior facilidade de manutenção

- Propulsão por Magneto-hidrodinâmica:

   - Sem partes móveis
   - Maior eficiência e menor ruído

- Tecnologia Disruptiva e Potencial para Novas Aplicações:

   - Inovação no design e aplicação de reaction wheels
   - Potencial de adaptação para outras plataformas
# Metodologias
## Metodologias/procedimentos/técnicas
Até ao momento o grupo tem estado dividido entre dois componentes fundamentais do projeto, a montagem e testes do BLDC e do seu circuito de controlo, e a montagem, testes e investigação necessária para o desenvolvimento do prototipo do MHD contudo têm havido processos a correr em paralelo como a modelação 3D do chassis e a escrita do relatório.

### Montagem/testes do Motor (BLDC)
O processo de montagem do circuito de controlo do BLDC passou por soldar o circuito, cujo diagrama se encontra na imagem abaixo, constituído por um controlador de velocidade electrónico (U1), o próprio BLDC (M1), dois relés automóveis (K1, K2) (que permitem a inversão do sentido de rotação do BLDC, através da inversão da ordem das fases nas bobines do motor) e um MOSFET (Q1) que permite o accionamento simultâneo dos dois relés (que são operados a 12V) com uma voltagem de controlo de 5V.

![Diagrama Circuito de Controlo](Diagrama_circuito_controlador.png)

Quanto à testes, esta está a ser feita através da ligação do ESC e do MOSFET a um micro computador raspberry pi 4 e utilizando uma bateria S3 para alimentar o motor, a mesma que alimentará este na versão final do projeto, e dos relés através de uma fonte de alimentação externa, que será substituída por um boost converter alimentado pela mesma bateria S3 na versão final. Estamos neste momento a testar variações do código para tentar meter o motor a rodar e como tal não podemos fornecer ainda nem o código nem o diagrama de ligação ao raspberry pi.

### Montagem/testes do MHD
O MHD é constituído por dois ímanes de neodímio isolados com fita de poliamida orientados paralelamente, de tal modo a obter o campo magnético mais uniforme possível, estando estes separados por duas chapas de latão colocadas perpendicularmente aos ímanes, sendo estrutura toda suportada por mais fita de poliamida. Anteriormente foi usado fita isoladora em vez de fita de poliamida mas esta degradava-se na presença de um dos produtos resultantes da reação química que ocorre secundariamente ao funcionamento do MHD, a electrólise da água salgada, que liberta cloro e e hidróxido de sódio (embora em quantidades muito reduzidas comparativamente com o volume de água disponível).
No MHD as barras de latão servem como elétrodos que geram um campo elétrico, O funcionamento do MHD resulta da aplicação de uma força de Lorentz nos iões de sódio presentes na água, sendo esta igual ao produto externo entre a densidade de corrente e o campo magnético, sendo assim o MHD mais eficiente quando o campo elétrico encontra-se perpendicular ao campo magnético.
A testes do MHD passou pela submersão deste numa caixa cheia de água salgada à salinidade de \\(\approx 35g/L\\), a salinidade do oceano atlântico, e pela alimentação do MHD a partir de uma fonte de alimentação externa a 24V, observando a velocidade de saída de "bolhas" criadas pelos gases resultantes da electrólise que acontece paralelamente devido à presença de um campo elétrico. Esta medição de velocidade não foi rigorosa sendo apenas um indicador aproximado do funcionamento do MHD. No futuro, tencionamos colar o MHD a uma plataforma flutuante para avaliar o seu verdadeiro potencial enquanto método de propulsão.

### Modelação 3D
A nossa modelação 3D foi feita no blender e neste momento temos modelos para os pesos das reaction wheels e para o exterior do chassis do primeiro prototipo, que pode ser vistos nas imagens abaixo.

![Modelo Chassis](Chassis_modelo.png)

### Relatório e File Sharing
O nosso relatório foi feito em markdown e exportado para pdf e, tal como todos os nossos outros ficheiros e cronograma foi trabalhado e sincronizado entre membros da equipa utilizando o git com a plataforma de cloud hosting de git da microsoft "GitHub".

## Dificuldades Encontradas

- Dificuldade em soldar certas partes do circuito de controlo do MHD, devido a falta de prática recente pela pessoa a soldar.
- Curto circuito no MHD devido a mau isolamento dos ímanes em relação ás barras de cobre, problema que levou demasiado tempo a diagnosticar.
- Libertação de óxidos de latão solúveis em água, de cor verde, por parte do MHD, poderá ser resolvido através da utilização de um ânodo sacrificial no interior da embarcação.

## Materiais
### Presentemente em utilização

- 2 relés automóveis
- 1 ESC (electronic speed controller)
- 1 N-MOSFET
- 1 BLDC
- 1 Raspberry pi 4
- 2 Barras de latão
- Cabos Dupont
- Fita Kapton
- Fita Isoladora

## Cronograma de atividade atualizado
![cronograma](cronograma.png)

## Identificar o contributo individual de cada membro para o desenvolvimento do projeto
- João Ferreira
	- Montagem e soldagem do circuito de controlo do BLDC
	- Modelação 3D

- Luís Henriques
	- Montagem e testes do MHD, bem como investigação sobre como fazer o mesmo.
	- Diagramas de Circuito

- Pedro Tereno
	- Assistência na montagem do MHD e do circuito de controlo do BLDC quando necessária
	- Organização do relatório e da informação pertinente ao mesmo
# Resultados esperados
Esperamos até ao fim do período ter um sistema elétronico funcional numa breadboard com um motor, um MHD e um raspberry pi, tudo alimentado a partir de uma única bateria S3. Também procuramos ter um primeiro prototipo funcional no final de Janeiro.

O nosso objetivo final é um barco sem peças moveis no exterior que utilize reaction wheels para virar e estabilizar-se e um MHD como meio de propulsão.
# Agradecimentos
Queremos agradecer ao professor Pedro Jorge pela ajuda neste trabalho, disponibilizando espaço e materiais.
