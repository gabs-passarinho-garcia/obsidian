---
tags:
  - projeto/rpg
  - campanha/fabula-ultima
  - adversarios
  - fabula-ultima/goiany-incident
sistema: Fabula Ultima
tipo: Fichas
---

# 🧌 Adversários de Goiany

# 🐕 Dogzilla (Cão Mutado pelo Césio)
![[Dogzilla_art.png|300]]
**Nível 10 | Campeão (3 a 6 PJ) | Fera / Mutação Radiativa**
*Traços: Dor Aguda, Fúria Descontrolada, Fogo Purpúreo, Tamanho Colossal.*

**VIG** d10 | **DES** d10 | **AST** d6 | **VON** d6
**PV:** 300 (Crise 150) | **PM:** 80 | **Iniciativa:** 15
**Defesa:** Física 10 | Mágica 6
**Afinidades:** ⚡ Abs (Raio) | ☠️ Abs (Veneno) | ⚔️ Vuln (Físico)

---
### ⚔️ Ataques & Ações
* **[C a C] Mordida Mutante:** 【DES + VIG】+1 | Dano: 【RA + 5】 Físico.
* **[Distância] Sopro de Césio (Laser):** 【DES + AST】+1 | Multi (2) | Dano: 【RA + 10】 Veneno.
  * *Efeito:* Alvos atingidos sofrem o efeito imediato de avançar **+2 segmentos no Relógio de Dosimetria** do grupo.

---
### ⚙️ Regras Especiais
* **Lambida Radiativa (Reação):** Ao acertar o ataque *Mordida Mutante*, Dogzilla pode gastar 20 PM para infligir o status **Fraco** no alvo e adicionar +2 segmentos diretos no Relógio de Dosimetria.
* **Explosão Radiativa de Agonia:** Se derrotado sem a conclusão da *Contenção por Chumbo*, a Relíquia expõe seu núcleo e causa uma onda radiativa terminal, adicionando **+3 segmentos** de Dosimetria na party.
* **Relógio de Objetivo: Contenção por Chumbo** (`VIEW[{relogio_chumbo}]` / 4)
  `INPUT[slider(minValue(0), maxValue(4)):relogio_chumbo]`
  * *Ação Principal dos Heróis:* Teste 【AST + DES】 (Dif 10) usando vigas/vergalhões de chumbo espalhados na mina. Ao acumular 4 sucessos, o Sopro de Césio é desativado e a Explosão Radiativa final é completamente prevenida.

---

# 👥 Horda de Goiany (Moradores Desesperados)
![[Horde_art.png|300]]
**Nível 5 | Soldado (Horda) | Humanoide**
*Traços: Desesperados, Ignorantes, Enfurecidos, Armados com Ferramentas Agrícolas.*

**VIG** d8 | **DES** d8 | **AST** d8 | **VON** d8
**PV:** 60 (Crise 30) | **PM:** 45 | **Iniciativa:** 5
**Defesa:** Física 11 | Mágica 8
**Afinidades:** 🔥 Vuln (Fogo) | 💧 Res (Água)

---
### ⚔️ Ataques & Ações
* **[C a C] Enxame de Ferramentas:** 【DES + VIG】 | Dano: 【RA + 12】 Físico.

---
### ⚙️ Regras Especiais
* **Massa Desgovernada (Passiva):** Se o Relógio de Atitude da Vila estiver no nível **Hostil (0)**, a Horda recebe bônus de +2 em testes de Precisão e causa +5 de Dano Físico adicional por desespero cego.
* **Superstição Vulnerável (Estratégia Social):** Um herói pode gastar uma Ação Principal e fazer um teste de 【AST + VON】 contra a Defesa Mágica da Horda (8) para demonstrar um fenômeno lógico ou citação sagrada. Em caso de sucesso, a Horda fica hesitando e perde sua próxima ação de combate.