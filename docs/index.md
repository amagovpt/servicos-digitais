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


<table>
  <tr>
    <th colspan="4">Pedido</th>  
  </tr>
  <tr>
    <th>Parâmetros</th>
    <th>Tipo</th>
    <th>Obrigatório (Sim/ Não)</th>
    <th>Comentários</th>
  </tr>
  <tr>
    <td>isSDG</td>
    <td>boolean</td>
    <td>Sim</td>
    <td>A informação enviada está a ser enviada no âmbito do SDG?</td>
  </tr>
  <tr>
    <td>informationServiceStats</td>
    <td>Object</td>
    <td>Sim</td>
    <td>O objeto que representa os serviços informativos</td>
  </tr>
  <tr>
    <td>uniqueId</td>
    <td>string</td>
    <td>Sim</td>
    <td> O identificador único para o envio das estatísticas dos  serviços informativos para um intervalo de referência específico que é obtido através da api de Identificador Único</td>
  </tr>
  <tr>
    <td>referencePeriod</td>
    <td>Object</td>
    <td>Sim</td>
    <td>Representação do intervalo de referência com a data de ínicio e de fim.</td>
  </tr>
  <tr>
    <td>startDate</td>
    <td>string</td>
    <td>Sim</td>
    <td>Data de ínicio do intervalo de referência</td>
  </tr>
  <tr>
    <td>endDate</td>
    <td>string</td>
    <td>Sim</td>
    <td>Data de fim do intervalo de referência</td>
  </tr>
  <tr>
    <td>transferDate</td>
    <td>string</td>
    <td>Sim</td>
    <td>Data e hora em que estamos a invocar a API</td>
  </tr>
  <tr>
    <td>transferType</td>
    <td>String (enum)</td>
    <td>Sim</td>
    <td>Tipo de transferência de dados, neste caso será "API"</td>
  </tr>
  <tr>
    <td>nbEntries</td>
    <td>integer</td>
    <td>Sim</td>
    <td>Número de entradas , incluindo todas as fontes de URL's para as estatísticas que estão a ser enviadas</td>
  </tr>
  <tr>
    <td>sources</td>
    <td>Array of Objects</td>
    <td>Sim</td>
    <td>Representação da informação estatística sobre uma URL . Um objeto pode referenciar vários URLs</td>
  </tr>
  <tr>
    <td>source</td>
    <td>object</td>
    <td>Sim</td>
    <td>Dados estatísticos</td>
  </tr>
  <tr>
    <td>sourceUrl</td>
    <td>string</td>
    <td>Sim</td>
    <td>URL através do qual os dados estão a ser obtidos.</td>
  </tr>
  <tr>
    <td>statistics</td>
    <td>Objects</td>
    <td>Sim</td>
    <td>Representação dos dados estatísticos para um URL
	An object representing the statistical information for one particular source URL.</td>
  </tr>
  <tr>
    <td>nbVisits</td>
    <td>integer</td>
    <td>Sim</td>
    <td>Número total de visitas ao URL</td>
  </tr>
  <tr>
    <td>originatingCountry</td>
    <td>string</td>
    <td>Sim</td>
    <td>País de onde as visitas são originadas no acesso ao URL.</td>
  </tr>
  <tr>
    <td>country</td>
    <td>String enum</td>
    <td>Sim</td>
    <td>Código ‘ISO 3166-1 alpha-2’ do País
	
Enumerado:

<ul>
  <li>AT</li>
  <li>BE</li>
  <li>BG</li>
  <li>CY</li>
  <li>CZ</li>
  <li>DE</li>
  <li>DK</li>
  <li>EE</li>
  <li>EL</li>
  <li>ES</li>
  <li>FI</li>
  <li>FR</li>
  <li>HR</li>
  <li>HU</li>
  <li>IE</li>
  <li>IS</li>
  <li>LT</li>
  <li>LI</li>
  <li>LU</li>
  <li>LV</li>
  <li>MT</li>
  <li>NL</li>
  <li>NO</li>
  <li>PL</li>
  <li>PT</li>
  <li>RO</li>
  <li>SE</li>
  <li>SI</li>
  <li>SK</li>
</ul>
    	
 </td>
  </tr>
  <tr>
    <td>deviceType</td>
    <td>string</td>
    <td>Sim</td>
    <td>Tipo de dispositivo utilizado para visitar o URL
<ul>
 <li>Mobile</li>
  <li>Tablet</li>
  <li>PC</li>
</ul>
 </td>
  </tr>

  <tr>
    <td colspan="4" >Resposta</td>
 
  </tr>
  <tr>
    <th colspan="2">Código</th>
    <th colspan="2">Mensagem</th>
   
  </tr>
  <tr>
    <td>200</td>
    <td>OK</td>
   
  </tr>
