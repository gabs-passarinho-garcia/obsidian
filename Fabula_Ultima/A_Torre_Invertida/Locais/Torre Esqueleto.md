---
tags:
  - local
  - masmorra
  - fabula-ultima/torre-invertida
  - tema/realismo-poetico
tipo: Esqueleto da Exploração
status: Refinado
arquiteto: "[[Robert Hooke]]"
localização: Centro da [[Vila de Queda-Livre]]
relogio_labirintite: 0
---
# 🏰 Estrutura de Exploração: A Torre da Inversão

> *"Se o chão rejeita os nossos pés, nós marcharemos pelo céu."*

## ⚙️ A Dinâmica Central (O Core Loop)
A Torre da Inversão é um organismo em agonia, reagindo violentamente à intrusão. A exploração segue este ciclo a cada nova sala ou andar:

1. **A Transição:** Ao cruzar uma porta, a gravidade sofre um solavanco. O *Relógio de Labirintite* avança **1 seção** para o grupo.
2. **A Anomalia:** O Mestre rola **1d6** na *Tabela de Anomalias* abaixo para definir a regra física do ambiente.
3. **A Resolução:** O grupo enfrenta a ameaça (Combate ou Teste de Grupo de Física Cinemática).
4. **O Preço:** Falhas nos testes de navegação ou uso leviano de magias de voo/teletransporte avançam o *Relógio de Colapso Gravitacional*.

---

## 🎲 Tabela de Anomalias da Sala (Role 1d6)
*Role ao entrar em uma nova zona. A regra se mantém até a próxima transição.*
`dice: 1d6`

| 1d6 | Anomalia | Efeito Mecânico (Fabula Ultima) |
| :---: | :--- | :--- |
| **1** | **Pés de Chumbo** | A gravidade puxa demais. Todos recebem o status *Lento*. |
| **2** | **Falta de Atrito** | O chão é ensaboado de vácuo. Ataques corpo a corpo sofrem Desvantagem. |
| **3** | **Chuva Invertida** | Estilhaços e destroços caem do chão para o teto. Dano ambiental no fim da rodada. |
| **4** | **Vácuo Parcial** | O ar é rarefeito e cortante. Todo Dano de Vento/Ar é maximizado na cena. |
| **5** | **Gravidade Nula** | O ambiente perde o prumo. Teste de `Agilidade + Vontade`. Falhas resultam em ficar à deriva. **Avança o Relógio de Labirintite em 2 seções instantaneamente.** |
| **6** | **Esmagamento** | A pressão dobra. Personagens frágeis (sem bônus de Defesa Física alto) sofrem dano direto de Crise ao entrar. |

---

## 🤢 O Preço do Caos: Labirintite e Dramina

O corpo humano não foi feito para ser dobrado junto com o espaço. Acompanhe a vertigem do grupo:
**Relógio de Labirintite Global:** ( `VIEW[{relogio_labirintite}]` / 6 )
`INPUT[slider(minValue(0), maxValue(6)):relogio_labirintite]`

### Efeitos do Enjoo Gravitacional
* **Estágio 1 - Suor Frio (Relógio em 3/6):** A vertigem bate. O grupo recebe o status **Abalado** (Atributos mentais caem temporariamente).
* **Estágio 2 - Colapso Gástrico (Relógio em 6/6):** O estômago vence. O status agrava para **Lento**. No próximo combate, personagens devem gastar a Ação Principal para "limpar o sistema" (vomitar). Lutar ignorando a ânsia causa Dano Direto de Crise em PM (Pontos de Mente).

### 🧪 Item de Inventário: Tintura de Dramina
*Uma poção alquímica espessa e amarga, com cheiro de raiz-pesada e ferrugem.*
* **Custo:** 2 PI (Pontos de Inventário) e uma Ação de Inventário para consumir.
* **O Alívio:** Zera instantaneamente o Relógio de Labirintite do usuário e cura status ligados ao enjoo.
* **O Preço (Efeito Colateral):** A mente amortece. O usuário sofre imediatamente o status **Ofuscado** (Intuição reduzida) devido à sonolência severa.
* **Overdose:** Ingerir uma segunda dose enquanto já estiver *Ofuscado* força o corpo a desligar. O personagem cai no estado **Sono/Inconsciente** por 1 rodada completa.

---

## 🗺️ O Esqueleto dos Andares

### 1. O Teto do Saguão (Entrada)
* **Atmosfera:** O grupo cai para o teto. Afrescos rachados e destroços pairam invertidos.
* **Desafio de Navegação:** Teste de Grupo de `Agilidade + Vigor` para saltar por escadarias quebradas como se fossem plataformas suspensas.
* **Encontro:** Gárgulas de pedra que manipulam pedregulhos gravitacionais.
* **Lore:** Aqui se encontra a primeira página rasgada dos *[[Manuscritos de Da Vinci]]*.

### 2. A Cela Estática (Andar Intermediário)
* **Atmosfera:** Ponto de equilíbrio pesado. O ar parece água. O olho do furacão.
* **O Dilema Moral:** O encontro com [[Isaac Newton]]. Ele calcula os nós de energia da torre. 
* **Resolução:** Libertá-lo entrega ao grupo os *[[Cálculos de Galileu]]* (ativando a "Equação da Graça" na batalha final), mas desestabiliza a masmorra, avançando o Relógio de Colapso Gravitacional.
* **Lore:** Podem encontrar a luva chamuscada de [[Helena]], sentindo o peso do sacrifício visceral que causou tudo.

### 3. O Planetário Quebrado (Fundo do Céu - Clímax)
* **Atmosfera:** O cume da torre, um fosso magnético onde o *[[Motor Ascendente]]* guincha, exalando calor, ozônio e culpa.
* **O Confronto:** [[Robert Hooke]] luta de forma errática. Ele usa os controles do Motor para rolar ativamente na *Tabela de Anomalias* como Ação Secundária.
* **Tática Brutal:** O Motor é um alvo vulnerável à quebra de componentes. Destruir suas válvulas reproduz o superaquecimento letal, causando Dano Massivo de Fogo em Hooke e forçando o combate de volta ao "chão firme".