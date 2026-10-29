# Respira, Jé

Um "boletim do tempo" do bolso: uma página única, em linguagem simples, para colocar em
contexto a queda da bolsa depois do segundo turno de 25 de outubro de 2026.

Publicado em <https://guilupino.github.io/respira-je/>

---

## Para que serve

Na segunda-feira, 26/10/2026, o Ibovespa caiu 13,88% e acionou o circuit breaker, e os
bancos começaram a subir os juros do financiamento imobiliário. A página foi feita para
uma amiga que estava ouvindo só notícia ruim, e usa uma ideia simples: **tempo** é o
pânico de hoje, **clima** é a tendência de décadas.

O conteúdo tenta ser independente de lado político. Ele mostra presidentes de todos os
partidos com o mesmo critério e inclui uma seção sobre o que o mercado tem razão de
acompanhar.

## O que tem na página

- **A previsão de hoje.** O que aconteceu em 26/10 e 27/10, e o Ibovespa no acumulado de 2026.
- **O clima.** Gráfico do Ibovespa de 1994 a 2026 com as nove eleições marcadas, em escala
  logarítmica ou linear, e uma tabela com a variação em cada mandato.
- **A ressaca pós-eleição.** Primeiro pregão e primeira semana depois de cada segundo
  turno, de 2002 a 2026.
- **Máquina do tempo do pânico.** Quanto R$ 1.000 investidos no fim de cada ano de
  eleição valeriam hoje.
- **Cesta.** Simulador de carteira (ações, dólar e renda fixa) mostrando o resultado
  de cada combinação no dia 26/10.
- **Juros do financiamento.** O que mudou, por quê, e o paralelo com 2002.
- **Como os profissionais pensam.** A carteira All Weather de Ray Dalio e citações de
  Buffett, Dalio e Peter Lynch.
- **Respira.** Um exercício de respiração guiada de 30 segundos.

## Dados e fontes

Todos os números foram coletados em 28/10/2026. Valores do Ibovespa são nominais (sem
descontar inflação). A lista completa de fontes está no rodapé da página:

- Fechamentos anuais do Ibovespa: Macrotrends (1994 a 2022), B3 (2023), Bloomberg Línea
  (2024) e InfoMoney (2025)
- Mercado em 26 e 27/10/2026: InfoMoney e CNN Brasil
- Reação pós-eleição de 2002 a 2022: Elos Ayta, via TNH1
- Juros do financiamento: Investidor10, citando a MySide
- Selic: decisão do Copom de 16/09/2026
- Desemprego: IBGE, via DGABC

> Material informativo, não é recomendação de investimento.

---

## Estrutura do repositório

```
.
└── index.html    # página completa: HTML, CSS, dados e JavaScript num arquivo só
```

A única dependência externa é carregada por CDN: [Chart.js 4.4.1](https://www.chartjs.org/)
(gráficos), além das fontes do Google Fonts (Bricolage Grotesque, Atkinson Hyperlegible
e IBM Plex Mono).

## Como editar

Abra o `index.html` em qualquer editor. Os dados ficam no bloco `<script>` no fim do arquivo:

- `closes`: fechamento anual do Ibovespa por ano
- `NOW` e `PRE`: pontos atuais e da véspera da eleição
- `terms`: os mandatos da tabela
- `rData`: reação no primeiro pregão e na primeira semana de cada eleição
- `R`: variação de cada ativo no dia 26/10, usada no simulador da cesta

Para atualizar `NOW` com um novo fechamento, mude o número. O gráfico, a tabela e a
máquina do tempo são recalculados a partir dele. Os textos fixos não mudam sozinhos:
ajuste à mão a data "27/10/2026" e os números dos cartões do topo (como o "+9%" do ano).

## Publicação

O site é servido pelo GitHub Pages a partir da raiz da branch `main`. Qualquer push que
altere o `index.html` publica a nova versão em um ou dois minutos.
