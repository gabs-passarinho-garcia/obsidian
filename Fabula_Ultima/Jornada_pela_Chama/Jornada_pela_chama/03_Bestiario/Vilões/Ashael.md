---
nome: Ashael, o Bibliotecário
nivel: 10
rank: Vilão Menor
especie: Humanoide ([[Arcanista]])
hp_max: 80
hp_atual: 80
mp_max: 90
mp_atual: 90
ultima_points: 5
des: 8
int: 10
vig: 6
von: 12
defesa: 9
def_magica: 12
iniciativa: 12
tags:
  - vilao
  - fabula_ultima
---

# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`
> *"A vida eterna é uma página bem escrita. Deixe-me ler sua alma."*

---
## 📊 Status Vital

**Pontos de Vida (PV)** 
```meta-bind
INPUT[progressBar(maxValue(80)):hp_atual]
```

`VIEW[{hp_atual}]` / `VIEW[{hp_max}]` (Crise: 40)
`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]` 

**Pontos de Magia (PM)** 
```meta-bind
INPUT[progressBar(maxValue(90)):mp_atual]
```

`VIEW[{mp_atual}]` / `VIEW[{mp_max}]` 
`BUTTON[pm-5]` `BUTTON[pm-10]` 

**Pontos de Ultima:** `VIEW[{ultima_points}]`

---
## 🎲 Atributos
| DES | INT | VIG | VON |
| :-: | :-: | :-: | :-: |
| d8 | d10 | d6 | d12 |

**Defesa:** 9 | **D. Mágica:** 12 | **Iniciativa:** 12

---
## ⚔️ Ações & Feitiços

### 📖 [[Encadernar Alma]] (10 PM)
*Ataque Mágico vs Vontade.*
* **Efeito:** O alvo sofre **dano mental** e fica **Lento**. Se o alvo chegar a 0 PV com este ataque, ele não morre; ele é transformado em um livro e adicionado à estante (Capturado).

### 🖐️ [[Mão Espectral]] (Ação Básica)
* **Acerto:** `dice: 1d10 + 1d12` (INT + VON)
* **Dano:** `dice: 1d12 + 6` (Dano de Trevas)

### 📚 [[Convocar Golem de Papel]] (15 PM)
Ashael convoca 2 **[[Golens de Livros]]** (Soldados, Nível 5) para protegê-lo.

---
## 🛡️ Afinidades
* **Vulnerável:** 🔥 [[Fogo]] (Sua coleção queima fácil!)
* **Resistente:** 🌑 [[Trevas]]
* **Imune:** 🧪 [[Veneno]] (Ele já está meio morto por dentro).

---
## ⏰ Relógio da Cena: "A Fuga Incendiária"
**Objetivo:** Fugir da Mansão em Chamas com o [[Livro de Elifeu]].
**Tamanho:** 6 Segmentos.

1. **Preencher:** Usar [[Fogo]] (Narelly), Derrubar Estantes (Galal), Guiar ([[Treco]]).
2. **Consequência (Falha):** Ashael bloqueia a saída ou o fogo causa dano massivo ao grupo.
3. **Consequência (Sucesso):** O grupo escapa, a mansão desaba, Ashael jura vingança.

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