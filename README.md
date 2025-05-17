# ALura2025
Curso de imersão de IA com a Alura e o Google Gemini
# Agente de Planejamento de Gastos de Viagem Internacional

Este é um agente Python projetado para calcular estimativas de gastos para viagens internacionais, levando em consideração diversos fatores fornecidos pelo usuário.

## Funcionalidades

O agente recebe os seguintes dados como entrada:

* **Tópico:** O assunto principal da viagem (e.g., férias, negócios).
* **País:** O país de destino da viagem.
* **Perfil:** O estilo de viagem desejado (`mochileiro`, `econômico`, `confortável`, `luxuoso`).
* **Data de Início da Viagem:** A data de partida da viagem (formato YYYY-MM-DD).
* **Data de Retorno da Viagem:** A data de retorno da viagem (formato YYYY-MM-DD).
* **Número de Adultos:** O número de viajantes adultos.
* **Número de Crianças:** O número de crianças viajando.

Com base nesses dados e no perfil do buscador definido, o agente realiza as seguintes ações:

1.  **Determina o Destino:** Se uma cidade específica não for fornecida no `país`, o agente escolherá uma cidade relevante dentro do país para a análise.
2.  **Seleciona Interesses:** Escolhe automaticamente dois interesses específicos dentre `Gastronomia`, `Museus`, `Aventura` e `Compras` para alocar o orçamento.
3.  **Pesquisa de Custos:** Utiliza a ferramenta de busca do Google (`google_search`) para obter informações atualizadas sobre os custos de viagem, respeitando as datas fornecidas e focando em até 4 opções relevantes por estilo de viagem. A pesquisa considera preço, categoria e avaliações recentes (máximo de três meses da data atual). Avaliações com pouca informação ou entusiasmo são descartadas em favor de avaliações mais detalhadas.
4.  **Calcula Estimativa Detalhada:** Gera um orçamento detalhado por categoria:
    * Voos
    * Aluguel de Carro (se aplicável)
    * Hotéis/Hospedagem
    * Refeições
    * Atrações Turísticas e Atividades
    * Transporte Local
    * Seguro Viagem
    * Visto e Taxas de Entrada (se aplicável)
    * Comunicações
    * Emergências/Imprevistos
    * Compras/Souvenirs
    * Outros
5.  **Conversão de Moedas:** Converte o custo total para a moeda de origem do viajante (assumindo BRL) e para a moeda local do destino, utilizando taxas de câmbio atualizadas obtidas através da ferramenta de busca.
6.  **Apresenta o Orçamento:** Exibe o orçamento detalhado por categoria e o custo total em ambas as moedas.
7.  **Oferece Dicas:** Fornece dicas de economia e personalização da viagem.

## Perfil do Buscador
