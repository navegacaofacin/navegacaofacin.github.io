# Guia Site

## Arquivos
- **index.html** cont�m a p�gina inicial onde se decide qual m�todo utilizar (sala como refer�ncia ou QRcode).
- **input.html** cont�m a p�gina onde o usu�rio completa seu estado atual (sala ou entrada) e estado objetivo (sala ou pessoa).
- **path.html** cont�m a p�gina que mostra o caminho que o usu�rio deve fazer atrav�s de fotos.
- **style.css** cont�m as configura��es de cor e posicionamento dos elementos.
- **plans/** cont�m os planos pr�-compilados em formato JSON, os argumentos de cada a��o devem corresponder as fotos dispon�veis.
- **images/** cont�m as fotos do ambiente.

Uma URL com informa��es � gerada ao clicar o bot�o **Ir** da p�gina input.html no formato ``input.html?from=X&to=Y``, onde X e Y correspondem aos estados inicial e final do usu�rio.
Um plano deve existir com o nome ``X Y.json`` na pasta ``plans``, tais planos poderiam ser gerados sob demanda e armazenados ou gerados em lote de cada sala para outra.
Na lista de pessoas o ID das mesmas representa a sala onde elas est�o, sendo assim os planos sempre s�o de um lugar para outro.
Os campos pessoa e sala destinos s�o exclusivos e limpam o outro caso modificados.
O usu�rio � avisado caso um campo esteja em branco (posi��o atual ou as duas possibilidades de descrever o destino).

## Servidor

V�rios servidores est�o dispon�veis dentro de diversos interpretadores.
O servidor do Ruby pode ser executado com o comando abaixo e mant�m o site em <http://localhost:8888/>.

```Shell
cd DTA-FinalProject/src-site
ruby -run -e httpd . -p 8888
```