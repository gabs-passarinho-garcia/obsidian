---
nome: Vinha-daninha Retorcida
nivel: 5
rank: Soldado
especie: Planta
hp_max: 50
hp_atual: 50
mp_max: 40
mp_atual: 40
des: 8
int: 6
vig: 6
von: 8
defesa: 9
def_magica: 9
iniciativa: 14
tags:
  - monstro
  - fabula-ultima/torre-invertida
exampleProperty: 50
banner: Fabula_Ultima/A_Torre_Invertida/assets/Vinha_art.png
banner_y: "33"
---
# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`
![[Vinha_art.png]]
## 📊 Status Vital
**Pontos de Vida (PV)**
```meta-bind
INPUT[progressBar(maxValue(50)):hp_atual]
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
💥 **Chicote de Raízes (Corpo a Corpo)**
**Acerto (DES + VON):** `dice: 1d{des} + 1d{von}`
* **Dano (HR + 5) Físico
**Efeito:** As raízes tentam puxar a vítima para o chão invertido. O alvo sofre o status *Abalado*.

## ⚡ Habilidades
**Pólen da Inocência Apodrecida (5 PM)**
`BUTTON[habilidade-5]`
**Descrição:** A planta sacode suas folhas manchadas, liberando um esporo com cheiro de maçã doce, mas de cor púrpura. Atinge até dois alvos. Cada alvo faz um teste de **VON + VON** contra a Defesa Mágica da Vinha. Em uma falha, sofrem 10 de dano de Veneno e adquirem o status *Envenenado*.

## 🛡️ Afinidades
**Vulnerável:** Vento 🌪️
**Resistente:** Terra 🪨
**Imune:** Veneno 🧪

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