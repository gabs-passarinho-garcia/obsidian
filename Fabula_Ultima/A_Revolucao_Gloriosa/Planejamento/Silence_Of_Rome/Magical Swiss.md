---
nome: Magical Swiss
nivel: 10
rank: Soldado
especie: Humanoide
hp_max: 50
hp_atual: 50
mp_max: 70
mp_atual: 70
des: 8
int: 8
vig: 6
von: 10
defesa: 9
def_magica: 10
iniciativa: 8
tags:
  - monstro
  - fabula-ultima/revolucao-gloriosa
  - guarda-suico
banner: Fabula_Ultima/assets/Magical_Swiss_art.png
banner_y: "25"
---
# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`
![[Swiss_guard_magical_art.png]]

## 📊 Status Vital
**Pontos de Vida (PV)**
```meta-bind
INPUT[progressBar(maxValue(50)):hp_atual]
```
`VIEW[{hp_atual}]` / `VIEW[{hp_max}]` (Crise: `VIEW[round({hp_max}/2)]`) 
`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]` 

**Pontos de Magia (PM)**

```meta-bind
INPUT[progressBar(maxValue(70)):mp_atual]
```
`VIEW[{mp_atual}]` / `VIEW[{mp_max}]` 
`BUTTON[pm-5]` `BUTTON[pm-10]` `BUTTON[rest]`

## 🎲 Atributos
| DES | INT (AST) | VIG | VON |
|:---:|:---:|:---:|:---:|
| d`VIEW[{des}]` | d`VIEW[{int}]` | d`VIEW[{vig}]` | d`VIEW[{von}]` |

**Defesa:** `VIEW[{defesa}]` | **D. Mágica:** `VIEW[{def_magica}]` | **Iniciativa:** `VIEW[{iniciativa}]`

## ⚔️ Ataques Básicos
💥 **Voltaic Surge (Corpo a Corpo)**
**Acerto (AST + VON):** `dice: 1d{int} + 1d{von}`
**Dano:** (HR + 5) Raio
**Efeito:** Este ataque tem como alvo a Defesa Mágica em vez da Defesa[cite: 2]. Ao acertar, recupera 5 PM[cite: 2].

## ⚡ Feitiços e Habilidades
✨ **Lux (Feitiço - 10 PM por alvo)**[cite: 2]
**Acerto (AST + VON):** `dice: 1d{int} + 1d{von}`
**Descrição:** Alvo: Até 3 criaturas[cite: 2]. Causa (HR + 15) de dano de Luz[cite: 2].

💀 **Ômega (Feitiço - 20 PM)**[cite: 2]
**Acerto (AST + VON):** `dice: 1d{int} + 1d{von}`
**Descrição:** Alvo: 1 criatura[cite: 2]. O alvo perde uma quantidade de PV igual a `20 + (nível do alvo / 2)`[cite: 2].

📣 **Grito de Guerra (Feitiço - 10 PM por alvo)**[cite: 2]
**Descrição:** Alvo: Até 3 aliados[cite: 2]. Todos os alvos recebem +1 em Testes de Precisão até o fim da cena[cite: 2].

💥 **Explosão de Alma / Detonação Final (Ato Final)**[cite: 2]
**Descrição:** Quando reduzido a 0 PV, liberta uma rajada sacra[cite: 2]. Aliados próximos recuperam 10 PM e inimigos sofrem 10 de dano de Luz automático[cite: 2].

📜 **Maestria Mágica**[cite: 2]
**Descrição:** Interação aprimorada com relógios de cena mágicos[cite: 2]. Pode avançar ou atrasar 1 seção adicional ao interagir com relógios arcanos.

## 🛡️ Afinidades
**Vulnerável:** Trevas 🌑, Veneno 🧪[cite: 2]
**Resistente:** Nenhuma
**Imune:** Ar 🌪️, Luz 🪞[cite: 2]

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