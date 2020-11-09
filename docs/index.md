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
    <td>Request</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Parameter</td>
    <td>Type</td>
    <td>Required (Yes / No)</td>
    <td>Notes</td>
  </tr>
  <tr>
    <td>isSDG</td>
    <td>boolean</td>
    <td>Yes</td>
    <td>Is this information associated with the group of services related to SDG?</td>
  </tr>
  <tr>
    <td>informationServiceStats</td>
    <td>Object</td>
    <td>Yes</td>
    <td>An object representing statistics on information services.</td>
  </tr>
  <tr>
    <td>uniqueId</td>
    <td>string</td>
    <td>Yes</td>
    <td>Unique ID for information services statistics submission for a specific reference period received from the UniqueID web API call.</td>
  </tr>
  <tr>
    <td>referencePeriod</td>
    <td>Object</td>
    <td>Yes</td>
    <td>Container of the Start Date and End Date of the reference period.</td>
  </tr>
  <tr>
    <td>startDate</td>
    <td>string</td>
    <td>Yes</td>
    <td>Start Date of the reference period.</td>
  </tr>
  <tr>
    <td>endDate</td>
    <td>string</td>
    <td>Yes</td>
    <td>End Date of the reference period.</td>
  </tr>
  <tr>
    <td>transferDate</td>
    <td>string</td>
    <td>Yes</td>
    <td>Date Time when the web API is called</td>
  </tr>
  <tr>
    <td>transferType</td>
    <td>String (enum)</td>
    <td>Yes</td>
    <td>Transfer type should be used as ‘API’ to call this web service.</td>
  </tr>
  <tr>
    <td>nbEntries</td>
    <td>integer</td>
    <td>yes</td>
    <td>No of total entries including all source URL for which the statistics are sent.</td>
  </tr>
  <tr>
    <td>sources</td>
    <td>Array of Objects</td>
    <td>Yes</td>
    <td>An object representing statistical information about one source URL. Array of objects because a given Reference Period is associated to several URLs.</td>
  </tr>
  <tr>
    <td>source</td>
    <td>object</td>
    <td>Yes</td>
    <td>Object holding the statistical data</td>
  </tr>
  <tr>
    <td>sourceUrl</td>
    <td>string</td>
    <td>Yes</td>
    <td>URL for which the statistics is collected.</td>
  </tr>
  <tr>
    <td>statistics</td>
    <td>Objects</td>
    <td>Yes</td>
    <td>An object representing the statistical information for one particular source URL.</td>
  </tr>
  <tr>
    <td>nbVisits</td>
    <td>integer</td>
    <td>Yes</td>
    <td>Total number of visits to the URL</td>
  </tr>
  <tr>
    <td>originatingCountry</td>
    <td>string</td>
    <td>Yes</td>
    <td>Country from where the visits are originated to the URL.</td>
  </tr>
  <tr>
    <td>country</td>
    <td>String enum</td>
    <td>Yes</td>
    <td>This field holds the country codes as per the ‘ISO 3166-1 alpha-2’.
enum:
    	- AT
    	- BE
    	- BG
    	- CY
        - CZ
    	- DE
    	- DK
    	- EE
    	- EL
    	- ES
    	- FI
    	- FR
    	- HR
    	- HU
    	- IE
    	- IS
    	- IT
    	- LI
    	- LT
    	- LU
    	- LV
    	- MT
    	- NL
    	- NO
    	- PL
    	- PT
    	- RO
    	- SE
    	- SI
    	- SK
    	
 </td>
  </tr>
  <tr>
    <td>deviceType</td>
    <td>string</td>
    <td>Yes</td>
    <td>Type of Device used to visit the URL
-          Mobile
-          Tablet
-          PC
 </td>
  </tr>
  <tr>
    <td> </td>
    <td> </td>
    <td> </td>
    <td> </td>
  </tr>
  <tr>
    <td>Response</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>Code</td>
    <td>Message</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>200</td>
    <td>OK</td>
    <td></td>
    <td></td>
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
- Número de pedidos
- Assunto
- Categorias 
     - Cidadãos ou Negócio
	 - Transfronteiriço ou nacional
- Tempo médio de resposta num período de 6 meses
- Dados de contexto
- Frequência uma vez por mês

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

