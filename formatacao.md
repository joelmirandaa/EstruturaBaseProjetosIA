# INSTRUÇÕES DE FORMATAÇÃO E ORGANIZAÇÃO DE CÓDIGO

Sempre que criar, editar, corrigir ou reformatar códigos, siga estas instruções, independentemente da linguagem de programação utilizada.

## 1. Regras gerais

- Identifique automaticamente a linguagem e aplique suas convenções de formatação.
- Priorize código limpo, organizado, legível e consistente.
- Utilize indentação uniforme, respeitando a estrutura de cada linguagem.
- Organize blocos, funções, métodos, classes, condições e estruturas de repetição.
- Use quebras de linha para separar instruções e facilitar a leitura.
- Evite linhas excessivamente longas. Utilize aproximadamente 120 caracteres como referência, respeitando as convenções da linguagem.
- Separe blocos lógicos com linhas em branco quando necessário.
- Mantenha os elementos filhos indentados dentro de seus respectivos elementos pais.
- Evite código comprimido, instruções desnecessariamente agrupadas e estruturas difíceis de acompanhar.
- Não adicione comentários desnecessários nem altere comentários existentes durante uma simples formatação.

## 2. Indentação por linguagem

- **HTML/XML:** 2 espaços por nível de hierarquia.
- **CSS/SCSS:** 2 espaços por nível.
- **JavaScript/TypeScript/Node.js:** 2 espaços por nível.
- **PHP:** 4 espaços em blocos PHP puros e 2 espaços na estrutura HTML.
- **Java:** 4 espaços por nível.
- **Python:** 4 espaços por nível, seguindo a PEP 8.
- **SQL:** organize consultas em múltiplas linhas, com cláusulas bem separadas.
- **JSON/YAML:** 2 espaços por nível, respeitando a sintaxe específica.
- **Outras linguagens:** utilize o padrão recomendado pela comunidade ou pelo projeto.

Nunca misture tabulações e espaços no mesmo arquivo, salvo quando o formato exigir.

## 3. Organização das estruturas

- Coloque instruções independentes em linhas separadas.
- Indente corretamente o conteúdo de funções, classes, métodos, condições e loops.
- Organize imports, requires e dependências em blocos coerentes, sem alterar sua ordem quando isso puder afetar o comportamento.
- Separe declarações, inicializações, processamento e retorno quando melhorar a leitura.
- Mantenha estruturas aninhadas visualmente organizadas.
- Preserve a ordem original de execução.
- Não divida expressões de maneira que altere sua interpretação.
- Evite múltiplas instruções na mesma linha, exceto quando a sintaxe ou a convenção justificar.

## 4. HTML e templates

- Organize os elementos conforme sua hierarquia.
- Utilize um elemento estrutural por linha.
- Elementos curtos contendo apenas texto podem permanecer em uma linha.
- Links, botões e componentes com vários elementos filhos devem ser organizados em múltiplas linhas.
- Mantenha atributos na mesma linha quando possível, quebrando linhas extensas de maneira consistente.
- Separe seções principais com linhas em branco.
- Preserve integralmente textos, atributos, classes, IDs e expressões dinâmicas.
- Respeite a sintaxe original de templates e componentes.
- Não converta estruturas PHP, JSX ou de outros templates para outra sintaxe durante uma simples formatação.

## 5. CSS e estilos

- Organize seletores, propriedades e blocos de forma consistente.
- Utilize uma declaração CSS por linha.
- Indente corretamente regras aninhadas.
- Separe blocos de seletores para facilitar a leitura.
- Preserve valores, unidades, seletores, especificidade e ordem das declarações.
- Não agrupe, reorganize ou remova propriedades automaticamente.

## 6. JavaScript, TypeScript, Java e Python

- Organize funções, métodos, classes, objetos e estruturas condicionais conforme as convenções da linguagem.
- Mantenha os blocos internos corretamente indentados.
- Quebre expressões extensas sem alterar sua execução.
- Preserve operadores, tipos, parâmetros, retornos e tratamento de exceções.
- Em Python, respeite rigorosamente a indentação, pois ela faz parte da sintaxe.
- Em JavaScript e TypeScript, preserve construções sensíveis à inserção automática de ponto e vírgula.
- Em Java, mantenha a organização convencional de classes, métodos e blocos.
- Em Node.js, siga as regras de JavaScript ou TypeScript e preserve a estrutura dos módulos.

## 7. PHP e SQL

- Organize instruções PHP em linhas separadas.
- Utilize linhas em branco entre grupos lógicos.
- Preserve exatamente as tags PHP existentes.
- Em templates, mantenha a sintaxe original das estruturas condicionais e de repetição.
- Formate consultas SQL extensas em múltiplas linhas.
- Organize cláusulas SELECT, FROM, JOIN, WHERE, GROUP BY, HAVING e ORDER BY.
- Preserve parâmetros, aliases, condições, operadores e a lógica das consultas.

## 8. Preservação do código existente

Quando solicitar apenas formatação:

- Altere exclusivamente indentação, espaçamento e quebras de linha que não modifiquem o comportamento.
- Não modifique nomes de variáveis, funções, métodos, classes ou arquivos.
- Não altere textos, mensagens, atributos, IDs ou caminhos.
- Não adicione, remova ou reorganize funcionalidades.
- Não modifique operadores, condições, consultas ou regras de negócio.
- Não corrija erros automaticamente.
- Não renomeie arquivos, pastas ou dependências.
- Não altere a estrutura lógica nem a ordem de execução.
- Não remova trechos considerados redundantes.
- Não aplique refatorações sem autorização.
- Preserve strings, comentários e conteúdos nos quais espaços ou quebras de linha sejam significativos.

Se alguma alteração visual puder modificar o comportamento, preserve o trecho original.

## 9. Criação e edição de códigos

Quando solicitar código novo ou alterações funcionais:

- Escreva o código já formatado e organizado.
- Respeite as convenções e a arquitetura existente no projeto.
- Mantenha consistência entre arquivos da mesma aplicação.
- Não introduza dependências, funcionalidades ou mudanças estruturais desnecessárias.
- Evite abreviações confusas e estruturas excessivamente compactas.
- Priorize legibilidade e manutenção sem adicionar complexidade desnecessária.

## 10. Entrega do resultado

- Quando solicitar um arquivo completo, devolva todo o conteúdo, sem omitir trechos.
- Não substitua partes do código por comentários como "restante permanece igual".
- Preserve a extensão e a linguagem original.
- Utilize blocos de código com a identificação correta da linguagem quando a entrega for no chat.
- Se o código for muito extenso, não o resuma nem o corte silenciosamente.
- Informe separadamente eventuais problemas identificados, sem corrigi-los quando a tarefa for apenas formatação.
- Se não for possível garantir que determinada mudança preserve o comportamento, mantenha o código original e explique a limitação.

**Regra principal:** a formatação deve melhorar a leitura e a organização do código sem modificar seu funcionamento. Em tarefas exclusivamente de formatação, nenhuma alteração funcional está autorizada.
