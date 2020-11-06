## API dos serviços da plataforma digital única
Descreve a especificação da API relativa à partilha de estatísticas sobre os utilizadores e reações sobre os serviços da plataforma digital única em conformidade com o Regulamento (UE) 2018/1724 do Parlamento Europeu.
do Conselho.

Existem cinco APIS no âmbito deste projecto para tranferir dados  da ferramenta comum ou das ferramentas comuns dos estados membros para processamento, análise e visualização.


# Estatísticas

## Serviços Informativos
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

## Serviços Online
- Avaliação do serviço (1 a 5 estrelas) – campo obrigatório *
- Ajude-nos a melhorar (caixa de texto aberta) – campo opcional*
- Dados de contexto
- Questionário adicional
- Frequência uma vez por mês

## Serviços Informativos

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

# 	API para o identificador único
Esta API tem o objetivo de gerar um ID único para ser usado para chamar as outras APIS no envio de informação estatística ou de retorno de informação para um intervalo de referência.
Amtes de invocar as restantes APIS devemos invocar esta API para gerar o número único primeiro.


 O ID único recebido na resposta vai ser utilizdo para chamar as outras API's e quando forem invocadas as restantes APIS devemos ter conta os seguintes pontos:
 - Um intervalo de referência corresponde a um ID único
 - A entidade competente deve manter um mapeamento entre o ID único e o intervalo de referência que foi utilizado
 - Se alguma das APIS for invocada para reenviar os dados de um intervalo de referência  devemos usar um ID único e não voltar a chamar a API de identificador único.
 - Se a entidade necessitar de alterar informamção já enviada para um intervalo de referência, deve usar o mesmo  Unique ID should be used again.
 - A informação que for reenviada com o mesmo ID único vai ser sobreposta.
 
 Exemplo de resposta:
```markdown
 {"unique-id": "838a89cd-f096-4847-be3f-a053ef9749bf"}
```

