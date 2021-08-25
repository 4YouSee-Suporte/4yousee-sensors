<h1 align="center" >
    <img src="https://user-images.githubusercontent.com/63620799/130874258-c42b9165-e0b0-4f85-99dc-252e3ccae260.png">
</h1>
<h2 align="center">
Script em Python para execução de conteúdos 📺🟩 <br>
    <img alt="GitHub stars" src="https://img.shields.io/github/stars/4YouSee-Suporte/4yousee-sensors?style=social">
    <img alt="GitHub followers" src="https://img.shields.io/github/followers/4YouSee-Suporte?label=Follow%20me%20%3A%29&style=social">
</h2>

<h2>⚈ Acerca de 4YouSee Sensors</h2>
4YouSee Sensors é um programa que funciona em background e recebe comandos para execução arbitrária de conteúdos no 4YouSee Player.


<h2>⚈ Requisitos</h2>

- Conta em 4YouSee com ao menos uma licença ativa. Se não tiver, pode abrir uma conta de teste no link https://www.4yousee.com.br/register/.

- 4YouSee Player instalado. Para instalar você pode consultar a seguinte documentação: https://suporte.4yousee.com.br/kb/article/115233/.

- Uma vez instalado o 4YouSee Player, é necessário obter o token dele. Para obter o token você pode consultar na seguinte documentação: https://suporte.4yousee.com.br/kb/article/117490/

- Conteúdos na playlists do player em execução agendados ao futuro. Se tiver dúvidas, pode revisar essa documentação: https://suporte.4yousee.com.br/kb/article/115221/.

- Identificar o id dos conteúdos a serem exibidos. Veja na seguinte imagem o código do conteúdo é o `76`

<h1 align="center" >
    <img src="https://user-images.githubusercontent.com/63620799/130876922-3ee847cb-183f-47cd-ac0b-fccb823875fa.png">
</h1>


<h2>⚈ Como é o fluxo de funcionamento do 4YouSee Sensors</h2> 

1. O player se encontra online e exibindo conteúdos segundo sua playlist.

    1.1. ❗❗ Dentro da playlist deve estar o conteúdo que você quer que seja exibido após entrada do sinal. Esse conteúdo deve estar agendado ao futuro. Se são vários conteúdos, então todos eles devem estar agendados ao futuro.
  
2. É digitado um número existente no arquivo `txtCodPlayer.txt`. Ou seja, é recebida a sinal pelo teclado.

3. É executado o conteúdo equivalente ao número digitado segundo o arquivo `txtCodPlayer.txt`


<h2>⚈ Como instalar o 4YouSee Sensors</h2>

### 1. Baixar o codBar.py

Para instalar o 4yousee sensors devemos inicialmente baixar o arquivo codBar.py e abrir ele para que na linha 8 (colocar o token entre as aspas) podamos colocar o token obtido anteriormente. Enseguida você pode colocar ele na pasta onde se encontram os arquivos do player. A continuação indicamos donde se encontram as pastas em Windows e Linux:

Windows               | Linux
--------------------  | ------
C:\\.4yousee\Python27\ | ~\\.4yousee\

> No caso do windows, o python a utilizar é o python do próprio programa (4yousee player) mas no caso do linux será o python do sistema. Mas pode ficar tranquilo que só iremos instalar 2 libs.


### 2. Instalar libs

Para que o script funcione, precisa de duas libs externas: `requests` e `pynput`. São instaladas da seguinte forma:

#### Windows:

Dentro do command prompt você deve ir até a casta `C:\\.4yousee\Python27\` e escrever o seguinte comando:

> `python -m pip install pynput && python -m pip install pynput`


#### Linux:

Dentro da linha de comando digitar o seguinte:

> `python -m pip install pynput && python -m pip install pynput`

Se as libs foram instalada com sucesso, podemos inferir que o 4YouSee Sensors foi instalado!.


<h2>⚈ Como Configurar o 4YouSee Sensors</h2> 

Abrir o arquivo `txtCodPlayer.txt` ubicado na pasta do usuário (se não se encontra, você pode criar ele exatamente com esse nome: `txtCodPlayer.txt`) e dentro dele vão se encontrar os códigos e conteúdos referente a como você quer que sejam exibidos a partir da sinal de entrada. Exemplo:

```txtCodPlayer.txt
6;150 
11;49
10;4
```

O primeiro campo é a sinal esperada e o segundo é o conteúdo a executar após receber a sinal, divididos por um `;`. Então:

- No caso da primeira linha: `6;150`. Ao momento de digitar o `6` e dar um enter, vai ser executado o conteúdo de id `150`.

<h2>⚈ Como Executar o 4YouSee Sensors</h2> 

Para colocar o programa em funcionamento basta com executar o arquivo `codBar.py` que para o windows será com o Python do 4yousee player e para o caso do linux será com o Python do sistema. 

#### Windows:

Dentro do command prompt você deve ir até a casta `C:\\.4yousee\Python27\` e escrever o seguinte comando:

> `python codBar.py`

ou para funcioanr sem exibir a tela do command prompt

> `python codBar.py`


#### Linux:

Dentro da linha de comando digitar o seguinte:

> `python ~\.4yousee\codBar.py`


Pronto, agora se você digitar o número parametrizado no arquivo `txtCodPlayer.txt` vai ser executado o conteúdo referente ao número que você digitou. 


<h2>⚈ Como monitorar o comportamento o 4YouSee Sensors</h2> 

#### Windows:

Abrindo o `PowerShell` você deve digitar o seguinte para ver em tempo real o que está acontecendo com o programa:

> C:\Users\Alfonso> `Get-Content key_log.txt -Wait -Tail 30`

#### Linux:

Dentro da linha de comando digitar o seguinte:

> ~ $`tail key_log.txt`

Dessa forma você consegue saber se não foi executado um conteúdo ou se não foi reconhecida uma sinal do teclado ou outro possível erro.

> ❌ Atenção : O 4YouSee Sensors não reconhece as teclas vindas pelo teclado numérico.