</table>


 Exemplo de payload:
```markdown
 
  "isSDG": true,
  "content": [
    {
      "uniqueId": "123456789",
      "referencePeriod": {
        "startDate": "2020-01-01 00:00:00",
        "endDate": "2020-01-31 00:00:00"
      },
      "transferDate": "2020-02-01 00:00:00",
      "transferType": "API",
      "nbEntries": 1,
      "sources": [
        {
          "source": {
            "sourceUrl": "http://www1.ipq.pt/PT/IPQ/Pages/IPQ.aspx",
            "statistics": [
              {
                "deviceType": "Mobile",
                "nbVisits": 1,
                "originatingCountry": "TR"
              },
              {
                "deviceType": "PC",
                "nbVisits": 1,
                "originatingCountry": "IQ"
              }
            ]
          }
        }
      ]
    },
    {
      "uniqueId": "987654321",
      "referencePeriod": {
        "startDate": "2020-02-01 00:00:00",
        "endDate": "2020-02-29 00:00:00"
      },
      "transferDate": "2020-03-01 00:00:00",
      "transferType": "API",
      "nbEntries": 1,
      "sources": [
        {
          "source": {
            "sourceUrl": "http://www1.ipq.pt/PT/IPQ/Pages/IPQ.aspx",
            "statistics": [
              {
                "deviceType": "Mobile",
                "nbVisits": 1,
                "originatingCountry": "TR"
              },
              {
                "deviceType": "Tablet",
                "nbVisits": 1,
                "originatingCountry": "RS"
              }
            ]
          }
        }
      ]
    }
  ]
}

```

## Serviços de Assistência
- Número de pedidos
- Assunto
- Categorias 
     - Cidadãos ou Negócio
	 - Transfronteiriço ou nacional
- Tempo médio de resposta num período de 6 meses
- Dados de contexto
- Frequência uma vez por mês



 Exemplo de payload:
 
 
<table>
  <tr>
    <th colspan="4">Pedido</th>   
  </tr>
  <tr>
    <th>Parâmetros</th>
    <th>Tipo</th>
    <th>Obrigatório (Sim/ Não)</th>
    <th>Comentários</th>
  </tr>
  <tr>
    <td>isSDG</td>
    <td>boolean</td>
    <td>Sim</td>
    <td>A informação enviada está a ser enviada no âmbito do SDG?</td>
  </tr>
  <tr>
    <td>assistanceServiceStats</td>
    <td>Object</td>
    <td>Sim</td>
    <td>Representação dos serviços de assistência</td>
  </tr>
   <tr>
    <td>uniqueId</td>
    <td>string</td>
    <td>Sim</td>
    <td>O identificador único para o envio das estatísticas dos  serviços informativos para um intervalo de referência específico que é obtido através da api de Identificador Único</td>
  </tr>
  <tr>
    <td>referencePeriod</td>
    <td>object</td>
    <td>Sim</td>
    <td>Intervalo de referência</td>
  </tr>
 <tr>
    <td>startDate</td>
    <td>string</td>
    <td>Sim</td>
    <td>Data de ínicio do intervalo de referência</td>
  </tr>
  <tr>
    <td>endDate</td>
    <td>string</td>
    <td>Sim</td>
    <td>Data de fim do intervalo de referência</td>
  </tr>
 <tr>
    <td>transferDate</td>
    <td>string</td>
    <td>Sim</td>
    <td>Data e hora em que estamos a invocar a API</td>
  </tr>
  <tr>
    <td>transferType</td>
    <td>String (enum)</td>
    <td>Sim</td>
    <td>Tipo de transferência de dados, neste caso será 'API'</td>
  </tr>
 
</table>
 
```markdown

{
  "isSDG": true,
  "content": [
    {
      "uniqueId": "123456789",
      "referencePeriod": {
        "startDate": "2020-01-01 00:00:00",
        "endDate": "2020-01-31 00:00:00"
      },
      "transferDate": "2020-02-01 00:00:00",
      "transferType": "API",
      "nbEntries": 1,
      "sources": [
        {
          "source": {
            "sourceUrl": "https://www.iprhelpdesk.eu/",
            "statistics": [
              {
                "avgResponseTime": 223200000,
                "categoryOfUser": "business",
                "nbRequests": 1,
                "situationOfUser": "national",
                "subjectMatter": "Starting cross-border business"
              },
              {
                "avgResponseTime": 226800000,
                "categoryOfUser": "citizen",
                "nbRequests": 2,
                "situationOfUser": "cross-border",
                "subjectMatter": "Starting education"
              }
            ]
          }
        }
      ]
    },
    {
      "uniqueId": "987654321",
      "referencePeriod": {
        "startDate": "2020-02-01 00:00:00",
        "endDate": "2020-02-29 00:00:00"
      },
      "transferDate": "2020-03-01 00:00:00",
      "transferType": "API",
      "nbEntries": 1,
      "sources": [
        {
          "source": {
            "sourceUrl": "https://www.iprhelpdesk.eu/",
            "statistics": [
              {
                "avgResponseTime": 244800000,
                "categoryOfUser": "business",
                "nbRequests": 2,
                "situationOfUser": "national",
                "subjectMatter": "Starting cross-border business"
              },
              {
                "avgResponseTime": 147600000,
                "categoryOfUser": "citizen",
                "nbRequests": 2,
                "situationOfUser": "cross-border",
                "subjectMatter": "Starting education"
              }
            ]
          }
        }
      ]
    }
  ]
}
```

