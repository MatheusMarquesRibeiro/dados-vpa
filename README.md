# Dados abertos — Visões, preocupações e ações sobre a Química

Este repositório reúne os dados e os instrumentos de coleta associados ao manuscrito:

> **Visões, preocupações e ações sobre a Química: elaboração de instrumentos e síntese inicial das opiniões dos estudantes**

O estudo investiga como estudantes do Ensino Médio compreendem a presença da Química no cotidiano, avaliam o ensino de Química e de Ciências da Natureza, manifestam preocupações sobre questões sociais, científicas, tecnológicas e ambientais e relatam ações ou atitudes relacionadas à vida em sociedade.

## Autores

- Raniele Aparecida da Silva
- Matheus Marques Ribeiro
- Maria Eunice Ribeiro Marcondes

## Conteúdo do repositório

| Arquivo | Descrição |
|---|---|
| `Base de Dados MG.csv` | Base analítica de Minas Gerais, com respostas de 97 estudantes e 46 variáveis. Contém itens harmonizados sobre visões acerca da Química, conteúdos escolares, aulas de Química e relações entre Ciências da Natureza e outras áreas, além de variáveis de identificação do grupo e sexo. |
| `Dados SP N200.csv` | Base de São Paulo, mantida em sua estrutura original, com respostas de 200 estudantes e 181 variáveis. Inclui visões acerca da Química, preocupações sociais, ambientais, científicas e tecnológicas, temáticas de interesse, práticas de busca de informação, ações e atitudes e informações sociodemográficas. |
| `Inquérito sobre as visões, preocupações e ações - MG.pdf` | Instrumentos utilizados na pesquisa realizada em Minas Gerais. |
| `Inquérito sobre as visões, preocupações e ações - SP.pdf` | Instrumento utilizado na pesquisa realizada em São Paulo. |
| `LICENSE` | Licença aplicável ao conteúdo do repositório. |

## Características dos conjuntos de dados

Os dados foram obtidos em duas investigações independentes. Por esse motivo, os instrumentos, a quantidade de itens e algumas formas de redação ou organização das questões não são idênticos. Comparações entre as amostras devem considerar essas diferenças metodológicas.

### Minas Gerais

- **Participantes:** 97 estudantes;
- **Número de variáveis:** 46;
- **Formato de origem:** arquivo do IBM SPSS Statistics (`.sav`), posteriormente convertido para CSV;
- **Estrutura da base:** 43 itens de opinião e 3 variáveis auxiliares;
- **Principais dimensões:** presença da Química no cotidiano, percepção dos conteúdos escolares, avaliação das aulas de Química e relações entre Ciências da Natureza e outras áreas.

A base de Minas Gerais disponibilizada em CSV corresponde à **base analítica harmonizada** empregada nas comparações do estudo. Ela não reproduz todas as questões presentes no instrumento completo em PDF.

#### Organização das variáveis de Minas Gerais

| Variáveis | Conteúdo |
|---|---|
| `I.1` a `I.12` | Visões sobre a presença e as contribuições da Química no cotidiano e na sociedade. |
| `II.1` a `II.11` | Percepções sobre a aprendizagem e os conteúdos de Química ensinados na escola. |
| `III.1` a `III.16` | Percepções sobre as aulas de Química e suas contribuições formativas. |
| `IV.1` a `IV.4` | Relações entre Ciências da Natureza, Ciências Humanas, Português e Matemática. |
| `V` | Unidade amostral: `1 = São Paulo` e `2 = Minas Gerais`. Nesta base, todos os registros apresentam o código `2`. |
| `VI` | Sexo: `1 = Masculino` e `2 = Feminino`. |
| `VII` | Combinação entre unidade amostral e sexo: `1 = SP–Masculino`, `2 = SP–Feminino`, `3 = MG–Masculino` e `4 = MG–Feminino`. Nesta base, aparecem apenas os códigos `3` e `4`. |

Os 43 itens das seções I a IV utilizam os seguintes códigos:

| Código | Resposta |
|---:|---|
| 1 | Discordo totalmente |
| 2 | Discordo parcialmente |
| 3 | Concordo parcialmente |
| 4 | Concordo totalmente |
| 9 | Não sei |

### São Paulo

- **Participantes:** 200 estudantes;
- **Número de variáveis:** 181;
- **Principais dimensões:** visões sobre a Química, percepção do ensino de Ciências da Natureza, grau de preocupação com 60 situações sociais, ambientais, científicas e tecnológicas, interesse por temáticas para as aulas de Química, práticas de busca de informação, ações e atitudes e características sociodemográficas.

A base de São Paulo foi mantida sem alterações em relação ao arquivo utilizado na pesquisa.

## Formato dos arquivos

