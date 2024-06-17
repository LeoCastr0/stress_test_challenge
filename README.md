# Stress test App

## Visão Geral
Esta aplicação em Go, chamada "stress-test", foi criada para executar testes de carga em serviços web. Ao especificar uma URL de destino, o número total de requisições e o grau de concorrência, ela simula tráfego no serviço, permitindo avaliar seu desempenho sob condições de estresse.


### Instalação
Clone ou baixe o repositório para sua máquina local.

```bash
git clone https://github.com/leocastr0/stress_test_challenge.git
```

### Acesse o diretório do projeto

```bash
cd stress_test_challenge
```

## Utilização
Na pasta dist há um executável para Linux. Navegue até essa pasta:

```bash
cd dist
```

### Comando Básico
A forma básica para executar o teste de stress é:


```bash
docker run leocastr0/stress_test_challenge [flags]
#ou
./stress-test [flags]
```

### Flags
- `-u, --url`:  URL do serviço a ser testado
- `-r, --requests`:  Número total de requisições a serem enviadas
- `-c, --concurrency`:  Número total de requisições a serem enviadas  (padrão 2).

### Exemplo
Para testar um serviço em http://example.com com 100 requisições e um nível de concorrência de 5, use:

```bash
docker run leocastr0/stress_test_challenge -u http://example.com -r 100 -c 5
# ou
./stress-test -u http://example.com -r 100 -c 5

# ou também

docker run leocastr0/stress_test_challenge --url http://example.com --requests 100 --concurrency 5
# ou
./stress-test --url http://example.com --requests 100 --concurrency 5
```

## Mais detalhes
### Como construir e executar localmente do zero

Na pasta raiz do projeto, execute:

```bash
go mod tidy
go build -o stress-test main.go
./stress-test [flags]

# ou

docker build -t <nome_imagem> .
docker run <nome_imagem> [flags]

```
