---
tags:
  - monstro
  - fabula-ultima/goiany-incident
nivel: 10
rank: Campeão (4 ações)
especie: Fera / Mutação Radiativa
hp_max: 300
hp_atual: 300
mp_max: 80
mp_atual: 80
des: 10
int: 6
vig: 10
von: 6
defesa: 10
def_magica: 6
iniciativa: 12
fraqueza: Físico (VU)
relogio_chumbo: 0
---

# 🐕 Dogzilla (Cão Mutado pelo Césio)
![[Dogzilla_art.png|300]]
**Nível:** `VIEW[{nivel}]` | **Rank:** `VIEW[{rank}]` | **Espécie:** `VIEW[{especie}]`
*Traços: Dor Aguda, Fúria Descontrolada, Fogo Purpúreo, Tamanho Colossal.*

> *"Sob o fulgor violeta do Césio, a pele do cão racha e se retorce. Músculos hipertrofiados pulsam enquanto o ar ao redor estala com ozônio. Ele não uiva por fúria, mas pela agonia insuportável da matéria sendo consumida de dentro para fora."*

**VIG** d10 | **DES** d10 | **AST** d6 | **VON** d6
**PV:** 300 (Crise 150) | **PM:** 80 | **Iniciativa:** 12
**Defesa:** Física 10 | Mágica 6
**Afinidades:** ⚡ Abs (Raio) | ☠️ Abs (Veneno) | ⚔️ Vuln (Físico)

---
### ⚔️ Ataques & Ações
* **[C a C] Mordida Mutante:** 【DES + VIG】+1 | Dano: 【RA + 5】 Físico.
* **[Distância] Sopro de Césio (Laser):** 【DES + AST】+1 | Multi (2) | Dano: 【RA + 10】 Veneno.
  * *Efeito:* Alvos atingidos avançam +2 segmentos no Relógio de Dosimetria do grupo.

---
### ⚙️ Regras Especiais
* **Ações Múltiplas (Passiva):** Age **4 vezes** por rodada de conflito (substitui 4 soldados).
* **Lambida Radiativa (Reação):** Ao acertar o ataque *Mordida Mutante*, Dogzilla pode gastar **10 PM** para infligir a condição **Fraco** no alvo e avançar +2 segmentos no Relógio de Dosimetria do grupo.
* **Explosão Radiativa de Agonia (Ato Final):** Se derrotado sem que a *Contenção por Chumbo* tenha sido concluída, o núcleo no estômago do cão entra em colapso e explode, infligindo **+3 segmentos diretos** no Relógio de Dosimetria do grupo.
* **Relógio de Objetivo: Contenção por Chumbo** (`VIEW[{relogio_chumbo}]` / 4)
  `INPUT[slider(minValue(0), maxValue(4)):relogio_chumbo]`
  * *Ação Principal de Herói:* Teste 【AST + DES】 (Dif 10) usando vergalhões de chumbo espalhados na mina. Ao completar (4/4 sucessos), neutraliza o Sopro de Césio e desativa a Explosão Radiativa de Agonia.
