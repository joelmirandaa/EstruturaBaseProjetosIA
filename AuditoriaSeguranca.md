# AUDITORIA COMPLETA DE SEGURANÇA — AJUDA CÁ

Atue como um engenheiro de software sênior especializado em segurança de aplicações web, PHP, banco de dados, APIs e integrações de pagamento.

Seu objetivo é realizar uma auditoria completa de segurança no projeto **Ajuda Cá (AjudaCaSaas)**. Analise o código-fonte, identifique vulnerabilidades, avalie os riscos e corrija os problemas encontrados.

Não se limite a procurar problemas superficialmente. Inspecione a implementação real, acompanhe o fluxo de dados entre frontend, backend e banco de dados e verifique se as proteções realmente funcionam.

## 1. Reconhecimento e análise da arquitetura

Antes de modificar qualquer arquivo:

- Analise toda a estrutura do projeto.
- Leia a documentação existente.
- Identifique as tecnologias utilizadas.
- Mapeie as rotas, controllers, serviços, modelos e integrações.
- Identifique os pontos de entrada de dados.
- Analise a comunicação entre frontend, backend e banco de dados.
- Identifique áreas administrativas e funcionalidades restritas.
- Mapeie os fluxos de autenticação, autorização e pagamentos.

Crie uma visão geral da arquitetura e identifique os principais pontos de risco.

## 2. Auditoria de segurança da aplicação

Utilize como referência as recomendações da OWASP, especialmente OWASP Top 10.

Verifique:

**Autenticação e autorização**
- Proteção das áreas administrativas.
- Validação de sessões.
- Controle de acesso por perfil.
- Prevenção contra acesso indevido a funcionalidades restritas.
- Proteção contra IDOR.
- Verificação de permissões diretamente no backend.
- Prevenção contra escalonamento de privilégios.
- Segurança no processo de login e logout.

**Banco de dados**
- Proteção contra SQL Injection.
- Uso correto de consultas preparadas.
- Validação e tratamento de parâmetros.
- Proteção das operações de leitura, inserção, atualização e exclusão.
- Verificação de permissões nas operações CRUD.
- Proteção contra manipulação de identificadores.

**Tratamento de entradas e saídas**
- Proteção contra XSS armazenado e refletido.
- Proteção contra CSRF.
- Validação e sanitização de dados.
- Tratamento seguro de textos enviados pelos usuários.
- Prevenção contra execução de comandos ou códigos maliciosos.
- Separação entre dados armazenados e instruções executáveis.

**Sessões e cookies**
- Configuração segura dos cookies.
- Verificação de HttpOnly, Secure e SameSite.
- Proteção contra session fixation.
- Regeneração de identificadores de sessão.
- Expiração e encerramento adequado das sessões.

**Arquivos e uploads**
- Validação de extensão e MIME type.
- Limitação de tamanho.
- Proteção contra upload de arquivos executáveis.
- Geração de nomes seguros.
- Proteção contra path traversal.
- Verificação dos diretórios de armazenamento.

**Configurações**
- Análise dos arquivos de configuração.
- Verificação de mensagens de erro que exponham informações internas.
- Proteção de arquivos sensíveis.
- Análise de permissões de diretórios.
- Verificação de dependências desatualizadas ou vulneráveis.

## 3. Auditoria do painel administrativo

Analise todas as funcionalidades administrativas.

Verifique se:

- As rotas administrativas exigem autenticação.
- As permissões são verificadas no servidor.
- Usuários comuns não conseguem executar ações administrativas.
- A exclusão de registros exige autorização.
- A alteração de status não pode ser manipulada externamente.
- Os identificadores enviados pelo frontend são validados.
- As operações administrativas não podem ser executadas diretamente sem autorização.

Teste especialmente as operações de cadastro, edição, exclusão e alteração de status.

## 4. Auditoria da integração InfinitePay

Faça uma análise específica de toda a integração de pagamentos.

Verifique:

- Como os pagamentos são iniciados.
- Como os valores são definidos.
- Como a causa da doação é identificada.
- Como o identificador da transação é armazenado.
- Como o retorno do checkout é processado.
- Como o sistema confirma que um pagamento realmente aconteceu.
- Se existe possibilidade de falsificar uma confirmação de pagamento.
- Se o usuário consegue alterar o valor ou a finalidade da transação.
- Se existe possibilidade de reutilizar uma confirmação antiga.
- Se há proteção contra processamento duplicado.
- Se o sistema diferencia pagamento pendente, aprovado, recusado e cancelado.

