# Criando um Programa de Acesso a Leitores em Ruby

## Introdução
Neste tutorial, vamos criar um programa simples em Ruby que permite aos leitores de uma biblioteca inserirem seus dados (nome, sobrenome e idade) e, em seguida, imprime essas informações em uma única frase. Vamos dividir o projeto em módulos para facilitar a organização e manutenção do código.

## Passo 1: Configuração do Ambiente
Antes de começarmos, certifique-se de ter o Ruby instalado em seu computador. Se você ainda não o tem, siga as instruções para [instalar o Ruby](https://rubyinstaller.org/downloads/) no Windows. Se estiver usando Linux ou MacOS, provavelmente já possui o Ruby instalado.

## Passo 2: Criando o Projeto
Vamos criar um diretório para o nosso projeto. Abra o terminal e execute os seguintes comandos:

```bash
mkdir biblioteca
cd biblioteca
touch main.rb
```

O arquivo `main.rb` será nosso ponto de entrada para o programa.

## Passo 3: Escrevendo o Código
Agora, abra o arquivo `main.rb` em um editor de texto ou IDE Ruby. Vamos começar definindo os módulos e as funções necessárias.

### Módulo `Leitor`
```ruby
# main.rb

module Leitor
  def self.obter_dados
    print "Digite seu nome: "
    nome = gets.chomp

    print "Digite seu sobrenome: "
    sobrenome = gets.chomp

    print "Digite sua idade: "
    idade = gets.chomp.to_i

    { nome: nome, sobrenome: sobrenome, idade: idade }
  end

  def self.imprimir_dados(leitor)
    puts "Bem-vindo(a), #{leitor[:nome]} #{leitor[:sobrenome]}! Você tem #{leitor[:idade]} anos."
  end
end
```

### Módulo `Main`
```ruby
# main.rb

module Main
  def self.run
    leitor = Leitor.obter_dados
    Leitor.imprimir_dados(leitor)
  end
end

Main.run if __FILE__ == $PROGRAM_NAME
```

## Passo 4: Executando o Programa
No terminal, navegue até o diretório do projeto e execute:

```bash
ruby main.rb
```

Digite seu nome, sobrenome e idade quando solicitado. O programa imprimirá uma mensagem de boas-vindas com os dados fornecidos.

## Conclusão
Parabéns! Você criou seu primeiro projeto em Ruby. Agora você pode expandir esse programa, adicionar mais funcionalidades e explorar outros conceitos da linguagem. Divirta-se programando!

```ruby
# Exemplo de execução:
# Digite seu nome: Maria
# Digite seu sobrenome: Silva
# Digite sua idade: 30
# Bem-vindo(a), Maria Silva! Você tem 30 anos.
```