Os dados são disponibilizados em formato CSV:

- codificação de caracteres: **UTF-8 com BOM**;
- separador de colunas: **ponto e vírgula (`;`)**;
- células vazias representam respostas ausentes ou não registradas;
- números decimais, quando existentes, utilizam ponto como separador decimal.

O formato CSV preserva os nomes das colunas e os valores registrados, mas não incorpora automaticamente os rótulos de variáveis e de valores existentes no arquivo original do SPSS. Por isso, a interpretação deve ser feita com apoio deste README e dos instrumentos em PDF.

### Leitura em Python

```python
import pandas as pd

dados_mg = pd.read_csv(
    "Base de Dados MG.csv",
    sep=";",
    encoding="utf-8-sig"
)

dados_sp = pd.read_csv(
    "Dados SP N200.csv",
    sep=";",
    encoding="utf-8-sig"
)
```

### Leitura em R

```r
dados_mg <- read.csv2(
  "Base de Dados MG.csv",
  fileEncoding = "UTF-8-BOM"
)

dados_sp <- read.csv2(
  "Dados SP N200.csv",
  fileEncoding = "UTF-8-BOM"
)
```

## Escalas de resposta na base de São Paulo

As correspondências entre os códigos numéricos, as alternativas e os enunciados devem ser consultadas no instrumento de São Paulo.

De modo geral, foram utilizadas as seguintes escalas:

- concordância: **Discordo totalmente, Discordo parcialmente, Concordo parcialmente e Concordo totalmente**;
- preocupação ou interesse: escala de **1 a 5**;
- frequência das ações: **Nunca, Raramente, Às vezes, Muitas vezes e Sempre**;
- alternativa adicional: **Não sei**, quando prevista no instrumento.

## Identificação das variáveis

Os nomes das colunas seguem a numeração das seções, questões e itens dos respectivos instrumentos.

Na base de Minas Gerais, por exemplo:

- `I.1`: seção I, item 1;
- `II.4`: seção II, item 4;
- `III.10`: seção III, item 10;
- `IV.2`: seção IV, item 2.

Na base de São Paulo, por exemplo:

- `I.1.1`: seção I, questão 1, item 1;
- `II.1.15`: seção II, questão 1, item 15;
- `III.3.10`: seção III, questão 3, item 10;
- `IV.1`: seção IV, questão 1.

Para interpretar o enunciado de cada variável, consulte o instrumento em PDF correspondente.

## Observação sobre a conversão da base de Minas Gerais

O arquivo `Base de Dados MG.csv` foi gerado diretamente a partir da base original em formato SPSS. A conversão eliminou o problema de cabeçalho observado em uma versão anterior do CSV, na qual uma coluna aparecia como `V.1` entre `V.18` e `V.20`.

A nova base, porém, não é apenas uma correção daquele cabeçalho: ela corresponde a uma base analítica reduzida e harmonizada, com 46 variáveis, e não contém a sequência de itens `V.1` a `V.20`.

## Ética, privacidade e uso responsável

Os arquivos CSV não incluem campos de nome ou escola. Ainda assim, respostas abertas e combinações de características sociodemográficas devem ser tratadas com cautela para evitar tentativas de identificação indireta dos participantes.

Os dados devem ser utilizados exclusivamente para finalidades acadêmicas, educacionais ou científicas compatíveis com os princípios de ética em pesquisa. Não devem ser empregados para identificar, classificar individualmente ou produzir qualquer prejuízo aos participantes, às escolas ou às comunidades envolvidas.

## Como citar

Enquanto o artigo e o conjunto de dados não possuírem DOI, sugere-se a seguinte referência provisória:

> SILVA, Raniele Aparecida da; RIBEIRO, Matheus Marques; MARCONDES, Maria Eunice Ribeiro. **Dados e instrumentos da pesquisa “Visões, preocupações e ações sobre a Química”**. GitHub, 2026. Disponível em: `https://github.com/MatheusMarquesRibeiro/academicdata`.

Após a publicação do artigo ou o arquivamento de uma versão do repositório em plataforma com DOI, esta seção deverá ser atualizada.

Ao utilizar os dados, cite também o artigo correspondente.

## Licença

O repositório está disponibilizado sob a licença **CC0 1.0 Universal**, conforme o arquivo [`LICENSE`](./LICENSE).

Embora a licença permita ampla reutilização, solicita-se a citação dos autores e da fonte como prática de integridade e reconhecimento acadêmico.

## Contato

**Matheus Marques Ribeiro**  
E-mail: [ribeiro.m.marques@gmail.com](mailto:ribeiro.m.marques@gmail.com)

Dúvidas sobre o conjunto de dados, os instrumentos ou as condições de reutilização podem ser encaminhadas ao contato acima.
