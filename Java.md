Modificadores de Acesso | Dentro da Classe | Dentro do Pacote | Mesmo Pacote por Subclasses | Fora do Pacote por Subclasses | Global
----------------------- | ---------------- | ---------------- | --------------------------- | ----------------------------- | ------
Public | Sim | Sim | Sim | Sim | Sim
Protected | Sim | Sim | Sim | Sim | Não
Default | Sim | Sim | Sim | Não | Não
Private | Sim | Não | Não | Não | Não


# GIT
* git init -> inicia os repositórios vazios
* git add . -> adiciona todos os arquivos no repositório
* git commit -m "Mensagem" -> cria um novo commit
* git log --pretty=oneline -> verifica os commites que foram realizados 
* git restore --staged <ARQUIV)> -> remove os arquivos da staged area
* tags -> etiquetas para fazer marcações de versões do sistema Ex: V 1.0, V1.2
* git tag -> lista as versões dos sistemas
* git tag -a -m "Mensagem" -> cria uma nova tag



# STREAMS

## Interfaces Funcionais

Assinatura | Nome
---------- | ----
nada -> T  | Supplier
T -> Nada  | Consumer
T -> T     | UnaryOperator
T,T -> T   | BinaryOperator
S -> T     | Function
T->Boolean | Predicate 

## Match
* allMatch -> se todos passaram no teste
* anyMatch -> se algum passou no teste
* noneMatch -> se nenhum passou no teste
~~~ Exemplo Match
		Aluno a1 = new Aluno("Ana", 7.2);
		Aluno a2 = new Aluno("Lia", 5.2);
		Aluno a3 = new Aluno("Bia", 10.0);	
		List<Aluno> alunos = Arrays.asList(a1, a2, a3);
		Predicate<Aluno> aprovado = a -> a.nota >= 7;
		System.out.println(alunos.stream().allMatch(aprovado));
		System.out.println(alunos.stream().anyMatch(aprovado));
		System.out.println(alunos.stream().noneMatch(aprovado));
~~~

## MinMax
* max -> retorna o valor máximo
* min -> retorna o valor minimo
* Comparator -> Stream de comparacao
~~~ Exemplo MinMax
		Aluno a1 = new Aluno("Ana", 7.2);
		Aluno a2 = new Aluno("Lia", 5.2);
		Aluno a3 = new Aluno("Bia", 10.0);
		List<Aluno> alunos = Arrays.asList(a1, a2, a3);
		Predicate<Aluno> aprovado = a -> a.nota >= 7;
		Comparator<Aluno> melhorNota = (aluno1, aluno2) ->{
			if(aluno1.nota > aluno2.nota) return 1;
			if(aluno1.nota < aluno2.nota) return -1;
			return 0;	
		};
		System.out.println(alunos.stream().max(melhorNota).get());
		System.out.println(alunos.stream().min(melhorNota).get());
 
~~~


# Tratamento de Erros
## Tipos de Erros
* Erro de compilação
* Erro de Execução

# Padrão Observer
* Classe event -> Define as informações relevantes do evento (Carrega os dados do evento)
* Interface Observer -> todos os observadores implementam um 
* Subject -> responsavel por observar o evento e notificar os interessados


# Swing


# Padrões de projeto
* Definir o nome dos pacotes com o dominio da sua empresa ao contrário Ex: br.com.cod3r
* Pacote model ou modelo -> representam a lógica
* Pacote view ou visao -> a parte que interagem com o usuário (UI)


# Generics
* Classe<TIPO>
* É uma clase de tipo não especificado
* O tipo só é especificado na hora de criar o objeto


