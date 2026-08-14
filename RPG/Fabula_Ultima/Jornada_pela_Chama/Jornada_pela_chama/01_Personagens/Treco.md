---
nome: Treco
nivel: 5
rank: Companheiro (Soldado)
especie: Besta
hp_max: 45
hp_atual: 45
mp_max: 20
mp_atual: 20
des: 10
int: 6
vig: 8
von: 8
defesa: 10
def_magica: 8
iniciativa: 13
tags:
  - npc
  - companheiro
  - fabula_ultima
---

# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Espécie:** `VIEW[{especie}]`
> *"O leal e estranho companheiro de Galal. Ninguém sabe exatamente o que ele é, mas ele morde forte."*

---
## 📊 Status Vital

**Pontos de Vida (PV)**
```meta-bind
INPUT[progressBar(maxValue(45)):hp_atual]
```
`VIEW[{hp_atual}]` / `VIEW[{hp_max}]` (Crise: 22)
`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]`

**Pontos de Magia (PM)**
```meta-bind
INPUT[progressBar(maxValue(20)):mp_atual]
```
`VIEW[{mp_atual}]` / `VIEW[{mp_max}]`
`BUTTON[pm-5]` `BUTTON[rest]`

---
## 🎲 Atributos
| DES | INT | VIG | VON |
| :-: | :-: | :-: | :-: |
| d10 | d6 | d8 | d8 |

**Defesa:** 10 | **D. Mágica:** 8 | **Iniciativa:** 13

---
## ⚔️ Ações Básicas

### 🦷 Mordida da Lealdade (Corpo a Corpo)
* **Acerto:** `dice: 1d10 + 1d8` (DES + VIG)
* **Dano:** `dice: 1d8 + 5` (Físico)
* **Efeito:** Se Galal estiver em Perigo, Treco ganha +2 no acerto.

### 🛡️ Proteger (Reação)
Se [[Galal]] ou [[Narelly]] forem sofrer dano, Treco pode entrar na frente e receber o dano no lugar deles (uma vez por rodada).

---
## ❤️ Laços
* **[[Galal]]:** Lealdade (Seu humano favorito).
* **[[Narelly]]:** Afeto (Ela cheira a queimado, mas é legal).

```meta-bind-button
label: Dano - 5
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
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
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
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
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
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
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
id: pm-5
hidden: true
actions:
  - type: updateMetadata
    bindTarget: mp_atual
    evaluate: true
    value: x - 5
```
```meta-bind-button
label: Descansar
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
id: rest
hidden: true
actions:
  - type: updateMetadata
    bindTarget: mp_atual
    evaluate: true
    value: x + 20
```