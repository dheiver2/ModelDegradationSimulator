# Simulador de Degradação de Modelo

## Descrição
Este projeto implementa um **Simulador de Degradação de Modelo** em Python, que demonstra o fenômeno de *Model Collapse* (ou degeneração de modelo) em aprendizado de máquina. O simulador gera dados sintéticos iterativamente, treina modelos em cada geração e avalia a degradação do desempenho ao longo do tempo, visualizando métricas como MSE (Erro Quadrático Médio), R² (Coeficiente de Determinação) e mudanças na distribuição dos dados.

## Funcionalidades
- Geração de dados originais com uma relação não-linear complexa.
- Treinamento de modelos Random Forest em cada geração.
- Geração de dados sintéticos para simular iterações.
- Avaliação de métricas de desempenho (MSE, R², variância, média, desvio padrão).
- Visualização gráfica da degradação do modelo e da evolução da distribuição dos dados.
- Resumo detalhado dos resultados da simulação.

## Requisitos
Para executar o simulador, você precisará das seguintes bibliotecas Python:
```bash
numpy
matplotlib
scikit-learn
seaborn
```

Você pode instalá-las usando o pip:
```bash
pip install numpy matplotlib scikit-learn seaborn
```

## Como Usar
1. Clone ou baixe este repositório.
2. Certifique-se de que as dependências estão instaladas.
3. Execute o script principal (`simulator.py`):
   ```bash
   python simulator.py
   ```
4. O script irá:
   - Executar a simulação com 100 gerações (configurável).
   - Gerar gráficos mostrando a degradação das métricas e a evolução da distribuição dos dados.
   - Imprimir um resumo detalhado no console.

## Estrutura do Código
- **Classe `ModelDegradationSimulator`**:
  - `__init__`: Inicializa o simulador com tamanho do dataset e nível de ruído.
  - `generate_original_data`: Gera dados iniciais com uma relação não-linear.
  - `train_model`: Treina um modelo Random Forest.
  - `generate_synthetic_data`: Cria dados sintéticos para a próxima geração.
  - `evaluate_model`: Avalia o desempenho do modelo.
  - `simulate_degradation`: Executa a simulação por várias gerações.
  - `plot_degradation_metrics`: Plota gráficos das métricas de desempenho.
  - `plot_data_distribution_evolution`: Visualiza a evolução da distribuição dos dados.
  - `print_degradation_summary`: Exibe um resumo dos resultados.

## Resultados Esperados
- **Gráficos**:
  - Métricas de desempenho (MSE, R², variância, média, desvio padrão) ao longo das gerações.
  - Histogramas mostrando a evolução da distribuição dos dados alvo (y).
- **Resumo**:
  - Comparação do MSE e R² inicial e final.
  - Percentual de degradação do desempenho.
  - Observações sobre o fenômeno de *Model Collapse*.

## Exemplo de Saída
```plaintext
Iniciando simulação de degradação de modelo...
Processando geração 0...
...
Processando geração 99...
Simulação concluída!

============================================================
RESUMO DA DEGRADAÇÃO DO MODELO
============================================================
Gerações simuladas: 100
MSE:
  Inicial: X.XXXX
  Final: Y.YYYY
  Degradação: +ZZ.ZZ%
R²:
  Inicial: X.XXXX
  Final: Y.YYYY
  Degradação: -ZZ.ZZ%
Variância dos dados:
  Inicial: X.XXXX
  Final: Y.YYYY
Observações:
• MSE crescente indica piora na capacidade preditiva
• R² decrescente confirma degradação do modelo
• Mudanças na variância mostram alteração na distribuição dos dados
• Este fenômeno é conhecido como 'Model Collapse' ou 'Degeneração de Modelo'
```

## Notas
- O código usa uma semente aleatória (`np.random.seed(42)`) para reproducibilidade.
- Ajuste os parâmetros `initial_data_size`, `noise_level` e `num_generations` para experimentar diferentes configurações.
- O fenômeno de *Model Collapse* ocorre devido à amplificação de erros ao longo das gerações de dados sintéticos.

## Licença
Este projeto é distribuído sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes (se aplicável).

## Contato
Para dúvidas ou sugestões, entre em contato pelo e-mail ou abra uma issue no repositório.
