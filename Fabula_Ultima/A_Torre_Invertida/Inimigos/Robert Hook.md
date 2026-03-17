---
nome: Robert Hooke
nivel: 10
rank: Campeão (4)
especie: Humanoide
hp_max: 200
hp_atual: 200
mp_max: 120
mp_atual: 135
des: 6
int: 10
vig: 6
von: 10
defesa: 7
def_magica: 11
iniciativa: 11
tags:
  - monstro
  - fabula-ultima/torre-invertida
  - chefao
exampleProperty: 200
banner: Fabula_Ultima/A_Torre_Invertida/assets/Hooke_Battle_art.png
banner_y: "25"
---
# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`
*Traços: Arquiteto do Caos, Arrogante, Gênio da Física, Quebrado.*
*Vilão Maior (10 Pontos de Ultima)*
![[Hooke_Battle_art.png]]
## 📊 Status Vital
**Pontos de Vida (PV)**
```meta-bind
INPUT[progressBar(maxValue(200)):hp_atual]
```
`VIEW[{hp_atual}]` / `VIEW[{hp_max}]` (Crise: `VIEW[round({hp_max}/2)]`) 
`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]` 

**Pontos de Magia (PM)**

```meta-bind
INPUT[progressBar(maxValue(120)):mp_atual]
```
`VIEW[{mp_atual}]` / `VIEW[{mp_max}]` 
`BUTTON[pm-5]` `BUTTON[pm-10]` `BUTTON[rest]`

## 🎲 Atributos
| DES | INT (AST) | VIG | VON |
|:---:|:---:|:---:|:---:|
| d`VIEW[{des}]` | d`VIEW[{int}]` | d`VIEW[{vig}]` | d`VIEW[{von}]` |

**Defesa:** `VIEW[{defesa}]` | **D. Mágica:** `VIEW[{def_magica}]` | **Iniciativa:** `VIEW[{iniciativa}]`

*(Equipamento: Casaco Aristocrático Manchado concede +1 na Defesa e Defesa Mágica, já contabilizados nos atributos acima).*

## ⚔️ Ataques Básicos
💥 **Chave Inglesa Pesada (Corpo a Corpo)**
**Acerto (DES + VIG + 1):** `dice: 1d{des} + 1d{vig} + 1`
**Dano:** (HR + 5) Físico
**Efeito:** Um golpe desesperado e bruto de quem perdeu a elegância da ciência.

🎯 **Disparo de Grávitons (À Distância)**
**Acerto (AST + AST + 1):** `dice: 1d{int} + 1d{int} + 1`
**Dano:** (HR + 10) Ar
**Efeito:** Hooke manipula a gravidade local para arremessar detritos, parafusos e vigas de ferro com força letal.

## ⚡ Feitiços e Ações Únicas
**O Peso da Culpa (Ação)**
`BUTTON[habilidade-5]` *(O custo original não tem PM listado, usei botão genérico de habilidade)*
**Descrição:** Hooke usa as tragédias do mundo como arma psicológica. Ele faz um teste oposto de **AST + VON + 1** contra o teste de **VON + VON** de uma criatura que possa ouvi-lo. Se Hooke vencer, o alvo perde 10 PM e sofre a condição *Abalado*.

**Esmagamento Gravitacional (Feitiço - 10 PM)**
`BUTTON[pm-10]`
**Acerto (AST + VON + 1):** `dice: 1d{int} + 1d{von} + 1`
**Descrição:** Alvo: Até 3 criaturas. Hooke amplifica o peso dos alvos de forma impiedosa. Causa **(HR + 10) de dano Físico** e os alvos atingidos ficam *Lentos*.

## ⚙️ Regras Especiais
**Ações Múltiplas:**
Como um Campeão (4), Hooke age 4 vezes por rodada de conflito. Lembre-se de alternar cada turno dele com o turno de um Herói.

**Voo (Limitado):**
O campo gravitacional distorcido permite que ele flutue acima da arena. Ele não pode ser alvo de ataques corpo a corpo, a menos que o atacante também possa atingir alvos voadores. Se Hooke sofrer dano de **Terra**, ele perde os benefícios de Voo até o início do próximo turno dele, caindo pesadamente no chão sujo do planetário.

**Efeito de Crise (Falso Controle):**
A arrogância de Hooke cobra seu preço. Quando seus PV caem para 100 ou menos, ele entra em Crise e a Torre da Inversão surta. A partir de agora, toda vez que o turno de Hooke terminar, o núcleo pisca violentamente: todas as criaturas na cena (incluindo Hooke) sofrem **5 pontos de dano automático de Raio** (que ignora Defesa) enquanto engrenagens derretem ao redor da arena.

## 🛡️ Afinidades
**Vulnerável:** Terra 🪨 (A gravidade o puxa de volta)
**Resistente:** Ar 🌪️
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