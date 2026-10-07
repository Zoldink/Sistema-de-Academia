# NexusFit

> **Projeto de Orientação a Objetos (POO)** — PUC Minas Betim  
> **Integrantes:** Eduardo Antunes, Eric Gomes, Gustavo de Aguilar, Jefferson Marlon  

---

## 1.Apresentação do Sistema

### 1.1. O que o sistema faz?
O **NexusFit** é um sistema orientado a objetos desenvolvido para automatizar e centralizar a gestão operacional de uma academia. Ele gerencia o ciclo de vida do aluno desde o seu cadastro e escolha de planos específicos até o controle de pagamentos, status de matrícula, emissão de fichas de treino e monitoramento de pendências operacionais.

### 1.2. Para quem serve? (Público-Alvo)
O sistema atende a dois perfis principais de usuários através de um módulo de autenticação unificado:

* 👤 **Alunos (Clientes):** Podem realizar login, consultar pagamentos, verificar o status da matrícula, solicitar cancelamento de contrato, alterar de plano e visualizar sua ficha de treino.
* 👨‍💼 **Administradores / Funcionários:** Realizam o controle de matrículas, cadastros de alunos (contendo nome, e-mail, CPF, senha e número de matrícula), consulta de dados e pendências (verificando se o status está ativo ou inativo), cobranças de pagamentos, cancelamento de matrículas e elaboração/atualização das fichas de treino.

### 1.3. Principais Funcionalidades
* 🔐 **Controle de Matrícula e Autenticação:** Sistema de login unificado que valida credenciais e direciona o usuário para o painel correspondente ao seu perfil (Administrador ou Aluno).
* 🥇 **Gestão de Planos por Categoria:** Oferta de planos estruturados em níveis (**Diamante**, **Ouro** e **Prata**), cada qual com regras específicas de acesso aos dias da semana, aulas de bicicleta, aulas de box e benefícios exclusivos (como convites para amigos ou aulas avulsas de escolha).
* 💳 **Controle Financeiro e de Pendências:** Registro de pagamentos e verificação do status de atividade do aluno para liberação ou restrição de acesso.
* 📋 **Módulo de Fichas de Treino:** Elaboração e acompanhamento individualizado dos exercícios montados pelo funcionário e visualizados pelo aluno.

---

## 2.Requisitos Funcionais (RF)

Os requisitos funcionais definem as funcionalidades e os comportamentos que o sistema deve apresentar, detalhando o que os usuários poderão fazer.

| Código | Requisito Funcional | Descrição |
| :--- | :--- | :--- |
| **RF01** | **Cadastro de Usuários e Perfis** | O sistema deve permitir o cadastro de usuários diferenciando perfis de Alunos e Funcionários, coletando dados como nome, e-mail, CPF, senha e número de matrícula. |
| **RF02** | **Autenticação por Perfil** | O sistema deve validar as credenciais de acesso (e-mail/CPF e senha) e direcionar o usuário autenticado para o seu respectivo painel (Painel do Administrador ou Painel do Aluno). |
| **RF03** | **Gestão de Planos e Benefícios** | O sistema deve gerenciar os diferentes tipos de planos (**Diamante**, **Ouro** e **Prata**), aplicando regras específicas de frequência e modalidades. |
| **RF04** | **Gestão de Matrículas pelo Aluno** | O aluno deve poder escolher seu plano no momento da adesão, bem como solicitar a alteração de plano ou o cancelamento de sua matrícula pelo painel. |
| **RF05** | **Painel e Operações do Administrador** | O funcionário deve ter autonomia para consultar dados cadastrais completos dos alunos, verificar pendências (status ativo/inativo), efetuar cobranças, cancelar matrículas e criar ou atualizar a ficha de treino do aluno. |
| **RF06** | **Consulta de Pagamentos e Status** | O aluno deve poder consultar o seu histórico de pagamentos e o estado atual da sua matrícula, enquanto o sistema valida as pendências financeiras. |
| **RF07** | **Gestão de Fichas de Treino** | O sistema deve permitir que o funcionário cadastre e atualize a ficha de treino, ficando disponível para visualização pelo aluno. |

>  **Detalhamento das Regras de Negócio dos Planos (RF03):**
> * 💎 **Plano Diamante:** Acesso 7 dias por semana, aulas de bicicleta, aulas de box e direito a levar 3 amigos por mês.
> * 🥇 **Plano Ouro:** Acesso 7 dias por semana, aulas de bicicleta e aulas de box.
> * 🥈 **Plano Prata (Básico):** Acesso 5 dias por semana e direito a 1 aula por mês de livre escolha.

---

## 3.Requisitos Não Funcionais (RNF)

Os requisitos não funcionais estabelecem restrições técnicas, padrões de qualidade e premissas arquiteturais sob as quais o sistema deve ser construído.

* **RNF01 - Aplicação de POO:** O código-fonte deve ser obrigatoriamente estruturado com base nos quatro pilares da Programação Orientada a Objetos: **Abstração, Encapsulamento, Herança e Polimorfismo**.
* **RNF02 - Linguagem e Plataforma:** O projeto deve ser desenvolvido em **C#** utilizando o ecossistema .NET, garantindo tipagem estática e segurança de compilação.
* **RNF03 - Encapsulamento de Dados:** Atributos sensíveis (como senhas, CPF e status financeiros/de matrícula) devem ser mantidos privados (`private` ou `protected`), sendo acessados ou modificados estritamente por meio de propriedades (`get`/`set`) ou métodos validadores seguros.
* **RNF04 - Tratamento de Erros:** O sistema deve tratar exceções e entradas inválidas do usuário (ex: campos vazios, dados incorretos ou falhas de autenticação), evitando falhas abruptas durante a execução.
* **RNF05 - Padrões de Código:** O código deve seguir boas práticas de desenvolvimento (*Clean Code*), utilizando nomes descritivos para classes, métodos e variáveis, além de manter a organização modular por arquivos e *namespaces*.
* **RNF06 - Versionamento:** Todo o desenvolvimento do projeto deve ser rigorosamente versionado no GitHub, mantendo histórico de commits e documentação atualizada nas respectivas *branches* e arquivos Markdown.
