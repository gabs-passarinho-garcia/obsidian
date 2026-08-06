---
nome: Swiss Guard
nivel: 10
rank: Soldado
especie: Humanoide
hp_max: 80
hp_atual: 80
mp_max: 50
mp_atual: 50
des: 8
int: 6
vig: 10
von: 8
defesa: 10
def_magica: 6
iniciativa: 8
tags:
  - monstro
  - fabula-ultima/revolucao-gloriosa
  - guarda-suico
banner: Fabula_Ultima/assets/Swiss_Guard_art.png
banner_y: "25"
---
# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`
![[Swiss_guard_art.png]]

## 📊 Status Vital
**Pontos de Vida (PV)**
```meta-bind
INPUT[progressBar(maxValue(80)):hp_atual]
```
`VIEW[{hp_atual}]` / `VIEW[{hp_max}]` (Crise: `VIEW[round({hp_max}/2)]`) 
`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]` 

**Pontos de Magia (PM)**

```meta-bind
INPUT[progressBar(maxValue(50)):mp_atual]
```
`VIEW[{mp_atual}]` / `VIEW[{mp_max}]` 
`BUTTON[pm-5]` `BUTTON[pm-10]` `BUTTON[rest]`

## 🎲 Atributos
| DES | INT (AST) | VIG | VON |
|:---:|:---:|:---:|:---:|
| d`VIEW[{des}]` | d`VIEW[{int}]` | d`VIEW[{vig}]` | d`VIEW[{von}]` |

**Defesa:** `VIEW[{defesa}]` | **D. Mágica:** `VIEW[{def_magica}]` | **Iniciativa:** `VIEW[{iniciativa}]`

## ⚔️ Ataques Básicos
🗡️ **Alabarda Reagrupada (Corpo a Corpo)**[cite: 4]
**Acerto (DES + VIG + 1):** `dice: 1d{des} + 1d{vig} + 1`
**Dano:** (HR + 5) Luz[cite: 4]
**Efeito:** Possui a propriedade **Multi (2)** — pode atingir até 2 alvos na mesma ação[cite: 4].

🛡️ **Embracer / Estocada de Contenção (Corpo a Corpo)**[cite: 4]
**Acerto (VIG + VIG + 1):** `dice: 1d{vig} + 1d{vig} + 1`
**Dano:** (HR + 10) Físico[cite: 4]
**Efeito:** Inimigos atingidos tornam-se alvos válidos para a habilidade **Esmagar**[cite: 4].

## ⚡ Habilidades
✊ **Esmagar**[cite: 4]
**Descrição:** Garra e prende inimigos[cite: 4]. O guarda causa 10 de dano Físico automático a um alvo agarrado no início de seu turno sem precisar de teste de acerto.

🛡️ **Guarda Aprimorada**[cite: 4]
**Descrição:** Se o guarda usar a Ação de Guardar, seu próximo ataque causa +5 de dano adicional e ignora a Defesa do alvo[cite: 4].

⚡ **Mau Humor (Efeito de Crise)**[cite: 4]
**Descrição:** Enquanto estiver em Crise, ganha +2 no Dano de todos os ataques corpo a corpo[cite: 4].

💥 **Enfraquecimento Final (Ato Final)**[cite: 4]
**Descrição:** Quando derrotado, sua linha de defesa se rompe de forma exposta, tornando o líder da cena (como Jaime II) Vulnerável a dano de Fogo por 1 rodada[cite: 4].

## 🛡️ Afinidades
**Vulnerável:** Trevas 🌑, Veneno 🧪[cite: 4]
**Resistente:** Nenhuma
**Imune:** Luz 🪞[cite: 4]

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
    value: x + 10
```