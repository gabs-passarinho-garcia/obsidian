---
nome: Autômato de Repulsão
nivel: 10
rank: Soldado
especie: Construto
hp_max: 80
hp_atual: 80
mp_max: 40
mp_atual: 40
des: 8
int: 8
vig: 10
von: 6
defesa: 11
def_magica: 8
iniciativa: 5
tags:
  - monstro
  - fabula-ultima/torre-invertida
exampleProperty: 80
banner: Fabula_Ultima/A_Torre_Invertida/assets/Automato_art.png
banner_y: "17"
---
# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`
![[Automato_art.png]]
## 📊 Status Vital
**Pontos de Vida (PV)**
```meta-bind
INPUT[progressBar(maxValue(80)):hp_atual]
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
💥 **Maça Gravitacional (Corpo a Corpo)**
**Acerto (VIG + VIG + 1):** `dice: 1d{vig} + 1d{vig} + 1`
**Dano:** (HR + 14) Físico
**Efeito:** O impacto sobrecarrega o peso do herói. Se atingir, o alvo fica *Lento*.

## ⚡ Habilidades
**Construto**
**Descrição:** Por ser uma máquina feita das anotações de Da Vinci, o autômato é imune à condição *Envenenado*.

**Núcleo Exposto (Crise)**
**Descrição:** A genialidade de Hooke tem falhas. Enquanto o Autômato estiver em Crise (40 PV ou menos), suas válvulas superaquecem. Ele perde a Resistência a dano de Fogo, e o dano da sua Maça Gravitacional se torna do tipo **Raio**, enquanto faíscas espirram de seu chassi quebrado.

## 🛡️ Afinidades
**Vulnerável:** Raio ⚡, Gelo ❄️
**Resistente:** Fogo 🔥, Terra 🪨
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