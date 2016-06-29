# Navegação Facin

## Arquivos
- **index.html** contém a página inicial onde se decide qual método utilizar (sala como referência ou QRcode).
- **input.html** contém a página onde o usuário completa seu estado atual (sala ou entrada) e estado objetivo (sala ou pessoa).
- **path.html** contém a página que mostra o caminho que o usuário deve fazer através de fotos.
- **style.css** contém as configurações de cor e posicionamento dos elementos.
- **plans/** contém os planos pré-compilados em formato JSON, os argumentos de cada ação devem corresponder as fotos disponíveis.
- **images/** contém as fotos do ambiente.

Uma URL com informações é gerada ao clicar o botão **Ir** da página input.html no formato ``input.html?from=X&to=Y``, onde X e Y correspondem aos estados inicial e final do usuário.
Um plano deve existir com o nome ``X Y.json`` na pasta ``plans``, tais planos poderiam ser gerados sob demanda e armazenados ou gerados em lote de cada sala para outra.
Na lista de pessoas o ID das mesmas representa a sala onde elas estão, sendo assim os planos sempre são de um lugar para outro.
Os campos pessoa e sala destinos são exclusivos, quando um campo é alterado o outro volta ao valor default.
O usuário é avisado caso um campo esteja em branco (posição atual ou as duas possibilidades de descrever o destino).

O arquivo JSON segue o seguinte formato:

```JSON
[
  ["siga em frente", "r652 c45"],
  ["siga em frente", "c45 c46"],
  ["siga em frente", "c46 c29"],
  ["siga em frente", "c29 c20"],
  ["siga em frente", "c20 c19"],
  ["siga em frente", "c19 c23"],
  ["siga em frente", "c23 c24"],
  ["siga em frente", "c24 c25"],
  ["siga em frente", "c25 c26"],
  ["siga em frente", "c26 c27"],
  ["siga em frente", "c27 c28"],
  ["siga em frente", "c28 c47"],
  ["siga em frente", "c47 r623"]
]
```


## Servidor

Vários servidores estão disponíveis dentro de diversos interpretadores.
O servidor do Ruby pode ser executado com o comando abaixo e mantém o site em <http://localhost:8888/>.

```Shell
cd DTA-FinalProject/src-site
ruby -run -e httpd . -p 8888
```
