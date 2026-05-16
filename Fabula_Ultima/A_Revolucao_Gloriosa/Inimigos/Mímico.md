---
nome: Mímico de Obsidiana e Chumbo
nivel: 10
rank: Soldado
especie: Monstro
hp_max: 70
hp_atual: 70
mp_max: 45
mp_atual: 45
des: 10
int: 8
vig: 8
von: 6
defesa: 11
def_magica: 10
iniciativa: 9
tags:
  - monstro
  - fabula-ultima/torre-invertida
banner: Fabula_Ultima/A_Torre_Invertida/assets/Mimico_art.png
---
# 🧰 `VIEW[{nome}]`
> *"A ganância cega os olhos, mas afia os dentes de chumbo de quem espera no vácuo."*

![[Mimico_art.png]]

![[Mimico_battle_art.png]]

**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`
**Traços:** Amorfo, Furtivo, Sagaz, Voraz.

## 📊 Status Vital
**Pontos de Vida (PV)**
```meta-bind
INPUT[progressBar(maxValue(70)):hp_atual]
```
**`VIEW[{hp_atual}]` / `VIEW[{hp_max}]`** (Crise: `VIEW[round({hp_max}/2)]`) 
`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]` 

**Pontos de Magia (PM)**
```meta-bind
INPUT[progressBar(maxValue(45)):mp_atual]
```
**`VIEW[{mp_atual}]` / `VIEW[{mp_max}]`** ## 🎲 Atributos
| DES | INT (AST) | VIG | VON |
|:---:|:---:|:---:|:---:|
| d`VIEW[{des}]` | d`VIEW[{int}]` | d`VIEW[{vig}]` | d`VIEW[{von}]` |

**Defesa:** `VIEW[{defesa}]` | **D. Mágica:** `VIEW[{def_magica}]` | **Iniciativa:** `VIEW[{iniciativa}]`

## ⚔️ Ataques Básicos
💥 **Garra de Engrenagem (Corpo a Corpo)**
**Acerto (DES + VIG + 4):** `dice: 1d{des} + 1d{vig} + 4`
**Dano:** (HR + 5) Físico
**Efeito de Emboscada:** Se o mímico atacou um alvo desavisado, este ataque causa o **dobro de dano**.

🎯 **Roubo de Inventário (À Distância)**
**Acerto (DES + AST + 4):** `dice: 1d{des} + 1d{int} + 4`
**Dano:** (HR + 5) Físico
**Efeito Cruel:** Os alvos atingidos perdem imediatamente **2 Pontos de Inventário (PI)**. *Na Torre, isso rouba a munição de impulso deles!*

## ⚡ Habilidades e Regras Especiais
**Mudança de Forma Corrompida**
Enquanto transformado, o mímico é idêntico a um baú de manutenção de Robert Hooke. 

> [!danger] 👁️ Pista Visceral: O Erro na Equação
> Para identificar a criatura, os heróis devem notar uma falha sensorial que revela a alma do monstro:
> * **A Sombra Invertida:** A sombra do baú projeta-se na direção oposta à luz da sala, "subindo" pelas paredes como se estivesse ancorada em outra dimensão.
> * **O Calor da Carne:** O metal de obsidiana exala um calor febril e úmido, e ao encostar o ouvido na carcaça, ouve-se o ranger rítmico de engrenagens tentando moer ossos invisíveis.

**Predador da Inércia**
O mímico ignora os efeitos de **Falta de Atrito** e **Gravidade Nula**, pois suas garras se ancoram magneticamente na estrutura da Torre.

## 🛡️ Afinidades
**Vulnerável:** Terra 🪨, Veneno 🧪
**Resistente:** Físico ⚔️, Ar 🌪️, Trevas 🌑, Luz ☀️

---
```meta-bind-button
label: Dano - 5
id: dano-5
hidden: true
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
actions:
  - type: updateMetadata
    bindTarget: hp_atual
    evaluate: true
    value: x - 5
```
```meta-bind-button
label: Dano - 10
id: dano-10
hidden: true
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
actions:
  - type: updateMetadata
    bindTarget: hp_atual
    evaluate: true
    value: x - 10
```
```meta-bind-button
label: Cura + 5
id: cura-5
hidden: true
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
actions:
  - type: updateMetadata
    bindTarget: hp_atual
    evaluate: true
    value: x + 5
```