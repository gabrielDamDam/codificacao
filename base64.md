**Base64** é um método de codificação que transforma dados binários (como arquivos, imagens ou qualquer outro tipo de dado) em uma representação textual. Ele é muito utilizado para transmitir dados de forma segura através de meios que são projetados para lidar com texto, como emails ou URLs.

A codificação Base64 utiliza um conjunto de 64 caracteres diferentes (daí o nome Base64) que inclui:

- Letras maiúsculas (A-Z)
- Letras minúsculas (a-z)
- Dígitos (0-9)
- Dois símbolos adicionais (+ e /)

### Como funciona a codificação Base64?

1. **Conversão em Bits**: Primeiramente, os dados binários são convertidos em uma sequência de bits (0s e 1s).
    
2. **Agrupamento em Blocos de 6 Bits**: Em vez de usar os 8 bits tradicionais de um byte, a codificação Base64 agrupa os dados em blocos de 6 bits. Isso porque 6 bits podem representar 64 valores diferentes (2^6 = 64).
    
3. **Mapeamento de Caracteres**: Cada bloco de 6 bits é mapeado para um dos 64 caracteres do conjunto Base64.
    
4. **Preenchimento (Padding)**: Se a quantidade de bits não for múltipla de 6, a codificação Base64 adiciona caracteres de preenchimento (`=`) ao final para completar o bloco.

### Exemplo de Codificação Base64

Vamos pegar a palavra "Man" como exemplo:

1. **Texto Original**: "Man"
    
2. **Representação Binária**:
    
    - M = 01001101
    - a = 01100001
    - n = 01101110
    
    Juntando tudo: 01001101 01100001 01101110
    
3. **Agrupando em Blocos de 6 Bits**:
    
    - 010011
    - 010110
    - 000101
    - 101110
4. **Mapeamento Base64**:
    
    - 010011 = T
    - 010110 = W
    - 000101 = F
    - 101110 = u
    
    Resultado Base64: `TWFu`


### Comando `base64` no Linux

No Linux, o comando `base64` é usado para codificar e decodificar dados utilizando a codificação Base64. Ele é bastante simples de usar:

- **Codificar um arquivo para Base64**:
    
    `base64 arquivo.txt`
    
    Isso vai exibir o conteúdo do `arquivo.txt` codificado em Base64.
    
- **Decodificar um arquivo codificado em Base64**:

    `base64 -d arquivo_base64.txt`
    
Isso vai decodificar o conteúdo do `arquivo_base64.txt` de volta para o formato original.
    
- **Codificar uma string para Base64**:

    `echo -n "Hello World" | base64`
    
    A opção `-n` no `echo` é para não adicionar uma nova linha no final da string.
    
- **Decodificar uma string codificada em Base64**:

    `echo "SGVsbG8gV29ybGQ=" | base64 -d`

