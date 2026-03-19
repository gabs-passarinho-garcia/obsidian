---
nome: Robert Hooke
nivel: 10
rank: Campeão (4)
especie: Humanoide
hp_max: 200
hp_atual: 200
mp_max: 120
mp_atual: 120
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
![[Hooke_Battle_art.png|300]]

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

**A Roleta do Apocalipse (Ação)**
`BUTTON[habilidade-5]` *(Ação narrativa/mecânica)*
**Descrição:** Hooke puxa a alavanca principal do Motor Ascendente, forçando a realidade a dobrar.
* **O Efeito:** Role `1d8` na *Tabela de Anomalias do Motor* abaixo. A sala inteira sofre o efeito imediatamente.
* **O Preço:** O esforço fragmenta o núcleo da Torre. O Mestre deve preencher **1 Seção** do Relógio *Colapso Gravitacional da Torre*.

**O Peso da Culpa (Ação)**
**Descrição:** Hooke usa as tragédias do mundo como arma psicológica. Ele faz um teste oposto de **AST + VON + 1** contra o teste de **VON + VON** de uma criatura que possa ouvi-lo. Se Hooke vencer, o alvo perde 10 PM e sofre a condição *Abalado*.

**Esmagamento Gravitacional (Feitiço - 10 PM)**
`BUTTON[pm-10]`
**Acerto (AST + VON + 1):** `dice: 1d{int} + 1d{von} + 1`
**Descrição:** Alvo: Até 3 criaturas. Hooke amplifica o peso dos alvos de forma impiedosa. Causa **(HR + 10) de dano Físico** e os alvos atingidos ficam *Lentos*.

## ⚙️ Regras Especiais

**Ações Múltiplas:** Como um Campeão (4), Hooke age 4 vezes por rodada de conflito. Alterne cada turno dele com o turno de um Herói.

**Voo (Limitado):** O campo gravitacional distorcido permite que ele flutue acima da arena. Ele não pode ser alvo de ataques corpo a corpo, a menos que o atacante também possa atingir alvos voadores ou se a anomalia **Gravidade Nula** estiver ativa. Se Hooke sofrer dano de **Terra**, ele perde os benefícios de Voo até o início do próximo turno dele, caindo pesadamente no chão sujo.

**Efeito de Crise (Falso Controle):** Quando seus PV caem para 100 ou menos, ele entra em Crise. A partir de agora, toda vez que o turno de Hooke terminar, todas as criaturas na cena (incluindo Hooke) sofrem **5 pontos de dano automático de Raio** (ignora Defesa) enquanto engrenagens derretem ao redor da arena.

---

## 🌌 Dinâmica Exclusiva da Batalha

### 🎲 Tabela de Anomalias do Motor (Role 1d8)
*Role aqui:* `dice: 1d8`

| 🎲 | Anomalia | A Tela (Narrativa) | O Preço (Mecânica) |
| :---: | :--- | :--- | :--- |
| **1** | **Pés de Chumbo** | A gravidade se agarra como lama magnética. | Todos sofrem **Lento** (reduz DES). |
| **2** | **Falta de Atrito** | O chão perde a aderência. Balançar uma lâmina empurra você para trás. | **-2 em Precisão** corpo a corpo. *Leis da Inércia se aplicam.* |
| **3** | **Chuva Invertida** | Estilhaços disparam do chão ao céu. | Teste **【DES + DES】 (Dif 10)**. Falha: 10 ou 30 de dano Físico. |
| **4** | **Vácuo Parcial** | O ar vira lâmina; falta oxigênio. | **Vulnerabilidade a Ar** (dobro do dano). |
| **5** | **Gravidade Nula** | O estômago embrulha no vazio. *Hooke perde imunidade a ataques corpo a corpo.* | Teste **【DES + VON】 (Dif 10)** ou **Atordoado** + avança Relógio Labirintite. *Leis da Inércia se aplicam.* |
| **6** | **Esmagamento** | A gravidade dobra abruptamente. | Teste **【VIG + VIG】 (Dif 10)** ou 30 de dano Físico direto. |
| **7** | **A Lei de Hooke (Elasticidade)** | As paredes e o chão viram molas hipertensas. O impacto devolve o golpe. | Sempre que um personagem errar um ataque corpo a corpo, ele sofre **10 de dano Físico** do próprio recuo. |
| **8** | **Dilatação Temporal** | O tempo escorre espesso como mel. A luz curva e os sons chegam atrasados. | Conjurar feitiços exige um esforço titânico: o custo em PM de qualquer magia **dobra** nesta sala. |

