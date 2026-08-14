---
nome: Narelly
nivel: 5
classe_primaria: "[[Elementalista]]"
origem: "[[Vila do Pântano]]"
tema: "[[Dever]]"
identidade: "A poderosa maga que saiu em busca de salvação para sua vila."
hp_max: 50
hp_atual: 50
mp_max: 65
mp_atual: 65
ip_max: 6
ip_atual: 6
des: 8
int: 12
vig: 8
von: 10
defesa: 9
def_magica: 11
iniciativa: 8
tags:
  - pc
  - fabula_ultima
---

# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Classes:** `VIEW[{classe_primaria}]` | **Tema:** `VIEW[{tema}]`
> *`VIEW[{identidade}]`*

---
## 📊 Status Vital

**Pontos de Vida (PV)** 
```meta-bind
INPUT[progressBar(maxValue(50)):hp_atual]
```

`VIEW[{hp_atual}]` / `VIEW[{hp_max}]` (Crise: 25) 
`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]` 

**Pontos de Magia (PM)** 
```meta-bind
INPUT[progressBar(maxValue(65)):mp_atual]
```
`VIEW[{mp_atual}]` / `VIEW[{mp_max}]` 
`BUTTON[pm-5]` `BUTTON[pm-10]` `BUTTON[rest]`

**Pontos de Inventário (IP)**
`VIEW[{ip_atual}]` / `VIEW[{ip_max}]`

---
## 🎲 Atributos
| DES | INT (Astúcia) | VIG | VON |
| :-: | :-: | :-: | :-: |
| d`VIEW[{des}]` | d`VIEW[{int}]` | d`VIEW[{vig}]` | d`VIEW[{von}]` |

---
## ❤️ Laços
* **[[Socos]] (Família):** Afeto.
* **[[Vila do Pântano]]:** Lealdade e Inferioridade (O peso do dever).
* **[[Galal]]:** Lealdade (Parceiro de infortúnio).
* **[[Treco]]:** Desconfiança (Bicho esquisito...).

---
## ⚡ Magias Conhecidas
* **[[Fogo]] (Elementar):** Dano em área, perfeito para queimar bibliotecas malditas.
* **[[Gelo]] / [[Ar]]:** Controle de campo.

---
## 🎒 Equipamento & Notas
* **Arma:** [[Cajado de Madeira do Pântano]].
* **Acessório:** [[Amuleto da Vila]].

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
    value: x + 65
```