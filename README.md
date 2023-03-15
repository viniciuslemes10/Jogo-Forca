## Jogo da Forca:
  Este projeto foi desenvolvido em Python, que foi para simular o jogo da forca, ele contem o projeto principal que se chama jogo.py, nele você executa para jogar 
  o jogo. Também tem o arquivo palavras.txt, onde está todas as palavras que serão sorteadas por funções feitas em python para deixar o jogo mais dinâmico.
  
### Funções:

- Função **carrega_palavra_secreta():**<br><br>
  Está função vai abrir o arquivo palavras.txt com a função **open()** referenciando na variável arquivo, onde tem que passar o arquivo que deseja abrir e falar o
  que deseja fazer. Se deseja adicionar uma outra palavra você usa a letra "a", caso deseja ler deve-se usar a letra "r" e caso deseja escrever deve-se usar 
  a letra "w". Na nossa função vamos usar a letra "r" pois queremos ler nosso arquivo. Logo após criei um lista chamado **palavras[]**, depois usei um for para 
  que em cada linha que ele passar em arquivos, ele vai adicionar está linha na minha lista "palavras", sempre deve fechar o arquivo. A variável número está 
  recebendo uma palavra aleátoria vindo da minha lista, chamei a lista passando a variável numero como parametro, passando a palavra aleatoria toda maiúscula usei
  a função **upper()**. Retornando a palavra_secreta.
  
              def carrega_palavra_secreta():
                arquivo = open("palavras.txt", "r")
                palavras = []

                for linha in arquivo:
                    linha = linha.strip()
                    palavras.append(linha)

                arquivo.close()

                numero = random.randrange(0, len(palavras))
                palavra_secreta = palavras[numero].upper()
                return palavra_secreta
- Função **imprime_mensagem_abertura():**<br><br>
  Está função imprimi a mensagem bem-vindo, para dizer que o jogo começou.
  
      def imprime_mensagem_abertura():
        print("*********************************")
        print("***Bem vindo ao jogo da Forca!***")
        print("*********************************")
        
- Função **pede_chute():**<br><br>
  Uma vez que chamar está função ela vai ter um input lhe perguntando qual a letra, assim que informar qual letra você deseja colocar, ela retorna a letra informada.
  
      def pede_chute():
        chute = input("Qual letra? ")
        chute = chute.strip().upper()
        return chute
        
- Função **inicializa_letras_acertadas():**<br><br>
  Uma função onde ela tem como objetivo percorrer a lista do arquivo, a palavra que for escolhida ela irá colocar um [_] para simular o jogo da forca. Então se a palavra for uva, ela irá ficar assim ['_', '_', '_'].
  
      def inicializa_letras_acertadas(palavra):
        return ["_" for letra in palavra]