# O que utilizar?
* Métodos com uma única responsabilidade
* Interfaces para separar a parte de documentação do swagger
* Feign para requisições e em casos que não possa ser feito com o feign utilizar o RestTemplate
* Utilizar lombok para getters e setters sempre que possível
* Utilizar @RequiredArgsConstructor para injeção de dependências
* Enums no padrão UPPER_CASE
* Spring boot 2.5.0 ou +
* Java 16 ou +
* Utilizar mapstruct para conversão de DTOS em Entidades e vice-versa.
*  Use substantivos em vez de verbos em caminhos de endpoint
* Métodos pequenos e com no máximo 3 parâmetros
* Utilizar paginação em listagems
* Utilizar os Status Http correspondentes
* A camada service deve retornar apenas DTO para camada de controller
* A camada service somente deve retornar uma entidade caso seja possível acessa-lo de dentro da própria camada (modificador default ou protected)
* Para uma classe, caso seja necessário criar somente um com determinada assinatura. Casos onde necessitamos construir o objeto de forma diferente devemos utilizar métodos estáticos no padrão factory, por examplo MinhaClasse.of(name, desc)
* Métodos Mappers e/ou Parsers devem ser separados em uma classe expecífica
* MapStruct para mappers sempre que possível
* Sempre que houver criação/alteração de entidades na base relacional enviar o script para o tenant-manager
* Regras de negócios devem ser separadas por services, sempre seguindo o nome do seu contexto
* Sempre que possível utilizar a tipagem
* Em ts separar as classes em módulos
* Sempre que possível optar por lambda
* Sempre que facilitar utilizar novos recursos da linguagem
* Rodar o checkstyle, eslint e corrigir os erros antes de commitar
* Utilizar o logger em ts ao invés de console
* Utilizar o window.console em js para o front
* No backend , sempre logar os erros
# O que não utilizar?
* Exceções genéricas
* Documentação swagger na classe
* Fors aninhamos
* Try caths aninhados
* Métodos com múltiplas responsabilidades
* Comentários no código
* Nome de variável sem um sentido dentro do contexto
* @Autowired para injeção de dependências
* Pacotes fora do padrão mvc
* Estrutura do projeto em pastas desnecessárias
* Requisições com webflux
* Controle de transações manuais
* Propriedades adicionadas no application sem um valor default(permitido somente credenciais de ambientes GCP)
* Enums com valores minusculos
* Caracteres especiais com encode quebrado
* Não comitar arquivos gerados localmente, ex: target/* , arquivos lock, node_module...
* Em ts nunca colocar como provider uma classe que não pertence ao módulo
* Nunca utilizar hardcode
* Nunca alterar regras de checkstyle, editorconfig ou eslint
* Nunca utilizar diretamente o console ou alert
* Nunca ignorar erros que caem no try catch
 
 
 # Spring
- https://cursos.alura.com.br/course/logica-programacao-javascript-html
- https://cursos.alura.com.br/course/logica-programacao-pratica-com-desenho-animacoes-em-jogo
- https://cursos.alura.com.br/course/java-primeiros-passos
- https://cursos.alura.com.br/course/java-introducao-orientacao-objetos
- https://cursos.alura.com.br/course/java-heranca-interfaces-polimorfismo
- https://cursos.alura.com.br/course/java-excecoes
- https://cursos.alura.com.br/course/java-pacotes-e-java-lang
- https://cursos.alura.com.br/course/java-util-lambdas
- https://cursos.alura.com.br/course/java-trabalhando-com-io
- https://cursos.alura.com.br/course/servlets-fundamentos-programacao-web-java
- https://cursos.alura.com.br/course/servlet-autenticacao-autorizacao-mvc
- https://cursos.alura.com.br/course/maven-gerenciamento-dependencias-build-aplicacoes-java
- https://cursos.alura.com.br/course/mysql-manipule-dados-com-sql
- https://cursos.alura.com.br/course/jdbc-dao-persistencia
- https://cursos.alura.com.br/course/persistencia-jpa-introducao-hibernate
- https://cursos.alura.com.br/course/spring-data-jpa
- https://cursos.alura.com.br/course/spring-mvc-thymeleaf-bootstrap
- https://cursos.alura.com.br/course/spring-mvc-security-rest-vuejs-ajax
- https://cursos.alura.com.br/course/spring-boot-api-rest
- https://cursos.alura.com.br/course/spring-boot-seguranca-cache-monitoramento
- https://cursos.alura.com.br/course/spring-boot-profiles-testes-deploy
- https://www.alura.com.br/formacao-spring-framework