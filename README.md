# 🚀 Desvio de Asteroides (V7 - Final)

## 🌌 Visão Geral do Jogo

**Desvio de Asteroides** é um jogo arcade 2D de sobrevivência focado na destruição de ameaças e coleta de *power-ups*. Desenvolvido em **JavaScript Vanilla** utilizando a **Canvas API** para renderização. O objetivo é sobreviver o maior tempo possível e atingir a maior pontuação, desviando e destruindo os asteroides que caem.

---

## 💻 Controles

| Ação | Teclas Principais | Teclas Alternativas |
| :--- | :--- | :--- |
| **Mover para Cima** | **W** | Seta Cima (↑) |
| **Mover para Baixo** | **S** | Seta Baixo (↓) |
| **Mover para Esquerda** | **A** | Seta Esquerda (←) |
| **Mover para Direita** | **D** | Seta Direita (→) |
| **Atirar** | **ESPAÇO** | **ESPAÇO** |

---

## ⚙️ Mecânicas de Jogo

### Dificuldade
A dificuldade é dinâmica: a cada **50 pontos** alcançados, a velocidade e a taxa de surgimento dos asteroides são escaladas.

### Sistema de Vida e Dano
* A nave possui 5 pontos de vida (`maxHealth: 5`).
* Após sofrer dano, a nave se torna **Invulnerável** por 60 frames (aproximadamente 1 segundo), sinalizado pelo efeito de piscar.
* **Asteroides Pesados** (`HeavyAsteroid`) exigem 3 acertos para serem destruídos e causam mais dano.

### Power-ups
Os power-ups têm uma chance de 15% de cair após a destruição de um asteroide.
1.  **Fogo Rápido (Rapid Fire):** Reduz o *delay* entre os disparos.
2.  **Tiro Triplo (Triple Shot):** Permite disparar três projéteis simultaneamente.

---

## 🛠️ Arquitetura Técnica

O jogo é executado por um **Game Loop** baseado em `requestAnimationFrame`, que garante que as funções `update()` (lógica e física) e `draw()` (renderização) sejam chamadas de forma otimizada para o navegador.

### Estrutura de Classes
* **`Player`:** Objeto central para a nave, controlando estado de saúde e posição.
* **`Asteroid` e `HeavyAsteroid`:** Classes para as ameaças. `HeavyAsteroid` utiliza herança (`extends Asteroid`) para implementar múltiplos pontos de vida.
* **`Bullet`:** Gerencia projéteis.
* **`PowerUp`:** Gerencia itens coletáveis.

### Detecção de Colisão
A colisão entre a nave/tiros e asteroides é verificada utilizando a fórmula da distância euclidiana (teorema de Pitágoras) para determinar se a distância entre os centros das entidades é menor que a soma de seus raios (ou metades de largura/altura).

---

## 🔗 Referências

* Desenvolvimento do Game Loop: [MDN Web Docs - requestAnimationFrame](https://developer.mozilla.org/pt-BR/docs/Web/API/window/requestAnimationFrame)
* Renderização Gráfica: [MDN Web Docs - Canvas API](https://developer.mozilla.org/pt-BR/docs/Web/API/Canvas_API)
* Formato README.md: [GitHub Documentation - Mastering Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
