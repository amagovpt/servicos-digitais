## API dos serviços da plataforma digital única
Descreve a especificação da API relativa à partilha de estatísticas sobre os utilizadores e reações sobre os serviços da plataforma digital única em conformidade com o Regulamento (UE) 2018/1724 do Parlamento Europeu.
do Conselho.

Existem quatro APIS no âmbito deste projecto para tranferir dados  da ferramenta comum ou das ferramentas comuns dos estados membros para processamento, análise e visualização.


One additional API is also foreseen to provide the message ID to be used when calling any of the main four APIs above.  
In the table below is included a summary of the payloads to be transferred via the APIs and frequency of transmission. 
The API data definition files, so called “swaggers”, are created in a way to contain this information as outlined below.


# Estatísticas

Serviços Informativos
- Número de visitas
- Países dos utilizadores que visitam as páginas web
- Dispositivos utilizados para visitar as páginas web
- Dados de contexto
- Frequência uma vez por mês

Serviços de Assistência
- Número de pedidos
- Assunto
- Categorias 
     - Cidadãos ou Negócio
	 - Transfronteiriço ou nacional
- Tempo médio de resposta num período de 6 meses
- Dados de contexto
- Frequência uma vez por mês



# Retorno de informação e qualidade

Serviços Online
- Avaliação do serviço (1 a 5 estrelas) – campo obrigatório *
- Ajude-nos a melhorar (caixa de texto aberta) – campo opcional*
- Dados de contexto
- Questionário adicional
- Frequência uma vez por mês

Serviços Informativos

- Encontrou o que procurava? (opções exclusivas: SIM/NÃO/PARCIALMENTE) 
- Avaliar esta página (Pontuação através de estrelas: de 1 a 5)
- Ajude-nos a melhorar (caixa de texto aberta) – campo opcional*
- Dados de contexto
- Questionário adicional
- Frequência uma vez por mês


Serviços de Assistência

- Avaliação do serviço fornecido (1 a 5 estrelas) – campo obrigatório *
- Ajude-nos a melhorar (caixa de texto aberta) – campo opcional*
- Dados de contexto
- Questionário adicional
- Frequência uma vez por mês

