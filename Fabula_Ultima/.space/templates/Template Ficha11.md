---
nome: Nome do Monstro
nivel: 1
rank: Soldado
especie: Besta
hp_max: 50
hp_atual: 50
mp_max: 20
mp_atual: 20
des: 6
int: 6
vig: 6
von: 6
defesa: 8
def_magica: 8
iniciativa: 8
tags:
  - monstro
  - fabula_ultima
exampleProperty: 50
---


# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`

---
## 📊 Status Vital


**Pontos de Vida (PV)** 
```meta-bind
INPUT[progressBar(maxValue(50)):hp_atual]
```
`VIEW[{hp_atual}]` / `VIEW[{hp_max}]` (Crise: `VIEW[round({hp_max}/2)]`) 

`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]` 

**Pontos de Magia (PM)** 
```meta-bind
INPUT[progressBar(maxValue(20)):mp_atual]
```
`VIEW[{mp_atual}]` / `VIEW[{mp_max}]` 

`BUTTON[pm-5]` `BUTTON[pm-10]` `BUTTON[rest]`

---
## 🎲 Atributos
| DES | INT | VIG | VON |
| :-: | :-: | :-: | :-: |
| d`VIEW[{des}]` | d`VIEW[{int}]` | d`VIEW[{vig}]` | d`VIEW[{von}]` |

**Defesa:** `VIEW[{defesa}]` | **D. Mágica:** `VIEW[{def_magica}]` | **Iniciativa:** `VIEW[{iniciativa}]`

---
## ⚔️ Ataques Básicos

### 💥 Nome do Ataque (Melee)
* **Acerto (DES + VIG):** `dice: 1d{des} + 1d{vig}`
* **Dano (HR + 5)
* *Efeito:* Derruba o alvo.

---
## ⚡ Habilidades
### Nome da Habilidade (5 PM)
`BUTTON[habilidade-5]`
* **Descrição:** O monstro faz algo assustador.

---
## 🛡️ Afinidades
* **Vulnerável:** 
* **Resistente:** 
* **Imune:** ```

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
label: PM - 10
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
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
    value: x+10

```

```meta-bind-button
label: Habilidade
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
id: habilidade-5
hidden: true
actions:
  - type: updateMetadata
    bindTarget: mp_atual
    evaluate: true
    value: x - 5

```