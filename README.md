# Simulador de Autômatos Finitos

## Descrição
Este programa é um simulador de autômatos finitos que pode processar autômatos determinísticos, não determinísticos e não determinísticos com transições vazias. Ele permite que você defina o autômato via um arquivo JSON e teste diversas entradas para verificar se são aceitas ou rejeitadas.

## Funcionamento
O simulador recebe dois arquivos de entrada: um arquivo JSON que descreve o autômato e um arquivo CSV contendo as entradas de teste. Ele então executa o autômato para cada entrada e registra se cada uma é aceita ou rejeitada, juntamente com o tempo de execução. Os resultados são armazenados em um arquivo de saída.

## Exemplo de Uso
Para utilizar o simulador, forneça dois arquivos de entrada: um arquivo JSON com a definição do autômato e um arquivo CSV com as entradas a serem testadas. Especifique também um terceiro arquivo onde os resultados da simulação serão armazenados.

### Exemplo de arquivo de autômato:
`arquivo_do_automato.aut`

{
    "initial": 0,
    "final": [3, 5],
    "transitions": [
        {"from": 0, "read": "a", "to": 1},
        {"from": 0, "read": " ", "to": 2},
        {"from": 1, "read": "b", "to": 3},
        {"from": 2, "read": "c", "to": 3},
        {"from": 2, "read": " ", "to": 4},
        {"from": 3, "read": "a", "to": 5},
        {"from": 4, "read": "b", "to": 5},
        {"from": 5, "read": " ", "to": 0}
    ]
}
### Exemplo de arquivo de entradas:
`arquivo_de_testes.in`

aba  c;1
abc;0
a b a;0
Neste arquivo, cada linha contém uma entrada de teste e a saída esperada, separados por ";" (1 para aceita, 0 para rejeita).

### Exemplo de uso no terminal:
`python ferramenta.py arquivo_do_automato.aut arquivo_de_testes.in arquivo_de_saida.out`

### Exemplo de arquivo de saída:
`arquivo_de_saida.out`

aba  c;1;1;0.028
abc;0;0;0.003
a b a;0;0;0.003
O arquivo de saída registra a entrada, a saída esperada, a saída obtida e o tempo de execução, separados por ";".

##  Considerações
Certifique-se de que os arquivos de entrada estejam no formato correto e utilize a linha de comando para executar o script. Se estiver usando um terminal diferente, adapte os comandos conforme necessário para visualizar os resultados.





