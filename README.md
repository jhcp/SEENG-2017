# SEENG
This is the code for the Engineering Week (Semana das Engenharias) event 2017 edition website.

It is currently live at http://www.semanadasengenharias.com/2017

## About
The Engineering Week is an academic event hosted by Universidade Federal de Pernambuco - Unidade Acadêmica do Cabo de Santo Agostinho ([UACSA](http://www.uacsa.ufrpe.br)).

## Development
The *config.toml* file contains the text of the website.
Lecturers (palestrantes) data is located in the *data/palestrantes* folder.

It uses [Hugo](https://gohugo.io/) for static site generation, version 0.20.3. The command for generating the website is:

    hugo

You can preview the website in your machine with the following command:

    hugo server

The address for accessing it is informed in the output of this previous command. For further info go to [Hugo](https://gohugo.io/)'s website.

## Acknowledgements
The Hugo's theme used in this website is based on Hugo's [Creative](http://themes.gohugo.io/creative/) theme, which is based on a Bootstrap theme by David Miller. Hugo's Creative is published with an Apache License 2.0. Our customized version is included in this repository. A statement of modified files can be found at themes/hugo-creative-theme/CHANGES.md
