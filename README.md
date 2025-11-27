# Especificação de Requisitos do Sistema (ERS/SRS)

## Descrição Geral do Sistema
O sistema tem como objetivo modernizar as bibliotecas tradicionais, democratizar o acesso à informação e otimizar a gestão do acervo através de uma plataforma web centralizada.
Inclui o suporte a perfis de usuários leitores e bibliotecários, abrangendo as principais funcionalidades de catalogação, empréstimo, devolução e consulta de obras, operando em um contexto de arquitetura em nuvem com foco na alta disponibilidade e na experiência do usuário (UX).

---

## Requisitos Gerais

### Requisitos Funcionais (RF)
| ID | Descrição | Prioridade |
|----|------------|-----------|
| RF01 | O sistema deve permitir o cadastro, edição, exclusão e consulta de obras na biblioteca. | Essencial |
| RF02 | O sistema deve permitir registrar os empréstimos e devoluções de obras, atualizando automaticamente a disponibilidade. | Essencial |
| RF03 | O sistema deve possibilitar o cadastro e gerenciamento de usuários. | Essencial |
| RF04 | O sistema deve permitir que os usuários pesquisem obras por título, autor, categoria. | Essencial |
| RF05 | O sistema deve gerar relatórios sobre empréstimos realizados. | Importante |
| RF06 | O sistema deve permitir que os usuários realizem login e se cadastrem, incluindo um mecanismo para recuperação de senha. | Essencial |
| RF07 | O sistema deve permitir que um usuário entre em uma fila de espera (reservar) para uma obra que não esteja disponível. | Essencial |
| RF08 | O sistema deve notificar automaticamente os usuários sobre prazos de devolução e disponibilidade de obras reservadas. | Essencial |
| RF09 | O sistema deve calcular, registrar e gerenciar multas por atraso na devolução. | Essencial | 
| RF10 | O sistema deve permitir que o usuário consulte seu próprio histórico de empréstimos, status de reservas e pendências. | Importante |
| RF11 | O sistema deve diferenciar obras físicas de digitais, permitindo o empréstimo de e-books. | Importante |
| RF12 | O sistema deve apresentar uma página de detalhes para cada obra, exibindo informações completas. | Importante |
| RF13 | O sistema deve permitir que o administrador gerencie diferentes níveis de permissão de usuários. | Importante | 
| RF14 | O sistema deve expandir a funcionalidade de busca para incluir filtros avançados. | Desejável |
| RF15 | O sistema deve permitir que os usuários avaliem e escrevam resenhas sobre as obras. | Desejável |
| RF16 | O sistema deve fornecer um painel de controle (dashboard) para os administradores com estatísticas rápidas. | Desejável |
| RF17 | O sistema deve gerar relatórios adicionais, como obras mais reservadas e usuários com mais empréstimos. | Desejável |

### Requisitos Não Funcionais (RNF)
| ID | Descrição | Prioridade |
|----|------------|-----------|
| RNF01 | O sistema deve criptografar todas as senhas dos usuários no banco de dados.                          | Essencial    |
| RNF02 | O sistema deve estar disponível para acesso 99% do tempo.                                            | Essencial    |
| RNF03 | O sistema deve ser compatível com os navegadores web mais utilizados (Chrome, Firefox, Safari e Edge). | Importante |
| RNF04 | O tempo de resposta para uma busca de livros no catálogo não deve exceder 2 segundos.                | Importante   |
| RNF05 | O sistema deve permitir a personalização do tema entre modo claro e escuro.                          | Desejável    |

### Regras de Negócio (RN)
| ID | Descrição | Prioridade |
|----|------------| -----------|
| RN01 | Usuários com devoluções em atraso não podem realizar novos empréstimos ou renovações. | Importante |
| RN02 | Cada usuário pode ter no máximo 3 (três) livros emprestados simultaneamente. | Importante |
| RN03 | A renovação de um empréstimo só é permitida caso não haja fila de reserva para o livro. | Importante |
| RN04 | O livro reservado ficará disponível para retirada por um prazo de 48 horas. | Importante |
| RN05 | Professores cadastrados possuem um prazo de devolução estendido para 30 dias, enquanto os demais usuários possuem 15 dias. | Importante |

---

## Diagramas UML

### Diagrama de Casos de Uso
![Diagrama de Casos de Uso](docs/diagrama_caso_de_uso_V2.png)

### Diagrama de Sequência
![Diagrama de Sequência](docs/diagrama_sequencia_V2.png)
![Diagrama de Sequência](docs/Diagrama_Sequencia_V2.webp)


### Diagrama de Atividades
![Diagrama de Atividades](docs/Diagrama_atividade_V2.webp)
![Diagrama de Atividades](docs/Diagrama_atividade_V2..webp)
---

## Arquitetura do Sistema
O sistema adota o estilo arquitetural **MVC (Model–View–Controller)**, separando responsabilidades entre:
- **Model:** lógica e acesso a dados.  
- **View:** interface e interação com o usuário.  
- **Controller:** coordenação entre as camadas.

![Arquiteura do Sistema](docs/arquitetura.drawio.png)
