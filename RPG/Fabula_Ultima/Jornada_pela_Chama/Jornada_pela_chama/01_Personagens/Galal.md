---
nome: Galal
nivel: 5
classe_primaria: "[[Andarilho]]"
origem: "[[Vila das Bexigueiras]]"
tema: "[[Culpa]]"
identidade: "Um menino descobrindo seu potencial e que busca consertar seu erro."
hp_max: 45
hp_atual: 45
mp_max: 55
mp_atual: 55
ip_max: 6
ip_atual: 6
des: 8
int: 8
vig: 6
von: 10
defesa: 9
def_magica: 9
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
INPUT[progressBar(maxValue(45)):hp_atual]
```
`VIEW[{hp_atual}]` / `VIEW[{hp_max}]` (Crise: 22)
`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]`

**Pontos de Magia (PM)**
```meta-bind
INPUT[progressBar(maxValue(55)):mp_atual]
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
* **[[Elcana]]:** Inferioridade (Acha que nunca será tão bom quanto).
* **[[Abimenoni]]:** Admiração/Lealdade (O mentor).
* **[[Pais de Galal|Pais]]:** Afeto (O porto seguro).
* **[[Kuk]] (Menino Ogro):** Ódio (O bully).
* **[[Treco]]:** Afeto (O companheiro fiel).
* **[[Narelly]]:** Admiração e Desconfiança (Aliada poderosa, mas perigosa).

---
## 🎒 Equipamento & Notas
* **Arma:** [[Tesoura Quebrada]].
* **Item Chave:** [[Livro de Elifeu]] (Roubado/Recuperado).

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
    value: x + 55
```