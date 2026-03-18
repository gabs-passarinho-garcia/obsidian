---
nome: Lodo Estático
nivel: 5
rank: Soldado
especie: Monstro
hp_max: 60
hp_atual: 60
mp_max: 40
mp_atual: 40
des: 6
int: 6
vig: 8
von: 6
defesa: 9
def_magica: 7
iniciativa: 12
tags:
  - monstro
  - fabula-ultima/torre-invertida
exampleProperty: 60
banner: Fabula_Ultima/A_Torre_Invertida/assets/Lodo_art.png
---
# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`
![[Lodo_art.png|300]]
## 📊 Status Vital
**Pontos de Vida (PV)**
```meta-bind
INPUT[progressBar(maxValue(60)):hp_atual]
```
`VIEW[{hp_atual}]` / `VIEW[{hp_max}]` (Crise: `VIEW[round({hp_max}/2)]`) 
`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]` 

**Pontos de Magia (PM)**

```meta-bind
INPUT[progressBar(maxValue(40)):mp_atual]
```
`VIEW[{mp_atual}]` / `VIEW[{mp_max}]` 
`BUTTON[pm-5]` `BUTTON[pm-10]` `BUTTON[rest]`

## 🎲 Atributos
| DES | INT (AST) | VIG | VON |
|:---:|:---:|:---:|:---:|
| d`VIEW[{des}]` | d`VIEW[{int}]` | d`VIEW[{vig}]` | d`VIEW[{von}]` |

**Defesa:** `VIEW[{defesa}]` | **D. Mágica:** `VIEW[{def_magica}]` | **Iniciativa:** `VIEW[{iniciativa}]`

## ⚔️ Ataques Básicos
💥 **Pancada Viscosa (Corpo a Corpo)**
**Acerto (DES + VIG):** `dice: 1d{des} + 1d{vig}`
* **Dano (HR + 5) Físico
**Efeito:** O lodo gruda no alvo, reduzindo sua velocidade. O alvo sofre o status *Lento*.

## ⚡ Habilidades
**Óleo Corrompido (5 PM)**
`BUTTON[habilidade-5]`
**Descrição:** O monstro expele o sangue preto do Motor Ascendente. Um alvo à escolha deve rolar um teste de **VIG + VON** contra a Defesa Mágica do Lodo. Em uma falha, o alvo sofre 10 de dano de Trevas e sente sua consciência pesar, perdendo 5 PM.

## 🛡️ Afinidades
**Vulnerável:** Fogo 🔥
**Resistente:** Físico ⚔️
**Imune:** Trevas 🌑

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

```meta-bind-button
label: Habilidade - 5
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