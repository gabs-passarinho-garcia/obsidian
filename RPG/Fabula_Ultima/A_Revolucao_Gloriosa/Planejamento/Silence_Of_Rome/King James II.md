---
nome: Rei Jaime II
nivel: 10
rank: Campeão (4)
especie: Humanoide
hp_max: 280
hp_atual: 280
mp_max: 120
mp_atual: 120
des: 8
int: 8
vig: 8
von: 8
defesa: 8
def_magica: 8
iniciativa: 12
tags:
  - monstro
  - fabula-ultima/revolucao-gloriosa
  - chefao
banner: Fabula_Ultima/assets/King_Jaime_art.png
banner_y: "25"
---
# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`  
**Traços:** Ambition, Power, Catholic, Absolutista, Manipulador[cite: 1].  
**Vilão Maior** (10 Pontos de Ultima)[cite: 1]

![[James_II_art.png]]

## 📊 Status Vital
**Pontos de Vida (PV)**
```meta-bind
INPUT[progressBar(maxValue(280)):hp_atual]
```
`VIEW[{hp_atual}]` / `VIEW[{hp_max}]` (Crise: `VIEW[round({hp_max}/2)]`) 
`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]` 

**Pontos de Magia (PM)**

```meta-bind
INPUT[progressBar(maxValue(120)):mp_atual]
```
`VIEW[{mp_atual}]` / `VIEW[{mp_max}]` 
`BUTTON[pm-5]` `BUTTON[pm-10]` `BUTTON[rest]`

## 🎲 Atributos
| DES | INT (AST) | VIG | VON |
|:---:|:---:|:---:|:---:|
| d`VIEW[{des}]` | d`VIEW[{int}]` | d`VIEW[{vig}]` | d`VIEW[{von}]` |

**Defesa:** `VIEW[{defesa}]` | **D. Mágica:** `VIEW[{def_magica}]` | **Iniciativa:** `VIEW[{iniciativa}]`

## ⚔️ Ataques Básicos
💥 **Royal Sceptre (Corpo a Corpo)**[cite: 1]
**Acerto (DES + AST + 1):** `dice: 1d{des} + 1d{int} + 1`
**Dano:** (HR + 5) Físico[cite: 1]
**Efeito:** Golpe de autoridade real. Se acertar, o alvo perde 5 PM adicionais.

## ⚡ Feitiços e Ações Únicas
☠️ **Maldição XL (Feitiço - 10 PM)**[cite: 1]
`BUTTON[pm-10]`  
**Acerto (AST + VON + 1):** `dice: 1d{int} + 1d{von} + 1`  
**Descrição:** Alvo: 1 criatura[cite: 1]. O alvo sofre as condições **Atordoado** e **Fraco** simultaneamente[cite: 1].

🌑 **Arma de Trevas (Feitiço - 10 PM)**[cite: 1]
`BUTTON[pm-10]`  
**Descrição:** Encanta a própria arma ou a de um aliado[cite: 1]. Até o fim da cena, todo o dano causado pela arma se torna do tipo **Trevas**[cite: 1]. Se conjurada na própria arma, realiza um ataque livre com ela como parte da ação[cite: 1].

🦇 **Umbra (Feitiço - 10 PM por alvo)**[cite: 1]
`BUTTON[pm-10]`  
**Acerto (AST + VON + 1):** `dice: 1d{int} + 1d{von} + 1`  
**Descrição:** Alvo: Até 3 criaturas[cite: 1]. Uma tempestade de sombras consome os alvos, causando (HR + 15) de dano de Trevas[cite: 1].

📜 **Ação Única: Édito Real (Ação de Suporte)**[cite: 1]
`BUTTON[habilidade-5]`  
**Descrição:** Jaime II impõe sua vontade absolutista. Realiza um teste oposto de 【AST + VON + 1】 contra o teste de 【VON + VON】 de todos os heróis. Heróis que falharem entram na condição **Lento** e não podem realizar Ações de Objetivo durante a próxima rodada.

## ⚙️ Regras Especiais & Crise
* **Ações Múltiplas:** Como Campeão (4), Jaime II age **4 vezes por rodada**[cite: 1]. Alterne seus turnos com os dos heróis.
* 👑 **Efeito de Crise (Deus Vult / Fúria Absolutista):** Quando seus PV caem para 140 ou menos (Crise), todas as magias de Trevas dele passam a causar +5 de dano adicional. Além disso, no final de cada um dos seus turnos, o ambiente fica denso de opressão: todos os heróis em Crise sofrem 5 de dano direto de Trevas (ignora Defesa).
* 🚨 **Ato Final (Prisão Real):** Quando reduzido a 0 PV (caso não fuja via Ponto de Ultima), ele invoca a Guarda Real para cobrir seu recuo. O Relógio *"Julgamento Sumário / Prisão"* avança instantaneamente 2 seções.

## 🛡️ Afinidades
**Vulnerável:** Nenhuma
**Resistente:** Nenhuma
**Imune:** Trevas 🌑, Gelo ❄️[cite: 1]

---
```meta-bind-button
label: Dano - 5
style: default
id: dano-5
hidden: true
actions:
  - type: updateMetadata
    bindTarget: hp_atual
    evaluate: true
    value: x - 5
```
```meta-bind-button
label: Dano - 10
style: default
id: dano-10
hidden: true
actions:
  - type: updateMetadata
    bindTarget: hp_atual
    evaluate: true
    value: x - 10
```
```meta-bind-button
label: Cura + 5
style: default
id: cura-5
hidden: true
actions:
  - type: updateMetadata
    bindTarget: hp_atual
    evaluate: true
    value: x + 5
```
```meta-bind-button
label: PM - 5
style: default
id: pm-5
hidden: true
actions:
  - type: updateMetadata
    bindTarget: mp_atual
    evaluate: true
    value: x - 5
```
```meta-bind-button
label: PM - 10
style: default
id: pm-10
hidden: true
actions:
  - type: updateMetadata
    bindTarget: mp_atual
    evaluate: true
    value: x - 10
```
```meta-bind-button
label: Descansar
style: default
id: rest
hidden: true
actions:
  - type: updateMetadata
    bindTarget: mp_atual
    evaluate: true
    value: x + 10
```
```meta-bind-button
label: Habilidade
style: default
id: habilidade-5
hidden: true
actions:
  - type: updateMetadata
    bindTarget: mp_atual
    evaluate: true
    value: x - 5
```