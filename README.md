# Painel do Dr. Danilo Alencar

Painel interativo dos votos para deputado estadual no Tocantins, comparando o 1º turno de 2022 e 2026 por município e local de votação.

## Acessar

- Painel publicado via GitHub Pages: https://rogernogueira.github.io/painel-dr-danilo/
- Abra `dados/paineis/dr-danilo/painel-local.html` para a versão autocontida.
- Para a versão em arquivos, sirva `dados/paineis/dr-danilo/` por HTTP; não abra `index.html` diretamente via `file://`.

O painel usa DuckDB-WASM e Leaflet; o navegador precisa de acesso à internet para carregar os módulos do DuckDB distribuídos pelo jsDelivr.

## Dados

- Candidato: Dr. Danilo Alencar (`DR DANILO ALENCAR`), deputado estadual.
- Fontes: Boletins de Urna do 1º turno de 2022 e 2026 (TSE), cadastro de locais de votação e malha municipal do IBGE; coordenadas complementares podem vir do OpenStreetMap.
- A unidade de comparação dos votos é o local de votação associado por município e número do local. O nome/endereço do local pode mudar entre eleições; consulte a indicação “mesmo prédio” e a fonte da coordenada.
- O painel mostra votos nominais e participação sobre os votos válidos. A comparação entre anos não controla por mudança de eleitorado, candidatura, partido ou contexto eleitoral.
- Proveniência, dicionário e checksums estão em `dados/paineis/dr-danilo/metadata/`.

## Números estaduais no pacote

- 2022: 7.937 votos
- 2026: 22.997 votos

São totais registrados no pacote dos BUs usado pelo painel; não devem ser interpretados isoladamente como medida de apoio relativo. O painel também permite comparar a participação percentual sobre votos válidos.

## Desenvolvimento

Requisitos: Node.js e npm. O pacote de dados já está incluído neste repositório.

```bash
cd painel
npm ci
npm run build
```

O build lê o pacote `dados/paineis/dr-danilo/` e atualiza os arquivos servidos e `painel-local.html` nesse diretório.
