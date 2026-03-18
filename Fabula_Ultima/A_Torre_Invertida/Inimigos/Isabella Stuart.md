---
nome: Isabella Stuart
nivel: 10
rank: Campeã (2)
especie: Humanoide
hp_max: 100
hp_atual: 100
mp_max: 120
mp_atual: 120
des: 8
int: 10
vig: 6
von: 10
defesa: 9
def_magica: 11
iniciativa: 9
tags:
  - npc
  - vilao/maior
  - fabula-ultima/queda-livre
  - tema/realismo-poetico
  - monstro
  - fabula-ultima/torre-invertida
  - chefao
banner: Fabula_Ultima/A_Torre_Invertida/assets/Isabella_art.png
banner_y: "25"
---

# 🌹 `VIEW[{nome}]`

**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`
**Traços:** Falsa Vulnerabilidade, Herdeira Bastarda, Manipuladora, Oradora Implacável.
**Vilã Maior (10 Pontos de Ultima)**

> *"Isaac sempre disse que o que sobe, deve descer. Mal posso esperar para ver o mundo dele despencar enquanto eu finalmente subo."*

![[Isabella_battle_art.png|300]]
---

📊 **Status Vital**

**Pontos de Vida (PV)**
```meta-bind
INPUT[progressBar(maxValue(100)):hp_atual]
```
**`VIEW[{hp_atual}]` / `VIEW[{hp_max}]`** (Crise: `VIEW[round({hp_max}/2)]`)
`BUTTON[dano-5]` `BUTTON[dano-10]` `BUTTON[cura-5]` 

**Pontos de Magia (PM)**
```meta-bind
INPUT[progressBar(maxValue(120)):mp_atual]
```
**`VIEW[{mp_atual}]` / `VIEW[{mp_max}]`**
`BUTTON[pm-5]` `BUTTON[pm-10]` `BUTTON[rest]`

---

🎲 **Atributos**

| DES | INT (AST) | VIG | VON |
| :---: | :---: | :---: | :---: |
| d`VIEW[{des}]` | d`VIEW[{int}]` | d`VIEW[{vig}]` | d`VIEW[{von}]` |

**Defesa:** `VIEW[{defesa}]` | **D. Mágica:** `VIEW[{def_magica}]` | **Iniciativa:** `VIEW[{iniciativa}]`
*(Equipamento: Vestido Discreto de Alta Costura e Anel de Sinete dos Stuart).*

---

⚔️ **Ataques Básicos**

💥 **Estilete Oculto (Corpo a Corpo)**
**Acerto (DES + INT + 1):** `dice: 1d{des} + 1d{int} + 1`
**Dano:** (HR + 5) **Físico**
*Efeito: Um corte rápido e limpo, revelando que a máscara de doçura finalmente caiu.*

🎯 **Palavras Envenenadas (À Distância)**
**Acerto (INT + VON + 1):** `dice: 1d{int} + 1d{von} + 1`
**Dano:** (HR + 10) **Trevas**
*Efeito: Isabella sussurra verdades corrosivas sobre o passado e as falhas dos heróis, ferindo diretamente a alma.*

---

⚡ **Feitiços e Ações Únicas**

**Condenação Elegante (Ação - 10 PM)**
```meta-bind
BUTTON[pm-10]
```
*Descrição: Bella expõe as falhas morais de um inimigo. Teste oposto de [INT + VON + 1] contra [VON + VON] do alvo. Se vencer, o alvo perde 10 PM e sofre a condição **Abalado**.*

**Ordem da Coroa (Ação)**
*Descrição: Comando Tático. Bella incita um aliado NPC a protegê-la. O lacaio faz um ataque imediato ou assume a ação de Guarda para receber golpes no lugar dela.*

---

⚙️ **Regras Especiais e Dinâmica de Vilã**

- **Ações Múltiplas:** Como uma Campeã (2), Isabella age 2 vezes por rodada. Alternar turnos com os Heróis.
- **A Rosa Escondida (Passiva):** Recebe bônus de +3 em testes opostos em situações sociais.
- **O Sangue Não Mente (Efeito de Crise):** Quando em Crise (50 PV ou menos), a fachada dócil desaparece. Inimigos que a atacarem perdem 5 PM automaticamente por golpe.
- **Sedução Narrativa (Dilema):** Em falhas de negociação, ela oferece um Sucesso Custoso: ela ajuda o grupo, mas o jogador deve escrever um **Laço de Lealdade** com ela na ficha.
- **A Ascensão (Escalonamento):** Se fundir seu sangue ao Motor Ascendente, ela ignora a derrota e Escalona para **Vilã Suprema (15 Pontos de Ultima)**.

---

🛡️ **Afinidades**

- **Vulnerável:** Fogo 🔥 (A rosa queima sob a brutalidade).
- **Imune:** Trevas 🌑 (A corrupção moral é seu lar).

---

### 📖 A Rosa Amargurada (Lore de Sessão Zero)

**O Espelho de Ontem (A Variável Descartada):**
Anos antes de Helena, [[Isabella]] foi a paixão secreta de Newton. Ela acreditava que seriam os reis de uma nova era da razão. Mas Newton, ao perceber que a ambição política dela interferia em seus cálculos, terminou o romance de forma "amigável" e lógica. Para ele, foi uma equação resolvida. Para ela, foi o ato de ser apagada da história pelo homem que ela amava.

**O Encontro (Queda-Livre):**
Ela se infiltra no grupo como a guia doce da vila. Se o grupo resgatar Newton, a tensão será palpável. Ela o tratará com uma ironia cortante até o momento da traição no topo da Torre.

---

### 🎨 Prompts para Pixel Art (16-bits)

**Antes (Vibrante - Estilo Sea of Stars):**
`16-bit pixel art, Sea of Stars style. A breathtakingly beautiful young woman named Isabella with long flowing brown hair. She wears a vibrant floral dress and holds a basket of red roses. Radiant smile, noble posture. Sunlight filtering through lush green trees in a peaceful village. Warm and bright colors.`

**Depois (Sombria - Estilo Final Fantasy VI):**
`16-bit pixel art, Final Fantasy VI style. A mysterious and composed woman named Isabella in a dark, elegant hooded cloak. She is clutching a hidden gold signet ring near her chest. Sharp, calculating gaze. She stands in the dim, purple-lit shadows of a ruined tavern. Moody atmosphere, high contrast, blue and violet tones.`

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
```meta-bind-button
label: PM - 5
id: pm-5
hidden: true
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
actions:
  - type: updateMetadata
    bindTarget: mp_atual
    evaluate: true
    value: x - 5
```
```meta-bind-button
label: PM - 10
id: pm-10
hidden: true
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
actions:
  - type: updateMetadata
    bindTarget: mp_atual
    evaluate: true
    value: x - 10
```
```meta-bind-button
label: Descansar
id: rest
hidden: true
icon: ""
style: default
class: ""
cssStyle: negative
backgroundImage: ""
tooltip: ""
actions:
  - type: updateMetadata
    bindTarget: mp_atual
    evaluate: true
    value: x + 10
```
