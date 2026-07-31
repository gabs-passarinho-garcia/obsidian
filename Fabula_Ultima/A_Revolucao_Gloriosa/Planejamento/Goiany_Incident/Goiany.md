---
tags:
  - campanha/fabula-ultima
  - status/producao
  - tipo/local
  - tema/realismo-poetico
  - fabula-ultima/goiany-incident
tipo: Local
sistema: Fabula Ultima
regiao: "[[Vila de Goiany]]"
nome_original: "Goiany"
nivel_perigo: "Moderado a Crítico (Radiação)"
---

# 🏘️ Vila de Goiany (Cornualha)

> *"A terra aqui é humilde e o trigo é pouco, forasteiro. Mas quando a noite cai e as paredes começam a brilhar com a luz dos anjos, nós não sabemos se devemos rezar ou correr."* — Morador de Goiany

![[Goiany_art.png]]

## 🌑 A Atmosfera Visceral
Localizada no extremo sudoeste da Inglaterra, nas colinas acidentadas da Cornualha, a Vila de Goiany sempre viveu do trabalho duro em suas minas de chumbo e ferro. Tudo mudou quando mineradores violaram um recipiente sepultado por [[Robert Hooke]] e espalharam uma poeira que brilha em tom purpúreo-azul no escuro: o **Césio-137**.

Sob a luz do sol, Goiany parece uma vila bucólica ordinária, embora com uma calma inquietante e uma clínica improvisada lotada de doentes. Quando o sol se põe, o horror se revela: paredes de enxaimel, roupas penduradas no varal, poços de água e até os rostos de crianças pequenas emitem um brilho espectral constante. O ar tem gosto de ferro queimado e ozônio, e a população, sem entender a ciência por trás da radiação, divide-se entre a superstição religiosa e a negação desesperada.

---

## 📍 Pontos de Interesse (Os Focos da Praga)

### 🏥 A Enfermaria Comunitária & O Gazofilácio
A capela e o posto médico da vila estão apinhados de mineradores e seus familiares sofrendo de náuseas graves, queimaduras que não cicatrizam e queda de cabelo.
* **A Visão:** O Pároco local tenta confortar os doentes com orações no Gazofilácio, ignorando que o próprio altar foi contaminado por moedas e tecidos trazidos por fiéis infectados.
* **Mecânica de Interação:** Entrar no local sem proteção de chumbo exige teste de 【VON + VON】 (Dif 10) para suportar a vertigem radiológica. Permanecer 1 cena investigando avança **+1 segmento na Dosimetria do grupo**.

### 🏡 A Casa dos Mineradores (O Berço do Contágio)
A humilde residência onde a cápsula de chumbo desenterrada na mina foi aberta.
* **A Visão:** O local de maior contaminação na vila. O pó purpúreo impregnou os móveis, as louças e o alimento da família. A pequena [[Lady]] ingeriu o material em sua refeição e repousa em estado crítico no quarto dos fundos.
* **Mecânica de Busca:** Investigar a casa exige cuidado extremo. O manuseio de objetos sem luvas pesadas de chumbo inflige **+2 segmentos diretos no Relógio de Dosimetria**.

### 🧪 A Cabana nas Colinas (O Laboratório de Madame Curie)
Uma estrutura isolada no topo das colinas que cercam a vila, repleta de retortas, alambiques e equipamentos de medição alquímica.
* **A Visão:** [[Madame Curie]] trabalha incansavelmente medindo amostras de minerais trazidas da mina. O local cheira a reagentes e ervas medicinais.
* **Mecânica de Apoio:** [[Madame Curie]] fornece aos heróis as receitas do **Azul da Prússia** e orienta sobre a confecção de amuleto/detector Geiger (consumindo 3 segmentos dos relógios). *Nota: Devido às amostras acumuladas, a casa possui exposição radiológica dobrada!*

### ⛏️ A Mina Abandonada de Goiany
O epicentro do acidente. Foi de onde [[Robert Hooke]] extraiu o Césio para o [[Motor Ascendente]] e onde sepultou a sobra instável.
* **A Visão:** Trilhos ferrugentos entram na escuridão. O interior brilha como uma caverna de cristais pálidos, habitada pelo mutado [[Dogzilla]].
* **Mecânica:** Contém vigas de chumbo necessárias para o *Relógio de Contenção*.

---

## 🎲 Encontros e Rumores (1d8)

| 🎲 | Rumor / Evento de Ruas | A Cena (Narrativa) |
| --- | --- | --- |
| 1 | **Enfermaria Lotada** | Pessoas vomitando e apresentando feridas purpúreas nos braços. |
| 2 | **Brilho Noturno** | Moradores admirando panos e quinquilharias que "brilham no escuro". |
| 3 | **Tragédia Silenciosa** | A pequena [[Lady]] brincando com pó azul e comendo com as mãos sujas. |
| 4 | **Surto Supersticioso** | Habituais rejeitando conselhos médicos e acusando a Guilda Galesa de feitiçaria. |
| 5 | **O Cão Mutante** | Cão da família visto correndo para as minas com um brilho intenso no peito. |
| 6 | **A Alquimista Excêntrica** | Boatos sobre [[Madame Curie]] medir as pedras da mina com um bastão metálico. |
| 7 | **Fogo Santo no Altar** | O Pároco tentando acalmar o povo no Gazofilácio contaminado. |
| 8 | **Uivo do Abismo** | Rugidos ecoando das profundezas das minas abandonadas à meia-noite. |

---

## 🗣️ Habituais e Visitantes (Banco de Dados de NPCs)

```dataview
TABLE tipo, status, localização
FROM #npc AND #fabula-ultima/goiany-incident
SORT file.name ASC
```