# Retorno de Informação de primeiro de nível e de segundo nível
```markdown
{
  "isSDG": true,
  "content": [
    {
      "uniqueId": "123456789",
      "referencePeriod": {
        "startDate": "2020-01-01 00:00:00",
        "endDate": "2020-01-31 00:00:00"
      },
      "transferDate": "2020-02-01 00:00:00",
      "transferType": "API",
      "nbEntries": 2,
      "feedbacks": [
        {
          "feedback": {
            "category": "Procedure",
            "rating": 1,
            "source": "www.konsumenteuropa.se",
            "foundInformation": "Yes",
            "helpUsImprove": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
          }
        },
        {
          "feedback": {
            "category": "Information",
            "rating": 2,
            "source": "http://www.amsfl.li/ ",
            "foundInformation": "Partly",
            "helpUsImprove": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
          }
        }
      ]
    },
    {
      "uniqueId": "98765421",
      "referencePeriod": {
        "startDate": "2020-02-01 00:00:00",
        "endDate": "2020-02-29 00:00:00"
      },
      "transferDate": "2020-03-01 00:00:00",
      "transferType": "API",
      "nbEntries": 2,
      "feedbacks": [
        {
          "feedback": {
            "category": "Assistance",
            "rating": 5,
            "source": "http://www.moi.gov.cy/moi/moi.nsf/All/6D6489AF90B208F4C2257B89002E03F3",
            "foundInformation": "Partly",
            "helpUsImprove": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
          }
        },
        {
          "feedback": {
            "category": "Procedure",
            "rating": 1,
            "source": "https://www.odrcontactpoint.uk/",
            "foundInformation": "Yes",
            "helpUsImprove": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
          }
        }
      ]
    }
  ]
}

```


## Serviços de Assistência

Exemplo de payload:
```markdown
{
  "isSDG": true,
  "content": [
    {
      "uniqueId": "123456789",
      "referencePeriod": {
        "startDate": "2020-01-01 00:00:00",
        "endDate": "2020-01-31 00:00:00"
      },
      "transferDate": "2020-02-01 00:00:00",
      "transferType": "API",
      "nbEntries": 2,
      "feedbacks": [
        {
          "feedback": {
            "category": "Procedure",
            "rating": 1,
            "source": "www.konsumenteuropa.se",
            "foundInformation": "Yes",
            "helpUsImprove": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
          }
        },
        {
          "feedback": {
            "category": "Information",
            "rating": 2,
            "source": "http://www.amsfl.li/ ",
            "foundInformation": "Partly",
            "helpUsImprove": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
          }
        }
      ]
    },
    {
      "uniqueId": "98765421",
      "referencePeriod": {
        "startDate": "2020-02-01 00:00:00",
        "endDate": "2020-02-29 00:00:00"
      },
      "transferDate": "2020-03-01 00:00:00",
      "transferType": "API",
      "nbEntries": 2,
      "feedbacks": [
        {
          "feedback": {
            "category": "Assistance",
            "rating": 5,
            "source": "http://www.moi.gov.cy/moi/moi.nsf/All/6D6489AF90B208F4C2257B89002E03F3",
            "foundInformation": "Partly",
            "helpUsImprove": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
          }
        },
        {
          "feedback": {
            "category": "Procedure",
            "rating": 1,
            "source": "https://www.odrcontactpoint.uk/",
            "foundInformation": "Yes",
            "helpUsImprove": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
          }
        }
      ]
    }
  ]
}

```

## Serviços Informativos

- Encontrou o que procurava? (opções exclusivas: SIM/NÃO/PARCIALMENTE) 
- Avaliar esta página (Pontuação através de estrelas: de 1 a 5)
- Ajude-nos a melhorar (caixa de texto aberta) – campo opcional*
- Dados de contexto
- Questionário adicional
- Frequência uma vez por mês



## Serviços de Assistência

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

