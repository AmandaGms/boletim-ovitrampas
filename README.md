# Boletim Automatizado de Ovitrampas

Ferramenta desenvolvida em **R** e **R Markdown** para automatizar a geração de boletins de vigilância entomológica por ovitrampas a partir de dados exportados do aplicativo **Conta Ovos**.

O projeto utiliza arquivos **CSV** exportados pelo aplicativo, sendo outra alternativa para a utilização da API. A partir desses dados, a ferramenta calcula automaticamente indicadores, produz tabelas e gera um boletim em PDF, reduzindo significativamente o tempo necessário para elaboração dos relatórios periódicos.

O boletim permite acompanhar a **cobertura do monitoramento por ovitrampas no Distrito Federal**, avaliar o desempenho das Regiões Administrativas e verificar o cumprimento das metas estabelecidas no **Plano Distrital de Saúde do Distrito Federal 2024-2027**.

Embora tenha sido desenvolvido para o Distrito Federal, o código foi estruturado de forma que possa ser facilmente adaptado para outros estados ou municípios que utilizem ovitrampas na vigilância entomológica.

---

# Contexto

O monitoramento por ovitrampas é um importante componente da vigilância entomológica de Aedes aegypti. A elaboração manual de boletins e indicadores demanda tempo e está sujeita a erros. Esta ferramenta automatiza esse processo, permitindo a geração padronizada de relatórios que apoiam o monitoramento da cobertura das ovitrampas e o acompanhamento das metas do Plano Distrital de Saúde, contribuindo para a tomada de decisão pelos serviços de vigilância.

---

## Principais funcionalidades

- Importação automática dos arquivos CSV exportados pelo aplicativo Conta Ovos;
- Cálculo automático dos principais indicadores de vigilância entomológica;
- Monitoramento da cobertura de ovitrampas por Região Administrativa;
- Comparação dos indicadores com as metas estabelecidas pelo Plano Distrital de Saúde;
- Geração automática de tabelas e indicadores consolidados;
- Seleção do período de análise:
  - Mensal;
  - Quadrimestral;
  - Anual;
- Geração automática do boletim em PDF por meio do R Markdown.

---

## Estrutura do projeto

```
Boletim_ovitrampas.Rmd   -> script 
state-27-2026.csv -> banco de dados do ContaOvos
meta_nova.csv -> meta com quantidade de ovitrampas esperadas em cada município
README.md
```

---

## Pacotes utilizados

```r
tidyverse
kableExtra
janitor
stringi
```

---

## Como utilizar

### 1. Clone o repositório

```bash
git clone https://github.com/SEUUSUARIO/boletim-ovitrampas.git
```

### 2. Exporte os dados do aplicativo Conta Ovos

Exporte os dados em formato **CSV** e salve o arquivo na pasta do projeto.

### 3. Abra o arquivo

```
Boletim_ovitrampas.Rmd
```

### 4. Defina os parâmetros

Edite as variáveis conforme o período e a meta desejados:

```r
arquivo <- "state-27-2026.csv"

meta_ra <- read_csv2("meta_nova.csv")

Periodo_analise <- "Q1_2026"  # ESCOLHA O MÊS, QUADRIMESTRE, OU ANO DE ANÁLISE (exemplo: Julho->  "Julho_2025",  1º quadrimestre de 2025 -> "Q1_2025"; Para todo ano de 2025 ->  "Ano_2025")
```

### 5. Gere o boletim

Execute o arquivo utilizando **Knit** no RStudio.

Ao final será gerado automaticamente um relatório em PDF contendo indicadores, tabelas e análises da vigilância entomológica.

---

## Adaptação para outros estados

O código foi desenvolvido para o Distrito Federal, porém pode ser adaptado para qualquer estado ou município que utilize dados de ovitrampas exportados em formato CSV.

Para a adaptação, basta alterar os arquivos de entrada (dados e metas) e, quando necessário, os nomes das regiões monitoradas.


---

## Licença

Este projeto está licenciado sob a **MIT License**.

---

## Autora

**Amanda Gomes**

