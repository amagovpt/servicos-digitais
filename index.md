<<<<<<< HEAD
---
layout: default
title: Home
nav_order: 1
description: "Just the Docs is a responsive Jekyll theme with built-in search that is easily customizable and hosted on GitHub Pages."
permalink: /
---
=======
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
>>>>>>> 788a28789561f035c40fb66ef8241891b168ea88

# Focus on writing good documentation
{: .fs-9 }

Just the Docs gives your documentation a jumpstart with a responsive Jekyll theme that is easily customizable and hosted on GitHub Pages.
{: .fs-6 .fw-300 }

[Get started now](#getting-started){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 } [View it on GitHub](https://github.com/pmarsceill/just-the-docs){: .btn .fs-5 .mb-4 .mb-md-0 }

---

## Getting started

### Dependencies

Just the Docs is built for [Jekyll](https://jekyllrb.com), a static site generator. View the [quick start guide](https://jekyllrb.com/docs/) for more information. Just the Docs requires no special plugins and can run on GitHub Pages' standard Jekyll compiler. The [Jekyll SEO Tag plugin](https://github.com/jekyll/jekyll-seo-tag) is included by default (no need to run any special installation) to inject SEO and open graph metadata on docs pages. For information on how to configure SEO and open graph metadata visit the [Jekyll SEO Tag usage guide](https://jekyll.github.io/jekyll-seo-tag/usage/).

### Quick start: Use as a GitHub Pages remote theme

1. Add Just the Docs to your Jekyll site's `_config.yml` as a [remote theme](https://blog.github.com/2017-11-29-use-any-theme-with-github-pages/)
```yaml
remote_theme: pmarsceill/just-the-docs
```
<small>You must have GitHub Pages enabled on your repo, one or more Markdown files, and a `_config.yml` file. [See an example repository](https://github.com/pmarsceill/jtd-remote)</small>

### Local installation: Use the gem-based theme

1. Install the Ruby Gem
```bash
$ gem install just-the-docs
```
```yaml
# .. or add it to your your Jekyll site’s Gemfile
gem "just-the-docs"
```
2. Add Just the Docs to your Jekyll site’s `_config.yml`
```yaml
theme: "just-the-docs"
```
3. _Optional:_ Initialize search data (creates `search-data.json`)
```bash
$ bundle exec just-the-docs rake search:init
```
3. Run you local Jekyll server
```bash
$ jekyll serve
```
```bash
# .. or if you're using a Gemfile (bundler)
$ bundle exec jekyll serve
```
4. Point your web browser to [http://localhost:4000](http://localhost:4000)

<<<<<<< HEAD
If you're hosting your site on GitHub Pages, [set up GitHub Pages and Jekyll locally](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll) so that you can more easily work in your development environment.

### Configure Just the Docs

- [See configuration options]({{ site.baseurl }}{% link docs/configuration.md %})

---
=======
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
>>>>>>> 788a28789561f035c40fb66ef8241891b168ea88

## About the project

Just the Docs is &copy; 2017-{{ "now" | date: "%Y" }} by [Patrick Marsceill](http://patrickmarsceill.com).

<<<<<<< HEAD
### License
=======

## Serviços de Assistência
>>>>>>> 788a28789561f035c40fb66ef8241891b168ea88

Just the Docs is distributed by an [MIT license](https://github.com/pmarsceill/just-the-docs/tree/master/LICENSE.txt).

<<<<<<< HEAD
### Contributing
=======
# API para o identificador único
Esta API tem o objetivo de gerar um ID único para ser usado para chamar as outras APIS no envio de informação estatística ou de retorno de informação para um intervalo de referência.
Amtes de invocar as restantes APIS devemos invocar esta API para gerar o número único primeiro.
>>>>>>> 788a28789561f035c40fb66ef8241891b168ea88

When contributing to this repository, please first discuss the change you wish to make via issue,
email, or any other method with the owners of this repository before making a change. Read more about becoming a contributor in [our GitHub repo](https://github.com/pmarsceill/just-the-docs#contributing).

#### Thank you to the contributors of Just the Docs!

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"/></a>
  </li>
{% endfor %}
</ul>

### Code of Conduct

Just the Docs is committed to fostering a welcoming community.

[View our Code of Conduct](https://github.com/pmarsceill/just-the-docs/tree/master/CODE_OF_CONDUCT.md) on our GitHub repository.
