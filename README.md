# Veiculos
Projeto de Visão Computacional embarcada (Edge AI) para contagem e classificação de veículos

O modelo de visão computacional, que detectou, contou e classificou foi criado e executado no Google Colab, constando o compartilhamento em Aplicativo/colab.

Os arquivos que foram utilizados: imagem e vídeo, estão em /Dados.

Os resultados gerados estão em: /Resultados.

Foi executado um modelo para imagem, que detectou, contou e classificou os veículos, porém, não atendem o fluxo em tempo real, assim, precisamos de um video. Também foram geradas estatísticas e graficos.

Para o video Reduzido, foram executados 3 modelos, com 141 frames, sendo o resultado:
1º - Detecta os veículos, evidência em resultados.
Demorou 9 minutos

2º Detecção, RASTREAMENTO e CONTAGEM de veículos - evidência em resultados.
Diferença em relação à versão anterior:
- Antes: contava toda detecção em todo frame (um mesmo carro era contado
  dezenas de vezes ao longo do vídeo).
- Agora: cada veículo recebe um ID único que é seguido entre os frames,
  então cada veículo é contado apenas UMA VEZ, independente de quantos
  frames ele aparece.
Demorou 15 minutos

3º Pipeline completo de análise de tráfego em vídeo - evidência em resultados.
  1. Detecção + classificação (carro, moto, ônibus, caminhão) - YOLOv8
  2. Rastreamento (ByteTrack) - cada veículo recebe um ID único
  3. Contagem de veículos únicos por classe
  4. Exportação de CSV com o histórico de cada veículo
  5. Relatório de texto com métricas de fluxo
  6. Gráficos (barras, pizza e fluxo ao longo do tempo)
Demorou 10 minutos

O modelo utilizado foi o YOLO, pois ele:
- Detecta, localiza e classifica objetos de imagem e vídeo (sem precisar de uma arquitetura adicional)
- Trabalha com RaspBerry PI 5;
- Boa precisão na deteção;
- Apresentou baixa latência;
- Capacidade de detectar vários objetos, quando esses estão juntos.

  
