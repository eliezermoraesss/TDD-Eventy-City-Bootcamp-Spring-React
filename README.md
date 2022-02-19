# Testes automatizados no back end<br>

## Competências<br>
### Fundamentos de testes automatizados<br>
Tipos de testes<br>
Benefícios<br>
TDD - Test Driven Development<br>
Boas práticas e padrões<br>
### JUnit<br>
Básico (vanilla)<br>
Spring Boot<br>
Repositories<br>
Services<br>
Resources (web)<br>
Integração<br>

### Mockito & MockBean<br>
@Mock<br>
@InjectMocks<br>
Mockito.when / thenReturn / doNothing / doThrow<br>
ArgumentMatchers<br>
Mockito.verify<br>
@MockBean<br>
@MockMvc<br>

# Fundamentos de testes automatizados<br>
## Tipos de testes<br>
### Unitário<br>
Teste feito pelo desenvolvedor, responsável por validar o comportamento de unidades funcionais de código. Nesse contexto, entende-se como unidade funcional qualquer porção de código que através de algum estímulo seja capaz de gerar um comportamento esperado (na prática: métodos de uma classe). Um teste unitário não pode acessar outros componentes ou recursos externos (arquivos, bd, rede, web services, etc.).<br>
### Integração<br>
Teste focado em verificar se a comunicação entre componentes / módulos da aplicação, e também recursos externos, estão interagindo entre si corretamente.<br>
### Funcional<br>
É um teste do ponto de vista do usuário, se uma determinada funcionalidade está executando corretamente, produzindo o resultado ou comportamento desejado pelo usuário.<br>

## Beneficios<br>
Detectar facilmente se mudanças violaram as regras<br>
É uma forma de documentação (comportamento e entradas/saídas esperadas)<br>
Redução de custos em manutenções, especialmente em fases avançadas<br>
Melhora design da solução, pois a aplicação testável precisa ser bem delineada<br>
TDD - Test Driven Development<br>
É um método de desenvolver software. Consiste em um desenvolvimento guiado pelos testes.<br>

Princípios / vantagens:<br>
Foco nos requisitos<br>
Tende a melhorar o design do código, pois o código deverá ser testável<br>
Incrementos no projeto têm menos chance de quebrar a aplicação<br>

Processo básico:<br>
Escreva o teste como esperado (naturalmente que ele ainda estará falhando)<br>
Implemente o código necessário para que o teste passe<br>
Refatore o código conforme necessidade<br>

Boas práticas e padrões<br>
Nomenclatura de um teste<br>
<AÇÃO> should <EFEITO> [when <CENÁRIO>]<br>

Padrão AAA<br>
Arrange: instancie os objetos necessários<br>
Act: execute as ações necessárias<br>
Assert: declare o que deveria acontecer (resultado esperado)<br>

Princípio da inversão de dependência (SOLID)<br>
Se uma classe A depende de uma instância da classe B, não tem como testar a classe A isoladamente. Na verdade nem seria um teste unitário.<br>
A inversão de controle ajuda na testabilidade, e garante o isolamento da unidade a ser testada.<br>

Independência / isolamento<br>
Um teste não pode depender de outros testes, nem da ordem de execução<br>

Cenário único<br>
O teste deve ter uma lógica simples, linear<br>
O teste deve testar apenas um cenário<br>
Não use condicionais e loops<br>

## Previsibilidade<br>
O resultado de um teste deve ser sempre o mesmo para os mesmos dados<br>
Não faça o resultado depender de coisas que variam, tais como timestamp atual e valores aleatórios.<br>


## JUnit <br>
Visão geral<br>
https://junit.org/junit5<br>
O primeiro passo é criar uma classe de testes<br>
A classe pode conter um ou mais métodos com a annotation @Test<br>
Um método @Test deve ser void<br>
O objetivo é que todos métodos @Test passem sem falhas<br>
O que vai definir se um método @Test passa ou não são as “assertions” deste método<br>
Se um ou mais falhas ocorrerem, estas são mostradas depois da execução do teste<br>
