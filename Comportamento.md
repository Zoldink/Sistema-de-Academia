# Como os 4 pilares irão trabalhar no sistema


## Abstração

Classes Abstratas:

Usuario: Não existem "usuários genéricos"; todo indivíduo cadastrado é obrigatoriamente um Aluno ou um Funcionario.

Plano: Serve como modelo base; na prática, o contrato sempre será PlanoDiamante, PlanoOuro ou PlanoPrata.

Por que abstrair? Isola regras essenciais (autenticação e pacotes) e padroniza comportamentos comuns.

O que foi ignorado (fora do escopo): Integração física com hardware de catracas, exames médicos detalhados e transações bancárias em tempo real.

## Encapsulamento
Atributos Privados/Protegidos: Senha, Cpf, StatusAtivoOuInativo, AulasEscolhaMes e ConvitesAmigosMes.

Controle de Acesso: Intermediado por propriedades (get/set) e métodos específicos da classe.

Validações Aplicadas:

Senha: Impede strings vazias ou com menos de 6 caracteres.

StatusAtivoOuInativo: Só pode ser alterado por métodos do Funcionario ou mediante baixa de pagamento.

ConvitesAmigosMes: Decrementa os convites e impede valores negativos.

## Herança
Hierarquia 1 (Atores do Sistema):

Classe-Mãe: Usuario (reúne Nome, Email, Cpf, Senha e RealizarLogin).

Filhas: Aluno (adiciona Matricula, VerFicha(), MudarPlano()) e Funcionario (adiciona Cargo, Salario, FazerFichaAluno(), CobrarPagamento()).

Hierarquia 2 (Modalidades de Contrato):

Classe-Mãe: Plano (define dias de acesso e permissões de aulas).

Filhas: PlanoDiamante (+3 convites/mês), PlanoOuro (libera Bike e Box), e PlanoPrata (5 dias/semana + 1 aula avulsa/mês).

## Polimorfismo
Método Base 1 (ExibirPainel() em Usuario):

No Aluno: Renderiza a tela do cliente (status da matrícula, pagamentos, troca de plano e ficha).

No Funcionario: Renderiza o painel administrativo (consulta de dados, cobrança e montagem de ficha).

Método Base 2 (ValidarAcessoAula() em Plano):

PlanoDiamante: Libera acesso 7 dias/semana, aulas de Bike, Box e entrada de convidados.

PlanoOuro: Libera acesso 7 dias/semana, aulas de Bike e Box.

PlanoPrata: Restringe o acesso a 5 dias/semana e valida o limite de 1 aula especial por mês.
