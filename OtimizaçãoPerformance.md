# Otimização de Performance e Velocidade da Aplicação

Quero que você faça uma auditoria completa de desempenho no projeto e implemente as melhorias necessárias para tornar a aplicação mais rápida, leve, responsiva e preparada para receber um número maior de usuários simultâneos.

**Objetivo principal:** eliminar lentidão, reduzir o tempo de carregamento das páginas, diminuir o consumo de recursos do servidor e melhorar a experiência dos usuários, principalmente em dispositivos móveis e conexões lentas.

Não quero apenas recomendações. Analise o código existente, identifique os problemas e implemente as correções necessárias.

## 1. Carregamento e experiência do usuário

- Implemente Skeleton Loading nas páginas, cards, tabelas e componentes que dependem de carregamento de dados.
- Utilize Lazy Loading para imagens que estejam fora da área visível da tela.
- Evite que a página fique em branco enquanto aguarda respostas do servidor.
- Implemente atualizações otimistas da interface (Optimistic UI), quando apropriado.
- Evite renderizações desnecessárias de componentes.
- Utilize SSR ou SSG quando a arquitetura e o tipo de página permitirem.
- Divida o JavaScript por páginas e funcionalidades (Code Splitting).
- Carregue scripts de terceiros somente depois que o conteúdo principal estiver disponível.
- Utilize fontes locais e limite a quantidade de pesos carregados.

## 2. Otimização de imagens e arquivos estáticos

- Converta e disponibilize imagens nos formatos WebP ou AVIF, mantendo qualidade adequada.
- Implemente redimensionamento de imagens conforme a necessidade de cada componente.
- Utilize CDN para distribuir arquivos estáticos.
- Configure cache de arquivos estáticos no navegador.
- Utilize compressão Brotli ou Gzip nas respostas HTTP.
- Remova arquivos, bibliotecas e dependências que não estejam sendo utilizados.
- Evite carregar recursos desnecessários em páginas que não precisam deles.

## 3. Otimização de API e comunicação

- Identifique e elimine chamadas duplicadas à API.
- Implemente debounce nos campos de pesquisa, filtros e autocompletar.
- Utilize paginação nas consultas que retornam grandes volumes de dados.
- Execute requisições independentes em paralelo sempre que possível.
- Configure timeout e tratamento de falhas nas APIs externas.
- Evite requisições desnecessárias ao navegar entre páginas.
- Implemente cache para respostas que não precisam ser atualizadas constantemente.
- Utilize respostas compactas, retornando somente os dados necessários.
- Implemente cancelamento de requisições obsoletas quando aplicável.

## 4. Banco de dados e servidor

- Identifique e corrija consultas N+1.
- Crie índices para colunas utilizadas frequentemente em pesquisas, filtros e relacionamentos.
- Evite utilizar SELECT * quando apenas algumas colunas são necessárias.
- Implemente pool de conexões com o banco de dados.
- Otimize consultas SQL lentas e relacionamentos entre tabelas.
- Utilize Redis para armazenar em cache os dados mais consultados, quando disponível.
- Configure invalidação de cache para evitar dados desatualizados.
- Mantenha o servidor de aplicação próximo geograficamente do banco de dados.
- Avalie o uso de filas para tarefas demoradas, como processamento de arquivos, envio de notificações e outras operações que não precisam bloquear a resposta ao usuário.
- Avalie a possibilidade de distribuir o tráfego entre múltiplas instâncias do servidor, caso a demanda justifique.

## 5. Recursos de inteligência artificial

Caso a aplicação possua funcionalidades de IA:

- Implemente streaming de respostas, exibindo os tokens progressivamente ao usuário.
- Evite bloquear a interface enquanto a IA processa uma resposta.
- Configure timeout nas requisições aos provedores externos.
- Evite chamadas duplicadas para a mesma solicitação.
- Implemente controle de erros, tentativas e cancelamento de operações.
- Utilize filas para operações de IA demoradas quando apropriado.

## 6. Otimização de listas e componentes

- Implemente virtualização em listas muito extensas.
- Carregue somente os registros necessários para a página atual.
- Evite renderizar grandes quantidades de elementos simultaneamente.
- Utilize paginação ou carregamento progressivo.
- Otimize tabelas, dashboards, gráficos e componentes que realizam muitas operações.
- Evite atualizações completas da página quando apenas um componente precisar ser atualizado.

## 7. Monitoramento e diagnóstico

- Implemente rastreamento de requisições lentas utilizando OpenTelemetry, se compatível com a infraestrutura.
- Identifique endpoints que apresentam maior tempo de resposta.
- Monitore erros, falhas de comunicação e consumo de recursos.
- Avalie métricas de desempenho com dados reais dos usuários (Real User Monitoring).
- Identifique gargalos no frontend, backend e banco de dados.
- Registre o tempo de execução das consultas mais importantes.

## 8. Testes de desempenho

Após as implementações:

- Teste o carregamento das páginas em dispositivos móveis.
- Simule conexões lentas e instáveis.
- Verifique o comportamento em diferentes tamanhos de tela.
- Teste pesquisas, filtros, paginações e formulários.
- Avalie o desempenho com múltiplos usuários simultâneos.
- Verifique se as otimizações não provocaram erros ou perda de funcionalidades.
- Compare os indicadores de desempenho antes e depois das alterações.

## 9. Regras obrigatórias de implementação

1. Antes de modificar qualquer arquivo, analise a arquitetura e identifique a tecnologia utilizada no projeto.
2. Não introduza tecnologias como Redis, CDN, filas ou OpenTelemetry sem verificar a compatibilidade com a infraestrutura atual.
3. Não instale dependências desnecessárias.
4. Preserve todas as funcionalidades existentes.
5. Não altere a identidade visual, o layout ou o comportamento dos componentes sem necessidade.
6. Não remova funcionalidades para conseguir melhorar os indicadores de velocidade.
7. Preserve a compatibilidade com dispositivos Android, iOS e computadores.
8. Evite soluções complexas quando uma implementação simples resolver o problema.
9. Faça as alterações por etapas, verificando se cada melhoria realmente funciona.
10. Não utilize dados fictícios para simular melhorias de desempenho.

## 10. Relatório final

Ao concluir, apresente um relatório contendo:

- Problemas de desempenho encontrados.
- Arquivos modificados.
- Otimizações implementadas.
- Dependências adicionadas ou removidas.
- Melhorias realizadas no frontend, backend e banco de dados.
- Testes executados e respectivos resultados.
- Gargalos que ainda precisam de atenção.
- Melhorias que dependem de infraestrutura externa ou configuração de produção.

**Resultado esperado:** uma aplicação rápida, estável, responsiva e preparada para crescer, sem prejudicar a experiência dos usuários ou comprometer as funcionalidades existentes.

Priorize melhorias que tragam impacto real na velocidade da aplicação. Não faça alterações apenas para adicionar tecnologias ou seguir tendências.
