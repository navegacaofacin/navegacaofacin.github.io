# Guia Site

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
Os campos pessoa e sala destinos são exclusivos e limpam o outro caso modificados.
O usuário é avisado caso um campo esteja em branco (posição atual ou as duas possibilidades de descrever o destino).

## Servidor

Vários servidores estão disponíveis dentro de diversos interpretadores.
O servidor do Ruby pode ser executado com o comando abaixo e mantém o site em <http://localhost:8888/>.

```Shell
cd DTA-FinalProject/src-site
ruby -run -e httpd . -p 8888
```