Analise especificamente a validação realizada por meio de:

`POST https://api.checkout.infinitepay.io/payment_check`

Verifique os parâmetros enviados, a resposta recebida, a validação dos dados e o comportamento do sistema diante de respostas inválidas.

**Atenção especial:** não considere um simples redirecionamento do checkout ou uma mensagem enviada pelo frontend como confirmação de pagamento.

Caso exista alguma validação sem autenticação criptográfica ou mecanismo confiável de confirmação, identifique o risco e proponha uma implementação segura, respeitando a documentação oficial da InfinitePay.

## 5. Auditoria local do Git e gerenciamento de credenciais

Faça uma análise do repositório e do histórico local de versionamento.

Verifique:

- Arquivos `.env` e outras configurações sensíveis.
- Senhas e credenciais inseridas diretamente no código.
- Tokens de API.
- Chaves privadas.
- Credenciais do banco de dados.
- Arquivos de configuração que não deveriam ser versionados.
- Histórico de commits em busca de informações sensíveis.
- Arquivos que deveriam estar no `.gitignore`.
- Possíveis segredos presentes em versões anteriores dos arquivos.

Analise também se as alterações atuais podem introduzir credenciais no próximo commit.

Não considere que remover uma credencial do código atual resolve o problema se ela continuar presente no histórico do Git.

Não altere o histórico de commits automaticamente. Caso encontre credenciais expostas, identifique o problema e recomende a rotação das respectivas chaves.

O repositório é privado. Não é necessário implementar configurações de proteção de branches, permissões administrativas ou políticas de segurança do GitHub.

## 6. Testes e validação das correções

Após identificar e corrigir as vulnerabilidades:

- Teste os fluxos de autenticação.
- Teste as permissões de usuários comuns e administradores.
- Teste as operações CRUD.
- Teste o envio de dados maliciosos.
- Teste os uploads.
- Teste as operações financeiras.
- Teste as respostas inválidas da API de pagamento.
- Verifique se as correções não quebraram funcionalidades existentes.

Não execute testes destrutivos em dados reais de produção. Utilize um ambiente seguro e dados de teste.

Não considere uma vulnerabilidade corrigida apenas porque o código foi alterado. Sempre que possível, valide o comportamento após a correção.

## 7. Relatório de auditoria

Ao finalizar, documente os resultados em um arquivo:

`docs/auditoria-seguranca.md`

O documento deverá apresentar:

- Resumo da auditoria.
- Tecnologias e áreas analisadas.
- Vulnerabilidades encontradas.
- Arquivos envolvidos.
- Descrição dos riscos.
- Nível de criticidade: crítico, alto, médio ou baixo.
- Correções realizadas.
- Testes executados.
- Problemas que permaneceram pendentes.
- Recomendações adicionais.

Diferencie claramente vulnerabilidades confirmadas, possíveis riscos e recomendações preventivas.

## 8. Regras de execução

1. Faça uma análise completa antes de começar a modificar o código.
2. Não altere funcionalidades que não estejam relacionadas às correções de segurança.
3. Preserve a arquitetura e as tecnologias existentes.
4. Não introduza frameworks desnecessários.
5. Não remova funcionalidades para simplesmente eliminar vulnerabilidades.
6. Não utilize soluções superficiais ou validações exclusivamente no frontend.
7. Priorize correções no backend.
8. Não invente mecanismos de segurança sem verificar sua compatibilidade com as tecnologias utilizadas.
9. Não exponha credenciais durante a auditoria.
10. Não faça commits ou pushes automaticamente.
11. Preserve o funcionamento atual do sistema.
12. Caso encontre um problema que exija uma mudança arquitetural significativa, documente o motivo antes de implementá-la.

**Resultado esperado:**

Entregar o Ajuda Cá com as vulnerabilidades identificadas e corrigidas, mantendo suas funcionalidades existentes, com validações efetivas no backend e um relatório técnico documentando todo o processo.

A auditoria deve ser baseada no código real do projeto. Não marque itens como seguros sem verificar sua implementação.
