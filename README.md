# Rotina9817_AnaliseDeCredito_Public

# Sumário
- [Descrição do Projeto](#descrição-do-projeto)
- [Requisitos do Sistema](#requisitos-do-sistema)
    - [Usuário](#usuário)
    - [Desenvolvedor](#desenvolvedor)
- [Detalhes Técnicos](#detalhes-técnicos)
    - [Arquitetura](#arquiterura)
    - [Estrutura de diretórios](#estrutura-de-diretórios)
    - [Nomenclatura de Controles](nomenclatura-de-controles)
    - [Compilação e Execução](#compilação-e-execução)
    - [Controle de Versões](#controle-de-versões)
- [Instruções de Instalação](#instruções-de-instalação)

# Descrição do Projeto

A descrição e  detalhes sobre o objetivo do projeto e suas funcionalidades presentes na ferramenta podem ser encontradas no arquivo [About.md](https://github.com/denissonjs/Rotina9817_AnaliseDeCredito_Public/blob/main/About.md) deste repositório. Este README tratará principalmente das especificações tecnicas de desenvolvimento.

# Requisitos do Sistema
## Usuário
### Requisitos Hardware
- Processador: Processador dual-core de 2,0 GHz ou superior.
- Memória RAM: Mínimo de 4 GB de RAM.
- Espaço em Disco: Não aplicável.
- Resolução de Tela: Recomendada resolução mínima de 1280x800 pixels.
### Requisitos de Software
- Sistema Operacional: Windows 10 (64 bits) ou posterior.
- Banco de dados: Oracle 12C ou superior.

## Desenvolvedor
### Requisitos de Software
- Sistema Operacional: Windows 10 (64 bits) ou posterior.
- Framework: Microsoft .NET Framework 4.8 ou superior.
- Banco de dados: Oracle 12C ou superior.
- Ambiente de Desenvolvimento: Visual Studio 2022 ou superior.

### Requisitos Hardware
- Processador: Processador dual-core de 2,0 GHz ou superior.
- Memória RAM: Mínimo de 8 GB de RAM.
- Espaço em Disco: Entre 10MB e 50MB disponível.
- Resolução de Tela: Recomendada resolução mínima de 1280x800 pixels.

### Dependências Externas (de projeto)
- Biblioteca de Banco de dados: Oracle.ManagedDataAccess
    - A biblioteca `Oracle Data Access` usada em projetos anteriores não será mais utilizado. O pacote se tornou obsoleto, sem mais suporte e assim não recomendado pela IDE utilizada no projeto.

- Biblioteca de exportação de arquivo: EPPlus
    - Parte dos usuários não possuem os Microsoft Office instalado por utilizarem versão web, por esse motivo o pacote `Microsoft.Office.Interop.Excel` usado em projetos anteriores não será mais utilizado. Arquivos do tipo XSLS serão exportados permitindo a abertura em qualquer ferramenta de office sendo microsoft ou não

- Instalação: Projeto - Gerenciar pacotes do nuget - Buscar e instalar o pacote.

# Detalhes Técnicos

## Arquiterura
Este projeto utiliza a arquitetura MVC (Model-View-Controller) para organizar e estruturar o código-fonte da aplicação Windows Form .NET. A escolha dessa arquitetura se baseia na simplicidade e direcionamento claro das responsabilidades, adequando-se às necessidades do projeto sem necessidades de arquiteturas mais robustas como a Clean Architecture.

### Sobre a Arquitetura MVC
O padrão MVC é amplamente utilizado no desenvolvimento de software e oferece uma divisão clara das responsabilidades em três componentes principais: Model, Views e Controllers. O vídeo [Entenda AGORA o PADRÃO Arquitetural MVC](https://www.youtube.com/watch?v=9Ieh0yoiiqI&pp=ygUSYXJxdWl0ZXR1cmEgbXZjIGMj) fornece mais detalhes sobre essa arquitetura.
### Vantagens da Arquitetura MVC para o Projeto
A escolha da arquitetura MVC para este projeto tem como objetivo aproveitar as seguintes vantagens:

- Separação de Responsabilidades:
A arquitetura MVC permite uma clara separação de responsabilidades entre as camadas do projeto. O Model se concentra na lógica de negócios e nos dados, a View na interface do usuário e a interação com o usuário, e o Controller na coordenação das ações entre o Model e a View. Isso torna o código mais organizado e facilita a manutenção e evolução do projeto.

- Facilidade de Testes:
A separação das responsabilidades na arquitetura MVC facilita a realização de testes unitários e automatizados. O Model, por exemplo, pode ser testado independentemente da View e do Controller, permitindo uma validação mais precisa da lógica de negócios.

- Reutilização de Componentes:
A arquitetura MVC incentiva a reutilização de componentes em diferentes partes do projeto. Por exemplo, a mesma View pode ser usada com diferentes Controllers para atender a diferentes requisitos ou fluxos de trabalho, sem a necessidade de reescrever o código.

Alguns exemplos da implementação deste modelo podem ser encontrados no vídeo [Projeto .NET: Aprenda as melhores práticas de arquitetura em 2023](https://youtu.be/jkPqczgDIZU).
### Conclusão

A arquitetura MVC oferece uma abordagem clara e estruturada para o desenvolvimento do projeto Windows Form .NET. Com a separação de responsabilidades e a facilidade de manutenção e teste, é possível desenvolver uma aplicação bem estruturada, escalável e de fácil evolução.

Este projeto busca tirar proveito dessas vantagens e oferecer uma experiência de desenvolvimento mais organizada e eficiente. Para mais informações sobre a arquitetura MVC, consulte a documentação fornecida e aproveite os recursos e exemplos disponíveis para ajudá-lo a criar uma aplicação de qualidade.

## Estrutura de diretórios

A principal estrutura de pastas segue o padrão de pastas para projetos Windows Form .NET criado pelo Visual Studio 2022. **Os componentes da divisão de responsabilidades do ***padrão MVC*** serão gerenciados em pastas ao invés de ***Class Libraries***.**

Models: Armazena as regras de negócio e acesso e persistência de dados.
Views: Armazena a lógica visual do négócio como apresentação de dados, formatação de numeradores. É dividida em "DataFormetters", "ControlModifies" e "FillDataControls".
Controlers: Controlers irá orquestrar a lógica de negócio tratando de objeto de filtros, validação de strings/queries SQL e organização de dados da persistência. Está dividida em Services e Helpers. 

## Nomenclatura de Controles

A nomenclatura dos controles (DataGridViews, TextBoxes, Labels, etc.) seguirá padronizado com a abreviação do tipo de controle seguido do nome do controle. Controles que poderão conter o mesmo nome mas que se encontram em containers (Tab Page) diferentes seguirão com a abreviação do controle seguida no nome do mesmo encerrando pelo nome do container.

Exemplo:
1. TextBox que contém o "nome do cliente" em container único: tbNomeCliente.
2. Textbox que contém o "nome do cliente" em container múltiplo nomeado por "mais limite": tbCodClienteMaisLimite

## Compilação e Execução

### Pré-requisitos
Certifique-se de que o seu sistema atenda aos [Requisitos](#requisitos_do_sistema_desenvolvedor) do Sistema mencionados na documentação.

### Passo 1: Clonar o repositório
1. Abra o Git Bash ou a ferramenta de linha de comando de sua preferência.
2. Navegue até o diretório em que deseja clonar o repositório.
3. Execute o seguinte comando: `git clone https://github.com/denissonjs/Rotina9817_AnaliseDeCredito`

### Passo 2: Configurar o ambiente
1. Abra o Visual Studio 2019 (ou superior).
2. Selecione a opção "Abrir um projeto ou uma solução".
3. Navegue até o diretório em que você clonou o repositório e selecione o arquivo de solução (.sln).
4. Aguarde até que o Visual Studio carregue o projeto e suas dependências.

### Passo 3: Restaurar os pacotes NuGet
1. No Visual Studio, abra o "Gerenciador de Pacotes NuGet" clicando com o botão direito do mouse no projeto no "Solution Explorer" e selecionando a opção "Gerenciador de Pacotes NuGet".
2. Na janela do "Gerenciador de Pacotes NuGet", clique na guia "Consolidar" para restaurar todos os pacotes NuGet necessários para o projeto.
3. Aguarde até que o Visual Studio restaure todos os pacotes NuGet e resolva as dependências.

### Passo 4: Configurar a conexão com o banco de dados Oracle
1. Abra o arquivo "app.config" (ou "web.config") localizado na pasta do projeto.
2. Localize a seção de configuração referente à conexão com o banco de dados Oracle.
3. Insira as informações necessárias, como a string de conexão, nome do banco de dados, usuário e senha.
4. Salve o arquivo de configuração.

### Passo 5: Compilar e executar o projeto
1. No Visual Studio, clique em "Compilar" para compilar o projeto.
2. Após a compilação ser concluída sem erros, clique em "Executar" ou pressione F5 para iniciar a aplicação.

## Colaboração
### Atualização de Releases
Antes do envio de é importante que o arquivo Changelog.md esteja atualizado com as modificações que estão sendo enviadas. A versão lançada deverá seguir o [padrão de versionamento](#controle-de-versões) adotado no projeto.
### Descrição de Commits
Para garantir a padronização das mensagens de commit neste projeto, é sugerido que os commits possuam o título da versão que está sendo enviada para o repositório remoto. Isso ajudará a identificar claramente as alterações associadas a cada versão do projeto.
### Efetuando Commit
1. Para adicionar todas as modificações ao stage execute: `git add .`
2. Para efetuar o commit execute: `git commit -m "Titulo da versao que esta sendo lançada"`.
3. Para enviar as alterações para o repositório remoto execute: `git push`.

## Controle de Versões
Para transparência em nossos ciclos de lançamento e para manter a compatibilidade com versões anteriores, a aplicação será mantida sob [as diretrizes de Controle de Versão Semântico](https://semver.org/) armazenados e disponíveis no arquivo de [Releases](https://github.com/denissonjs/Rotina9817_AnaliseDeCredito/blob/main/changelog.md) deste repositório. 

# Instruções de instalação
O trabalho do(s) desenvolvedor(es) terá como produto final um arquivo executável (.exe) que será gerenciado através do ERP da empresa, ou seja, em ambiente winthor. Sendo assim, a instalação partirá da equipe de análise de sistemas do ERP, não sendo necessárias nessa documentação, instruções sobre instalação do software.
