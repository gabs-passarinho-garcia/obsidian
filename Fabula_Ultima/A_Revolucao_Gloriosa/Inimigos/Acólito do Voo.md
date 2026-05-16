---
nome: Acólito do Voo
nivel: 5
rank: Soldado
especie: Humanoide
hp_max: 60
hp_atual: 60
mp_max: 45
mp_atual: 45
des: 8
int: 8
vig: 8
von: 8
defesa: 11
def_magica: 8
iniciativa: 5
tags:
  - monstro
  - fabula-ultima/torre-invertida
exampleProperty: 60
banner: Fabula_Ultima/A_Torre_Invertida/assets/Acolito_art.png
banner_y: "23.5"
---
# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`
![[Acolito_art.png|300]]
## 📊 Status Vital
**Pontos de Vida (PV)**
```meta-bind
INPUT[progressBar(maxValue(60)):hp_atual]
```
`VIEW[{hp_atual}]` / `VIEW[{hp_max}]` (Crise: `VIEW[round({hp_max}/2)]`) 
`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]` 

**Pontos de Magia (PM)**

```meta-bind
INPUT[progressBar(maxValue(45)):mp_atual]
```
`VIEW[{mp_atual}]` / `VIEW[{mp_max}]` 
`BUTTON[pm-5]` `BUTTON[pm-10]` `BUTTON[rest]`

## 🎲 Atributos
| DES | INT (AST) | VIG | VON |
|:---:|:---:|:---:|:---:|
| d`VIEW[{des}]` | d`VIEW[{int}]` | d`VIEW[{vig}]` | d`VIEW[{von}]` |

**Defesa:** `VIEW[{defesa}]` | **D. Mágica:** `VIEW[{def_magica}]` | **Iniciativa:** `VIEW[{iniciativa}]`

## ⚔️ Ataques Básicos
💥 **Arpão de Ancoragem (Corpo a Corpo)**
**Acerto (DES + VIG):** `dice: 1d{des} + 1d{vig}`
**Dano:** (HR + 12) Físico
**Efeito:** Eles tentam pregar os heróis no chão para que sintam o peso que Hooke repudia.

🎯 **Besta de Repetição (À Distância)**
**Acerto (DES + AST):** `dice: 1d{des} + 1d{int}`
**Dano:** (HR + 8) Físico

## ⚡ Habilidades
**Formação Defensiva**
**Descrição:** A Defesa e Defesa Mágica do acólito aumentam em +1 enquanto houver um ou mais aliados próximos.

**Ancorados**
**Descrição:** Graças às suas pesadas botas magnéticas, eles ignoram os efeitos narrativos e desvantagens de flutuar na anomalia de "Gravidade Zero".

## 🛡️ Afinidades
**Vulnerável:** Nenhuma
**Resistente:** Nenhuma
**Imune:** Nenhuma

---
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