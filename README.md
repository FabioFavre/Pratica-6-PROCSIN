# 🌊 Prática 6 — Processamento de Sinais I
### Projeto de Filtros IIR

[![CEFET/RJ](https://img.shields.io/badge/CEFET%2FRJ-Engenharia%20de%20Controle%20e%20Automa%C3%A7%C3%A3o-1F3864?style=for-the-badge&logo=academia)](https://www.cefet-rj.br)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)
[![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)](https://colab.research.google.com)

---

## 📋 Sumário

- [Sobre a Prática](#-sobre-a-prática)
- [Exercícios](#-exercícios)
  - [Questão 1 — Blocos de 2ª Ordem](#-questão-1--blocos-básicos-de-2ª-ordem)
  - [Questão 2 — Filtros Passa-Faixas](#-questão-2--filtros-passa-faixas-em-cascata)
  - [Questão 3 — Filtros Rejeita-Faixas](#-questão-3--filtros-rejeita-faixas-em-paralelo)
  - [Questão 4 — Quantização](#-questão-4--quantização-e-estabilidade)
  - [Questão 5 — Recuperação de Áudio](#-questão-5--recuperação-de-sinais-de-áudio)
- [Estrutura do Repositório](#-estrutura-do-repositório)
- [Como Executar](#-como-executar)
- [Dependências](#-dependências)
- [Equipe](#-equipe)

---

## 📖 Sobre a Prática

Esta prática explora o projeto e implementação de **Filtros Digitais IIR (Infinite Impulse Response)**, focando no uso de estruturas modulares para processamento de sinais complexos.

**1. Projeto de Filtros IIR:** Implementação baseada em blocos de 2ª ordem (SOS), explorando as características de seletividade, estabilidade e largura de banda.

**2. Quantização & Implementação:** Estudo da sensibilidade numérica e estabilidade ao quantizar coeficientes em precisões reduzidas, comparando implementações diretas com cascatas.

> 💡 **Por que blocos de 2ª ordem?** Implementar filtros de alta ordem diretamente é sensível a erros de quantização. A decomposição em seções de 2ª ordem (cascata ou paralelo) minimiza a sensibilidade numérica e garante maior controle sobre a estabilidade.

---

## 🧪 Exercícios

### ⚙️ Questão 1 — Blocos Básicos de 2ª Ordem

**Notebook:** `Questão_1.ipynb`

Projeto de filtros elementares com $f_s = 20.000$ Hz.

#### O que foi feito

| Item | Tipo | Descrição |
|------|------|-----------|
| **(a)** | Passa-baixas | $f_c = 1000$ Hz |
| **(b)** | Passa-altas | $f_c = 2000$ Hz |
| **(c)** | Passa-faixas | $f_c = 7000$ Hz |
| **(d)** | Notch | $f_c = 3000$ Hz |

*Em todos os casos: Análise da função de transferência, resposta em frequência, diagrama de polos/zeros e influência do parâmetro $r$.*

---

### 🧱 Questão 2 — Filtros Passa-Faixas em Cascata

**Notebook:** `Questão_2.ipynb`

Projeto de um passa-faixas com $f_{c1} = 6000$ Hz e $f_{c2} = 8000$ Hz utilizando cascata de blocos de 2ª ordem.

* **Análise:** Comparação da resposta em frequência e diagrama de polos e zeros com o filtro passa-faixas simples da Questão 1.

---

### 🎛️ Questão 3 — Filtros Rejeita-Faixas em Paralelo

**Notebook:** `Questão_3.ipynb`

Projeto de um rejeita-faixas (band-stop) com $f_{c1} = 1000$ Hz e $f_{c2} = 4000$ Hz utilizando paralelo de blocos de 2ª ordem.

* **Análise:** Comparação com o filtro Notch da Questão 1, avaliando seletividade e largura de banda.

---

### 📉 Questão 4 — Quantização e Estabilidade

**Notebook:** `Questão_4.ipynb`

Realização de quantização dos coeficientes com $b \in \{2, 4, 8, 16, 32\}$ bits.

* **Foco:** Comparação da resposta em frequência e posição de polos/zeros entre o filtro original e versões quantizadas.
* **Verificação:** Análise de estabilidade e sensibilidade numérica ao quantizar o filtro resultante vs. quantizar bloco a bloco.

---

### 🎙️ Questão 5 — Recuperação de Sinais de Áudio

**Notebook:** `Questão_5.ipynb`

Remoção de interferências no sinal `handel.wav` contaminado:
$$y(t) = x(t) + 0.05 \cos(200\pi t) + 0.075 \sin(4000\pi t) + n(t)$$

#### Pipeline de filtragem

1. **Análise:** Identificação das interferências (senoidais e ruído branco) no domínio da frequência.
2. **Projeto:** Sistema em cascata de blocos IIR para recuperar $\hat{x}(t)$.
3. **Avaliação:**
    * **Quantitativa:** SNR, MSE e potência do ruído residual.
    * **Qualitativa:** Avaliação da inteligibilidade e impacto perceptual.
    * **Quantização:** Teste final com $b \in \{2, 4, 8, 16\}$ bits.

---

## 📁 Estrutura do Repositório

```text
Pratica-6-PROCSIN/
│
├── 📓 Questao_1.ipynb        # Filtros básicos (LPF, HPF, BPF, Notch)
├── 📓 Questao_2.ipynb        # Filtros em cascata
├── 📓 Questao_3.ipynb        # Filtros em paralelo
├── 📓 Questao_4.ipynb        # Análise de quantização
├── 📓 Questao_5.ipynb        # Recuperação de áudio
│
└── 📄 Aula_Prática_6.pdf     # Enunciado oficial da prática

---

## ▶️ Como Executar

### Opção 1 — Google Colab (recomendado)

Clique no badge abaixo para abrir diretamente no Colab:

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/jeanraposojesus-hue/Pratica-5-PROCSIN/blob/main/Questao_1.ipynb)

### Opção 2 — Execução local

```bash
# 1. Clone o repositório
git clone [https://github.com/seu-usuario/Pratica-6-PROCSIN.git](https://github.com/seu-usuario/Pratica-6-PROCSIN.git)
cd Pratica-6-PROCSIN

# 2. Instale as dependências
pip install numpy scipy matplotlib jupyter

# 3. Inicie o Jupyter
jupyter notebook
```

---

## 📦 Dependências

| Biblioteca | Versão mín. | Uso |
|------------|:-----------:|-----|
| `numpy` | 1.23+ | Operações matriciais |
| `scipy` | 1.9+ | Filtros IIR, processamento de áudio |
| `matplotlib` | 3.6+ | Resposta em frequência, polos/zeros |
| `jupyter` | 6.0+ | Ambiente de desenvolvimento |

---

## 👥 Equipe

<table>
  <tr>
    <td align="center">
      <b>Jean Raposo Soares de Jesus</b><br/>
      <a href="https://github.com/jeanraposojesus-hue">@jeanraposojesus-hue</a>
    </td>
    <td align="center">
      <b>Igor Pinheiro Torres</b>
    </td>
    <td align="center">
      <b>Fabio Luiz Cocco Favre da Silva</b><br/>
      <a href="https://github.com/FabioFavre">@FabioFavre</a>
    </td>
  </tr>
</table>

---

<div align="center">

**Disciplina:** Processamento de Sinais I · **Professor:** Rafael Chaves  
**Curso:** Engenharia de Controle e Automação · **Instituição:** CEFET/RJ  

📚 Repositório de referência do professor: [rafaelschaves/gele7317-proc-sin](https://github.com/rafaelschaves/gele7317-proc-sin)

</div>
