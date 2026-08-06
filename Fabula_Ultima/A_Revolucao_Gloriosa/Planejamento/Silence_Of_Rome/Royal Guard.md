---
nome: Royal Guard
nivel: 10
rank: Soldado
especie: Humanoide
hp_max: 90
hp_atual: 90
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
  - guarda-real
banner: Fabula_Ultima/assets/Royal_Guard_art.png
banner_y: "25"
---
# `VIEW[{nome}]`
**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`
![[Royal_guard_art.png]]

## 📊 Status Vital
**Pontos de Vida (PV)**
```meta-bind
INPUT[progressBar(maxValue(90)):hp_atual]
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
🗡️ **Sabre (Corpo a Corpo)**[cite: 3]
**Acerto (DES + VIG + 1):** `dice: 1d{des} + 1d{vig} + 1`
**Dano:** (HR + 5) Físico[cite: 3]
**Efeito:** Possui a propriedade **Multi (2)** — pode atingir até 2 alvos na mesma ação[cite: 3].

🛡️ **Spear / Estocada de Contenção (Corpo a Corpo)**[cite: 3]
**Acerto (VIG + VIG + 1):** `dice: 1d{vig} + 1d{vig} + 1`
**Dano:** (HR + 10) Físico[cite: 3]
**Efeito:** Inimigos atingidos tornam-se alvos válidos para a habilidade **Esmagar**[cite: 3].

## ⚡ Habilidades
✊ **Esmagar / Crush (Habilidade)**[cite: 3]
**Descrição:** O guarda agarra e prende um inimigo com força bruta[cite: 3]. No início do turno do guarda, qualquer alvo agarrado sofre 10 de dano Físico automático sem necessidade de teste[cite: 3].

🛡️ **Guarda Aprimorada / Improved Guard (Regra)**[cite: 3]
**Descrição:** Quando o guarda realiza a ação de Guardar, seu próximo ataque corpo a corpo causa +5 de dano Físico adicional e ignora a Defesa do alvo[cite: 3].

🔄 **Recuperação Estável / Steady Recovery (Regra)**[cite: 3]
**Descrição:** Treinamento disciplinado permite ignorar fadiga de combate[cite: 3]. Sempre que realiza a ação de Guardar, o guarda remove um efeito de status: Atordoado, Abalado ou Lento[cite: 3].

⚡ **Mau Humor / Bad Temper (Efeito de Crise - Regra)**[cite: 3]
**Descrição:** Enquanto em Crise, a fúria desesperada do guarda adiciona +2 de dano a todos os seus ataques corpo a corpo[cite: 3].

🗯️ **Mau Perdedor / Sore Loser (Regra)**[cite: 3]
**Descrição:** Ao falhar em um Teste Oposto contra um inimigo, o guarda desfere um empurrão de revanche[cite: 3]. O inimigo deve realizar um teste de 【VIG + VIG】 (Dificuldade Fácil) ou sofrer a condição Abalado[cite: 3].

💥 **Enfraquecimento Final / Final Weakness (Ato Final - Regra)**[cite: 3]
**Descrição:** Quando reduzido a 0 PV, a formação do guarda se rompe e expõe a liderança[cite: 3]. O Campeão/Chefão da cena (como o Rei Jaime II) fica Vulnerável a dano de Fogo até o final da próxima rodada.

## 🛡️ Afinidades
**Vulnerável:** Gelo ❄️, Luz 🪞, Veneno 🧪[cite: 3]
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
    value: x + 10
```