> [!success] 🕊️ A Equação da Graça (Uso de Pontos de Fabula)
> O peso da Lei pode ser anulado. Se os heróis tiverem os Cálculos de Galileu ou a aliança de Newton, eles descobriram a "Equação da Graça" — um *backdoor* no código do universo de Hooke.
> * **Como usar:** Um jogador pode gastar **1 Ponto de Fabula** a qualquer momento para invocar o Tema da Esperança ou a ajuda de Newton.
> * **O Efeito:** A Graça apaga a dívida da física. A anomalia atual é **instantaneamente desativada**, a sala retorna à gravidade normal e a "Roleta do Apocalipse" falha por 1 rodada completa.

### 🍏 Ação de Suporte: As Três Leis de Newton (NPC Auxiliar)
Enquanto Newton estiver protegido pelo grupo, ele pode usar seu turno de NPC para manipular a física a favor dos heróis:
1. **Conservação de Momento (Ataque):** Newton calcula a parábola perfeita. O próximo ataque físico de um herói ganha **+5 de dano adicional**, e esse dano ganha penetração (ignora Resistências físicas).
2. **Cálculo Infinitesimal (Defesa):** Ele prevê a trajetória inimiga através de derivadas. Um herói alvo ganha **+2 na Defesa e Defesa Mágica** até o fim da rodada.
3. **Ação e Reação (Repulsão Cinética):** Newton prepara uma armadilha matemática. Escolha um herói; se esse herói sofrer um ataque corpo a corpo nesta rodada, a energia cinética é devolvida. O herói ganha **Resistência a dano Físico** contra esse golpe, e o atacante sofre **10 pontos de dano Físico automático** pelo coice da própria força.

---

### ⚖️ Composição do Encontro (Balanceamento)
*Esta batalha assume que Hooke enfrenta 4 Heróis. Ajuste conforme o tamanho do grupo:*
* **Se 5 Jogadores:** Adicione **1x Autômato de Repulsão** (Nível 10, 80 PV). O autômato atua como vanguarda, impondo a condição *Lento* e segurando os combatentes corpo a corpo enquanto Hooke voa.
* **Se 6 Jogadores:** Adicione **2x Acólitos do Voo** (Nível 5, 60 PV cada). Eles usam seus arpões para pregar os heróis no chão durante a gravidade zero, forçando o grupo a dividir o foco.

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
### 🌑 Contingência de Fuga: A Queda no Abismo
*Se Hooke for derrotado, o Mestre deve gastar todos os Pontos de Ultima possíveis para mantê-lo na luta até o fim.* * **Condição de Fuga:** Caso o combate termine ou a Torre colapse de forma imprevisível e Hooke ainda possua **pelo menos 1 Ponto de Ultima**, ele o gasta para fugir para os escombros inferiores do Motor Ascendente.
* **O Escalonamento Bestial (Futuro):** Ele não fugirá para tramar vingança, mas para apodrecer no próprio luto. Quando os heróis o reencontrarem no futuro, a radiação do Motor e a loucura terão consumido sua humanidade. Ele perderá a tag *Humanoide* e a classe *Arquiteto*, escalonando para um **Vilão Supremo (15 Pontos de Ultima)** com a tag **Fera/Monstro**. Seus atributos de Astúcia despencarão, substituídos por um Vigor colossal, e ele lutará como uma aberração gravitacional irracional, feita de carne, chumbo e tristeza.


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
> [!quote] 🕊️ Condição de Vitória: Redenção ou Resignação
> Se Hooke estiver com **0 Pontos de Ultima**, os heróis podem tentar redimi-lo em vez de matá-lo.
> * **Teste de Redenção:** Ação de Objetivo 【VON + VON】 ou 【AST + VON】 contra a Vontade de Hooke (d10).
> * **Influência de Newton:** Se a "Equação da Graça" foi ativada, os heróis ganham +4 no teste de precisão para este objetivo.
> * **Resultado:** Em caso de sucesso, Hooke entra em *Resignação*. Ele desliga o Motor e aceita as consequências de seus atos, abandonando sua vilania.
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