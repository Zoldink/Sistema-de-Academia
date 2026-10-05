
# Modelagem do Sistema - PulseGym

Esta seção apresenta a estrutura estática do sistema **NexusFit** sob a ótica da Orientação a Objetos. O desenho foi concebido para suportar dois perfis distintos de acesso através de um módulo de autenticação unificado: **Clientes (Alunos)** e **Administradores (Funcionários)**. 

Abaixo encontra-se o diagrama de classes em UML, seguido da listagem detalhada das responsabilidades de cada entidade e da explicação dos seus relacionamentos.

---

## 1. Diagrama de Classes (UML)

```mermaid
classDiagram
    class Usuario {
        <<abstract>>
        #string Nome
        #string Email
        #string Cpf
        #string Senha
        +RealizarLogin(string email, string senha) bool
        +RealizarLogout()
    }
    
    class Aluno {
        -string Matricula
        -string StatusMatricula
        -int PontosFidelidade
        +ConsultarPlanoAtivo()
        +VerificarPendenciasFinanceiras()
        +ConsultarExtratoFidelidade()
    }
    
    class Funcionario {
        -string Cargo
        -double Salario
        -string NivelPermissao
        +CadastrarNovoPlano()
        +RegistrarPagamentoAluno()
        +GerenciarMatriculas()
        +EmitirRelatorioInadimplencia()
    }
    
    class Plano {
        -int IdPlano
        -string NomePlano
        -double ValorMensal
        -int DuracaoMeses
        +AtualizarValorPlano(double novoValor)
    }
    
    class Pagamento {
        -int IdPagamento
        -double Valor
        -DateTime DataVencimento
        -string StatusPagamento
        +ProcessarPagamento()
        +MarcarComoPendente()
    }

    Usuario <|-- Aluno
    Usuario <|-- Funcionario
    Aluno "1" --> "1" Plano : possui contrato
    Aluno "1" --> "*" Pagamento : gera faturas
