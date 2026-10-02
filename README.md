# 🖨️ Calculadora de Impressão 3D

Ferramenta web para calcular o custo real de peças impressas em 3D e gerar orçamentos profissionais em PDF para clientes — direto no navegador, sem instalação e sem backend.

**[Abrir a calculadora »](https://iurycl.github.io/calculadora-impressao-3d/)**

## Recursos

- **Cálculo de custo por peça**, considerando filamento, energia, depreciação da impressora e mão de obra.
- **Orçamento com múltiplas peças**: adicione quantas peças forem necessárias e acompanhe o total em tempo real.
- **Geração de PDF profissional**, com dados da empresa (incluindo logo), dados do cliente, tabela de itens, condições de pagamento, prazo de entrega e validade do orçamento.
- **Parâmetros de custo configuráveis**: preço e peso do rolo de filamento, consumo da impressora, valor do kWh, valor e vida útil da impressora, tempos de fatiamento/acabamento, valor da hora de trabalho e margem de lucro.
- **Desconto por item** e suporte a múltiplos materiais (PLA, ABS, PETG, TPU, Nylon, ASA ou outro).
- 100% client-side: os dados não saem do seu navegador.

## Como usar

Não precisa instalar nada:

1. Acesse **[iurycl.github.io/calculadora-impressao-3d](https://iurycl.github.io/calculadora-impressao-3d/)**, ou baixe o repositório e abra o `index.html` diretamente no navegador.
2. Preencha os dados da empresa (nome é obrigatório) e, opcionalmente, adicione uma logo.
3. Preencha os dados do cliente e as especificações da peça (nome, peso e tempo de impressão são obrigatórios).
4. Ajuste os parâmetros de custo na seção "Configuração de Custos" conforme a sua impressora e seus valores.
5. Clique em **"Adicionar Peça ao Orçamento"** — repita para cada peça do orçamento.
6. Preencha condições de pagamento, prazo de entrega e validade do orçamento.
7. Clique em **"Gerar PDF Profissional"** para baixar o orçamento pronto para enviar ao cliente.

## Como o custo é calculado

Para cada peça adicionada, a calculadora soma quatro componentes de custo:

| Componente | Fórmula |
|---|---|
| Filamento | `(preço do rolo ÷ peso do rolo) × peso da peça` |
| Energia | `(consumo da impressora em W ÷ 1000) × tempo de impressão (h) × valor do kWh` |
| Depreciação | `(valor da impressora ÷ vida útil em horas) × tempo de impressão (h)` |
| Mão de obra | `((tempo de fatiamento + tempo de acabamento) ÷ 60) × valor da hora de trabalho` |

A soma desses quatro valores é o **subtotal**. Sobre o subtotal é aplicada a **margem de lucro** (%) configurada, e sobre o resultado é aplicado o **desconto do item** (%), chegando ao preço unitário. O preço final da peça é `preço unitário × quantidade`, e o orçamento total é a soma de todas as peças adicionadas.

## Tecnologias

- HTML, CSS e JavaScript puro — nenhum framework, sem etapa de build.
- [jsPDF](https://github.com/parallax/jsPDF) (via CDN) para geração do PDF no navegador.

## Estrutura

```
index.html   # aplicação inteira: markup, estilos e lógica
```

## Contribuindo

Pull requests são bem-vindos! A branch principal é protegida — toda alteração precisa passar por Pull Request e ser aprovada antes do merge.

## Licença

Distribuído sob a licença MIT. Veja [LICENSE](LICENSE) para mais detalhes.
