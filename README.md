# Máquina de Café em Java  

Simulação de uma máquina de café escrita em Java.

![Café.gif](https://www.mexidodeideias.com.br/wp-content/uploads/2016/05/dia-orgulho-geek.gif)

Desenvolvido para aplicar os estudos na linguagem, esse projeto é um desafio do [Movimento Codar](https://github.com/movimentocodar/iniciante-java-oo-2021), desenvolvido no Eclipse num período de dois dias e refatorado um tempo depois.

O objetivo desse código é simples: simular um sistema simples de uma **máquina de café** rodado pelo próprio terminal. Foi feito pensando em sua constante execução, como num sistema real, mas empilhando o mínimo de métodos possíveis sobre a stack.

## Funcionalidades

### Escolha de bebidas ☕

![Escolha de bebidas](https://cdn.discordapp.com/attachments/742936910019690607/893275561030475786/opcao-java.png)

Essa é a primeira interação do usuário com o sistema.

- É possível escolher entre _**5**_ bebidas, com três opções de preços. A água quente é gratuita e pula as etapas de verificação de pagamento.

- Escolher um número não listado lança uma **exception personalizada**, que é imediatamente tratada interrompendo o método atual da pilha e abrindo um novo, pedindo novamente a entrada do usuário. Esse processo se repete até que o usuário enfim coloque um número válido.

![exceptions.EscolhaErradaException: Você escolheu um número inválido(6). Escolha um número entre 0 e 5!](https://cdn.discordapp.com/attachments/742936910019690607/893281624450535444/exception.png)

- Escolher _**0**_ desliga o sistema, usando um `System.exit(0)`.

- A quantidade de água é exibida logo acima da escolha do usuário. Cada bebida gasta 50ml de água do repositório, que é constantemente atualizado na tela de escolha de bebidas. O repositório zerado impede o preparo de qualquer bebida, com uma exception que é imediatamente tratada, sem interromper a execução do programa.

![exceptions.FaltaAguaException: Não há água o suficiente para realizar operação. É necessário reabastecer.](https://cdn.discordapp.com/attachments/742936910019690607/893286000619569172/semagua.png)

### Processamento de Pedido 📋

- Ao escolher uma bebida que não seja água quente, o sistema pergunta se o usuário deseja escolher o nível de açúcar. O nível padrão são 3 colheres, que o usuário pode alterar, escolhendo de 0 a 5.

- O usuário pode escolher a forma de pagamento. Ao escolher dinheiro, deve inserir um valor que seja igual a qualquer cédula válida no Brasil em 2021. Ao escolher débito, há a liberdade para colocar como crédito o valor que preferir. Um valor menor que o preço da bebida escolhida resulta em outra exceção, indicando saldo induficiente, e o sistema volta à escolha de bebidas.

- Essa máquina de café não devolve troco. A cada transação é guardado o valor de "troco" como crédito, que desconta das próximas compras do usuário. Num sistema real, deveria ocorrer alguma forma de reconhecer os usuários e armazenar seus respectivos créditos, esse código simula isso.

![Forma de pagamento e armazenador de crédito](https://cdn.discordapp.com/attachments/742936910019690607/893291783113568276/2222.png)

### Preparo da bebida 🍵

- Para simular o processo de preparo da bebida, foi utilizado o `Thread.sleep(ms)` num método da classe abstrata **_Sistema Interno_**. Ele "pausa" o programa durante o tempo especificado (em _milisegundos_).

- É descrito o preparo de cada bebida com pausas entre cada etapa.

![Processo de preparo de um café.](https://cdn.discordapp.com/attachments/742936910019690607/893293527742693376/ssssss.png)

- No fim, é chamada novamente a tela de escolha de bebida. O processo se repete continuamente, encerrando os processos desnecessários para preservar a memória da stack. <h1/>

<div align=center>
  
  <h2>
    Tecnologias utilizadas <br>
    <a href="https://www.java.com/">
      <img alt="Java" width="60" height="60" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" />
    </a>
    <a href="https://www.eclipse.org/">
      <img alt="Eclipse IDE" height="40" src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d0/Eclipse-Luna-Logo.svg/1280px-Eclipse-Luna-Logo.svg.png" />
    </a>
  </h2>
</div>


<div align=center>
  <img src="https://cdn.discordapp.com/attachments/742936910019690607/893296064369668096/UEl2.gif"> <br>
  <strong>Obrigado por ler até aqui! 😄</strong>
</div>
