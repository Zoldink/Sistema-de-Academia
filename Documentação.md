# Documentação e Especificação do Sistema

## 1. Apresentação do Sistema

### 1.1. O que o sistema faz?
O **NexusFit** é um sistema orientado a objetos desenvolvido para automatizar e centralizar a gestão operacional de uma academia. Ele gerencia o ciclo de vida do aluno desde o seu cadastro e escolha de planos até o controle de pagamentos, pontuação no programa de fidelidade e monitoramento de pendências financeiras.

### 1.2. Para quem serve? (Público-Alvo)
O sistema atende a dois perfis principais de usuários:
* **Alunos:** Podem realizar login, acompanhar seu plano atual, consultar status de mensalidades, verificar pendências e acumular/resgatar pontos no programa de fidelidade.
* **Administradores / Funcionários:** Realizam o controle de matrículas, gestão de planos, liberação de acessos e monitoramento do caixa e inadimplências.

### 1.3. Principais Funcionalidades
* **Controle de Matrícula e Autenticação (Login):** Cadastro de novos usuários, controle de senhas com segurança e validação de perfil (Aluno vs. Funcionário).
* **Gestão de Planos:** Criação, edição e associação de diferentes tipos de planos de treinamento para os alunos.
* **Sistema de Pagamentos:** Registro e verificação de mensalidades pagas ou em aberto.
* **Módulo de Pendências:** Identificação automática de alunos com pagamentos atrasados ou restrições de acesso.
* **Programa de Fidelidade:** Sistema de acúmulo de pontos baseado na frequência ou tempo de plano ativo do aluno na academia.

---

## 2. Requisitos Funcionais (RF)
Os requisitos funcionais definem as funcionalidades e os comportamentos que o sistema deve apresentar, detalhando o que os usuários poderão fazer.

* **RF01 - Cadastro de Usuários:** O sistema deve permitir o cadastro de diferentes perfis de usuários (Alunos e Funcionários/Administradores), coletando dados como nome, CPF, e-mail e senha.
* **RF02 - Autenticação (Login):** O sistema deve validar as credenciais de acesso (CPF/E-mail e senha) para autenticar o usuário e direcioná-lo ao painel correspondente ao seu perfil.
* **RF03 - Gestão de Planos:** O administrador deve poder cadastrar, listar, atualizar e descontinuar planos de treinamento oferecidos pela academia (ex: Mensal, Trimestral, Anual).
* **RF04 - Controle de Matrículas:** O sistema deve permitir vincular um aluno ativo a um plano de academia específico, definindo data de início e vigência.
* **RF05 - Registro de Pagamentos:** O sistema deve registrar os pagamentos de mensalidades realizados pelos alunos, atualizando a data de quitação e o histórico financeiro.
* **RF06 - Monitoramento de Pendências:** O sistema deve identificar e sinalizar automaticamente alunos que possuem mensalidades vencidas ou pendências financeiras ativas.
* **RF07 - Programa de Fidelidade:** O sistema deve calcular, acumular e exibir pontos de fidelidade para os alunos com base na frequência ou na renovação de seus planos.

---

## 3. Requisitos Não Funcionais (RNF)
Os requisitos não funcionais estabelecem restrições técnicas, padrões de qualidade e premissas arquiteturais sob as quais o sistema deve ser construído.

* **RNF01 - Aplicação de POO:** O código-fonte deve ser obrigatoriamente estruturado com base nos quatro pilares da Programação Orientada a Objetos: **Abstração, Encapsulamento, Herança e Polimorfismo**.
* **RNF02 - Linguagem e Plataforma:** O projeto deve ser desenvolvido em **C#** utilizando o ecossistema .NET, garantindo tipagem estática e segurança de compilação.
* **RNF03 - Encapsulamento de Dados:** Atributos sensíveis (como senhas e estados financeiros) devem ser mantidos privados (`private` ou `protected`), sendo acessados ou modificados estritamente por meio de propriedades (`get`/`set`) ou métodos validadores.
* **RNF04 - Tratamento de Erros:** O sistema deve tratar exceções e entradas inválidas do usuário (ex: textos em campos numéricos, datas incorretas ou senhas vazias), evitando falhas abruptas durante a execução.
* **RNF05 - Padrões de Código:** O código deve seguir boas práticas de desenvolvimento (Clean Code), utilizando nomes descritivos para classes, métodos e variáveis, além de manter a organização modular por arquivos e namespaces.
* **RNF06 - Versionamento:** Todo o desenvolvimento do projeto deve ser rigorosamente versionado no GitHub, mantendo histórico de commits e documentação atualizada nas respectivas branches e arquivos Markdown.
