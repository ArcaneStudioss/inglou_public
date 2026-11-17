# Inglou

Plataforma de inglês por assinatura para crianças, adolescentes e adultos, com estudo individual e turmas de professores. A idade define temas e linguagem; o nível define a dificuldade.

> Estudo de caso. O código-fonte é privado.

## O que faz
- **Trilha personalizada** por objetivo, nível e desempenho, e não por "estilo de aprendizagem". Mede o que a pessoa acerta em cada modo (ler, escrever, ouvir) e treina o ponto fraco.
- **Tutor com IA** (Claude) com **modo de prática sem IA**: o app funciona inteiro com correção por regras, e a IA entra como camada extra, com cotas por plano.
- **Rádio**: episódio diário gerado a partir dos erros recentes do aluno, com voz sintetizada.
- **Turmas:** professor cria atividades, publica por versão e vê métricas, sem acesso ao que o aluno digitou. Privacidade definida por regra.
- **Conteúdo cultural** "Do Brasil pro mundo": 60 fichas de expressões regionais com fontes.
- Amigos, desafios, coleção de figurinhas e mascote, com regras de economia documentadas.

## Decisões técnicas
- Servidor HTTP **sem framework**, SQLite nativo e front-end em módulos JS **sem etapa de build**.
- **Gabarito nunca vai ao navegador:** a correção é feita no servidor.
- Cookies `__Host-` HttpOnly, CSP sem `unsafe-inline`, scrypt para senhas, JWT cifrado no servidor com Supabase Auth.
- Testes de segurança: IDOR entre alunos, força bruta, CSRF, injeção e limites de corpo.
- Conformidade: exportação e exclusão de dados; cadastro de menores com confirmação do responsável.
- Backup cifrado diário e restauração testada.

## Stack
Node.js 22 · SQLite · Supabase Auth · Claude API · ElevenLabs · Playwright · Docker

## Autor
Gabriel · [GitHub](https://github.com/ArcaneStudioss)
