# Smart Park - Gerador de QR Code PIX

Este projeto é uma aplicação Flask que gera QR Codes para pagamentos via PIX. Os QR Codes são gerados dinamicamente com base nas informações fornecidas pelo usuário e podem ser usados para facilitar pagamentos em estabelecimentos.

## Funcionalidades

- Geração de QR Code com informações específicas (valor da transação, ID do usuário).
- Cálculo do código CRC16 para validação do payload do QR Code.
- Armazenamento dos QR Codes gerados em um diretório específico.
- Exibição do QR Code gerado em uma página web.

## Pré-requisitos

Antes de começar, certifique-se de que você tem o seguinte instalado:

- Python 3.x
- Pip (gerenciador de pacotes Python)

## Instalação

1. Navegue até o diretório do projeto:

```bash
cd Prot-tipo-Gerador-de-QrCode-Pix
```

Instale as dependências necessárias. Você pode usar os seguintes comandos bash para instalar as bibliotecas:

```bash
pip install Flask
pip install qrcode
pip install crcmod
```

Ou, para uma instalação mais rápida, crie um arquivo `install.sh` com o seguinte conteúdo:

```bash
#!/bin/bash
pip install Flask qrcode crcmod
```

Em seguida, execute o arquivo:

```bash
bash install.sh
```

**Nota:** Você pode precisar criar um arquivo `requirements.txt` com as bibliotecas necessárias, como `Flask`, `qrcode`, e `crcmod`.


## Uso

Inicie a aplicação Flask:

```bash
python app.py
```

O servidor será iniciado no endereço `http://127.0.0.1:5000/`.

Para gerar um QR Code, faça uma requisição POST para o endpoint `/gerar_qrcode` com um JSON contendo o valor e o ID do usuário. Exemplo:

```bash
curl -X POST http://127.0.0.1:5000/gerar_qrcode -H "Content-Type: application/json" -d '{"valor": "15.00", "id_usuario": "12345"}'
```

A resposta incluirá o payload e a URL do QR Code gerado.

Para exibir o QR Code gerado, você pode acessar a URL correspondente:

```http
http://127.0.0.1:5000/exibir_qrcode/nome_do_arquivo.png
```

Substitua `nome_do_arquivo.png` pelo nome do arquivo retornado na resposta.

   
