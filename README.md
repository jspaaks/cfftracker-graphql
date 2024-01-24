
Instructions from https://docs.github.com/en/graphql/guides/using-the-explorer.

Install GraphQL Client Altair

```
snap install altair
```

```graphql
query {
    rateLimit {
        cost
        remaining
        resetAt
    }
    search(query: "is:public archived:false org:citation-file-format created:>2017-12-31", type: REPOSITORY, first: 100, after: null){
        repositoryCount
        pageInfo {
            endCursor
            hasNextPage
        }
        nodes {
            ... on Repository {
                nameWithOwner
                object(expression: "HEAD:CITATION.cff") {
                    ... on Blob {
                        text
                    }
                }
            }
        }
    }
}
```


Example result:

```
{
  "data": {
    "rateLimit": {
      "cost": 1,
      "remaining": 4998,
      "resetAt": "2024-01-24T11:24:19Z"
    },
    "search": {
      "repositoryCount": 12,
      "pageInfo": {
        "endCursor": "Y3Vyc29yOjEy",
        "hasNextPage": false
      },
      "nodes": [
        {
          "nameWithOwner": "citation-file-format/cffconvert",
          "object": {
            "text": "abstract: Command line program to validate and convert CITATION.cff files.\nauthors:\n  - affiliation: Netherlands eScience Center\n    alias: jspaaks\n    family-names: Spaaks\n    given-names: Jurriaan H.\n    orcid: https://orcid.org/0000-0002-7064-4069\ncontributors:\n  - affiliation: University of Oslo\n    alias: wleoncio\n    family-names: Leoncio\n    given-names: Waldir\n    name-suffix: Netto\n  - affiliation: Humboldt-Universität zu Berlin\n    alias: sdruskat\n    family-names: Druskat\n    given-names: Stephan\n    orcid: https://orcid.org/0000-0003-4925-7248\n  - affiliation: Netherlands eScience Center\n    alias: Tommos0\n    family-names: Klaver\n    given-names: Tom\n  - alias: zmoon\n    family-names: Moon\n    given-names: Zachary\n  - alias: nialov\n    family-names: Ovaskainen\n    given-names: Nikolas\n  - alias: musicinmybrain\n    family-names: Beasley\n    given-names: Ben\n  - alias: abelsiqueira\n    family-names: Soares Siqueira\n    given-names: Abel\n    orcid: https://orcid.org/0000-0003-4451-281X\n  - alias: monperrus\n    family-names: Monperrus\n    given-names: Martin\n  - alias: ots22\n  - affiliation: Netherlands eScience Center\n    alias: sverhoeven\n    family-names: Verhoeven\n    given-names: Stefan\n    orcid: https://orcid.org/0000-0002-5821-2060\ncff-version: 1.3.0\ndate-released: 2021-09-22\nidentifiers:\n  - type: doi\n    value: 10.5281/zenodo.1162057\n    description: Persistent identifier for all versions of cffconvert\n    relation: isPartOf\n  - type: doi\n    value: 10.5281/zenodo.5521767\n    description: Persistent identifier for this version of cffconvert\n    relation: isIdenticalTo\n  - type: url\n    value: https://github.com/citation-file-format/cffconvert\n    description: URL to the GitHub repository for cffconvert\n  - type: url\n    value: https://pypi.org/project/cffconvert\n    description: cffconvert on PyPI\nkeywords:\n  - bibliography\n  - BibTeX\n  - cff\n  - citation\n  - CITATION.cff\n  - CodeMeta\n  - EndNote\n  - RIS\n  - Citation File Format\nlicense: Apache-2.0\nmessage: If you use this software, please cite it using these metadata.\nrepository-artifact: https://pypi.org/project/cffconvert\nrepository-code: https://github.com/citation-file-format/cffconvert\ntitle: cffconvert\ntype: software\nversion: 3.0.0a0\nreferences:\n  - authors:\n      - affiliation: Netherlands eScience Center\n        family-names: Zwaan\n        given-names: Janneke\n        name-particle: van der\n        orcid: https://orcid.org/0000-0002-8329-7000\n      - affiliation: Netherlands eScience Center\n        family-names: Werkhoven\n        given-names: Ben\n        name-particle: van\n        orcid: https://orcid.org/0000-0002-7508-3272\n      - affiliation: Netherlands eScience Center\n        family-names: Andela\n        given-names: Bouwe\n        orcid: https://orcid.org/0000-0001-9005-8940\n      - affiliation: Netherlands eScience Center\n        family-names: Bos\n        given-names: Patrick\n        orcid: https://orcid.org/0000-0002-6033-960X\n      - affiliation: Netherlands eScience Center\n        family-names: Attema\n        given-names: Jisk\n        orcid: https://orcid.org/0000-0002-0948-1176\n      - affiliation: Netherlands eScience Center\n        family-names: Bakker\n        given-names: Tom\n      - affiliation: Netherlands eScience Center\n        family-names: Spaaks\n        given-names: Jurriaan H.\n        orcid: https://orcid.org/0000-0002-7064-4069\n      - affiliation: Netherlands eScience Center\n        family-names: Kuppevelt\n        given-names: Dafne\n        name-particle: van\n        orcid: https://orcid.org/0000-0002-2662-1994\n      - affiliation: Netherlands eScience Center\n        family-names: Veen\n        given-names: Lourens\n        orcid: https://orcid.org/0000-0002-6311-1168\n      - affiliation: Netherlands eScience Center\n        family-names: Rol\n        given-names: Evert\n        orcid: https://orcid.org/0000-0001-8357-4453\n      - affiliation: Netherlands eScience Center\n        family-names: Verhoeven\n        given-names: Stefan\n        orcid: https://orcid.org/0000-0002-5821-2060\n      - affiliation: Netherlands eScience Center\n        family-names: Diblen\n        given-names: Faruk\n        orcid: https://orcid.org/0000-0002-0989-929X\n      - affiliation: Netherlands eScience Center\n        family-names: Tjong Kim Sang\n        given-names: Erik\n        orcid: https://orcid.org/0000-0002-8431-081X\n    date-released: 2018-07-17\n    identifiers:\n      - description: Concept DOI for Netherlands eScience Center Python Template\n        type: doi\n        value: 10.5281/zenodo.1310751\n    keywords:\n      - cookiecutter\n      - template\n      - Python\n    license: Apache-2.0\n    repository-code: https://github.com/NLeSC/python-template\n    title: Netherlands eScience Center Python Template\n    type: software\n    version: 0.4.0\n  - authors:\n      - family-names: McAdoo\n        given-names: Timothy\n    title: How to Cite Software in APA Style\n    type: blog\n    url: >-\n      https://blog.apastyle.org/apastyle/2015/01/how-to-cite-software-in-apa-style.html\n"
          }
        },
        {
          "nameWithOwner": "citation-file-format/ruby-cff",
          "object": {
            "text": "# This CITATION.cff file was created by ruby-cff (v 1.2.0).\n# Gem: https://rubygems.org/gems/cff\n# CFF: https://citation-file-format.github.io/\n\ncff-version: 1.2.0\nmessage: If you use ruby-cff in your work, please cite it using the following metadata\ntitle: Ruby CFF Library\nabstract: This library provides a Ruby interface to manipulate Citation File Format files\nauthors:\n- family-names: Haines\n  given-names: Robert\n  orcid: https://orcid.org/0000-0002-9538-7919\n  affiliation: The University of Manchester, UK\n- name: The Ruby Citation File Format Developers\nkeywords:\n- ruby\n- credit\n- software citation\n- research software\n- software sustainability\n- metadata\n- citation file format\n- CFF\nversion: 1.2.0\ndoi: 10.5281/zenodo.1184077\ndate-released: 2024-01-19\nlicense: Apache-2.0\nrepository-artifact: https://rubygems.org/gems/cff\nrepository-code: https://github.com/citation-file-format/ruby-cff\nreferences:\n- type: software\n  title: Citation File Format\n  authors:\n  - family-names: Druskat\n    given-names: Stephan\n    orcid: https://orcid.org/0000-0003-4925-7248\n  - family-names: Spaaks\n    given-names: Jurriaan H.\n    orcid: https://orcid.org/0000-0002-7064-4069\n  - family-names: Chue Hong\n    given-names: Neil\n    orcid: https://orcid.org/0000-0002-8876-7606\n  - family-names: Haines\n    given-names: Robert\n    orcid: https://orcid.org/0000-0002-9538-7919\n  - family-names: Baker\n    given-names: James\n    orcid: https://orcid.org/0000-0002-2682-6922\n  - family-names: Bliven\n    given-names: Spencer\n    orcid: https://orcid.org/0000-0002-1200-1698\n    email: spencer.bliven@gmail.com\n  - family-names: Willighagen\n    given-names: Egon\n    orcid: https://orcid.org/0000-0001-7542-0286\n  - family-names: Pérez-Suárez\n    given-names: David\n    orcid: https://orcid.org/0000-0003-0784-6909\n    website: https://dpshelio.github.io\n  - family-names: Konovalov\n    given-names: Alexander\n    orcid: https://orcid.org/0000-0001-5299-3292\n  identifiers:\n  - type: doi\n    value: 10.5281/zenodo.1003149\n    description: The concept DOI for the collection containing all versions of the Citation File Format.\n  - type: doi\n    value: 10.5281/zenodo.5171937\n    description: The versioned DOI for the version 1.2.0 of the Citation File Format.\n  keywords:\n  - citation file format\n  - CFF\n  - citation files\n  - software citation\n  - file format\n  - YAML\n  - software sustainability\n  - research software\n  - credit\n  abstract: CITATION.cff files are plain text files with human- and machine-readable citation information for software. Code developers can include them in their repositories to let others know how to correctly cite their software. This is the specification for the Citation File Format.\n  date-released: 2021-08-09\n  license: CC-BY-4.0\n  version: 1.2.0\n"
          }
        },
        {
          "nameWithOwner": "citation-file-format/cffconvert-github-action",
          "object": {
            "text": "# YAML 1.2\n---\nauthors:\n  -\n    family-names: Spaaks\n    given-names: \"Jurriaan H.\"\n    orcid: \"https://orcid.org/0000-0002-7064-4069\"\n  -\n    family-names: Diblen\n    given-names: Faruk\n    orcid: \"https://orcid.org/0000-0002-0989-929X\"\n  -\n    family-names: \"Soares Siqueira\"\n    given-names: Abel\n    orcid: \"https://orcid.org/0000-0003-4451-281X\"\ncff-version: \"1.2.0\"\ndate-released: 2022-01-24\nidentifiers:\n  - type: doi\n    value: 10.5281/zenodo.3993241\n    description: \"The work's conceptdoi\"\nlicense: \"Apache-2.0\"\nmessage: \"If you use this software, please cite it using these metadata.\"\ntitle: \"cffconvert GitHub Action\"\nversion: 2.0.0\n...\n"
          }
        },
        {
          "nameWithOwner": "citation-file-format/doi2cff",
          "object": {
            "text": "# YAML 1.2\n# Metadata for citation of this software according to the CFF format (https://citation-file-format.github.io/)\ncff-version: 1.0.3\nmessage: If you use this software, please cite it as below.\n# FIXME title as repository name might not be the best name, please make human readable\ntitle: DOI 2 citation format file generator\ndoi: 10.5281/zenodo.1206049\n# FIXME splitting of full names is error prone, please check if given/family name are correct\nauthors:\n- given-names: Stefan\n  family-names: Verhoeven\n  affiliation: Netherlands eScience Center\n- given-names: Jurriaan\n  family-names: Spaaks\n  name-particle: H.\n  affiliation: Netherlands eScience Center\nversion: 1.0.0\ndate-released: 2018-03-23\nrepository-code: https://github.com/citation-file-format/doi2cff\nlicense: Apache-2.0\n"
          }
        },
        {
          "nameWithOwner": "citation-file-format/cff-initializer-javascript",
          "object": {
            "text": "abstract: Web form to initialize CITATION.cff files.\nauthors:\n  - affiliation: Netherlands eScience Center\n    family-names: Spaaks\n    given-names: Jurriaan H.\n    orcid: https://orcid.org/0000-0002-7064-4069\n  - affiliation: Netherlands eScience Center\n    family-names: Verhoeven\n    given-names: Stefan\n    orcid: https://orcid.org/0000-0002-5821-2060\n  - affiliation: Netherlands eScience Center\n    family-names: Diblen\n    given-names: Faruk\n    orcid: https://orcid.org/0000-0002-0989-929X\n  - affiliation: German Aerospace Center\n    family-names: Druskat\n    given-names: Stephan\n    orcid: https://orcid.org/0000-0003-4925-7248\n  - affiliation: Netherlands eScience Center\n    family-names: Soares Siqueira\n    given-names: Abel\n    orcid: https://orcid.org/0000-0003-4451-281X\n  - affiliation: Netherlands eScience Center\n    family-names: Garcia Gonzalez\n    given-names: Jesus\n    orcid: https://orcid.org/0000-0002-2170-3253\n  - affiliation: Netherlands eScience Center\n    family-names: Cushing\n    given-names: Reggie\n    orcid: https://orcid.org/0000-0002-5967-7302\ncff-version: 1.2.0\ndate-released: 2023-08-08\nidentifiers:\n  - type: doi\n    value: 10.5281/zenodo.8224012\n    description: >-\n      This is the identifier used to uniquely identify the version of the\n      software.\n  - type: doi\n    value: 10.5281/zenodo.1404735\n    description: >-\n      This is the identifier used to uniquely identify the software as a concept\n      (i.e., version-agnostic).\nkeywords:\n  - citation\n  - CITATION.cff\n  - credit\n  - research software engineering\nlicense: Apache-2.0\nmessage: If you use this software, please cite it using these metadata.\nrepository-code: https://github.com/citation-file-format/cff-initializer-javascript\ntitle: cffinit\nversion: 2.3.1\n"
          }
        },
        {
          "nameWithOwner": "citation-file-format/citemycode",
          "object": {
            "text": "cff-version: 1.0.3\nauthors:\n  - family-names: Druskat\n    given-names: Stephan\n    orcid: https://orcid.org/0000-0003-4925-7248\nauthors:\n  - family-names: Haupt\n    given-names: Carina\n    orcid: https://orcid.org/0000-0001-6447-1379\nauthors:\n  - family-names: Bouquin\n    given-names: Daina\n    orcid: https://orcid.org/0000-0003-2626-3688\nauthors:\n  - family-names: Gibson\n    given-names: Sarah\ntitle: Cite My Code\nversion: \ndoi: \ndate-released: \n\n"
          }
        },
        {
          "nameWithOwner": "citation-file-format/cff-initializer-javascript-v1",
          "object": {
            "text": "# YAML 1.2\n---\nabstract: \"Web form to initialize CITATION.cff files. The live version is hosted here: <a href=\\\"https://citation-file-format.github.io/cff-initializer-javascript/\\\">https://citation-file-format.github.io/cff-initializer-javascript/</a>.\"\nauthors:\n  -\n    affiliation: \"Netherlands eScience Center\"\n    family-names: Spaaks\n    given-names: \"Jurriaan H.\"\n    orcid: \"https://orcid.org/0000-0002-7064-4069\"\n  -\n    family-names: Lawson-Perfect\n    given-names: Christian\ncff-version: \"1.2.0\"\ndate-released: \"2021-08-16\"\nidentifiers:\n  - type: doi\n    value: 10.5281/zenodo.1404735\n    description: This the identifier used to uniquely identify the software as a concept (i.e., version-agnostic).\nkeywords:\n  - credit\n  - \"research software engineering\"\n  - citation\n  - CITATION.cff\nlicense: Apache-2.0\nmessage: \"If you use this software, please cite it using these metadata.\"\nrepository-code: \"https://github.com/citation-file-format/cff-initializer-javascript\"\ntitle: cffinit\nversion: \"1.6.0\"\n"
          }
        },
        {
          "nameWithOwner": "citation-file-format/get-spdx-licenses",
          "object": null
        },
        {
          "nameWithOwner": "citation-file-format/github2cff",
          "object": {
            "text": "cff-version: 1.0.3\nmessage: If you use this software, please cite it as below.\nauthors:\n  - family-names: McKain\n  - given-names: Dave\n  - family-names: Druskat\n    given-names: Stephan\n  - family-names: Parker\n    given-names: Joseph\n  - family-names: Baker\n    given-names: James\ntitle: github2cff\nversion: 0.1\ndate-released: 2018-03.28\n"
          }
        },
        {
          "nameWithOwner": "citation-file-format/pycff",
          "object": null
        },
        {
          "nameWithOwner": "citation-file-format/governance",
          "object": null
        },
        {
          "nameWithOwner": "citation-file-format/branding",
          "object": null
        }
      ]
    }
  }
}
```
