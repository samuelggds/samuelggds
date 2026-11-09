# MG Orçamentos — aplicação corporativa

**Desenvolvimento Full Stack · Projeto independente de Samuel Gomes**

## Problema e solução

A MG Refrigerações precisava organizar o trabalho administrativo com orçamentos, clientes, serviços, documentos e comunicação por e-mail. A aplicação centraliza esses fluxos e permite produzir documentos PDF associados aos orçamentos.

Este estudo de caso descreve a aplicação hospedada no repositório [Project-Budget](https://github.com/samuelggds/Project-Budget). O [site da MG Refrigerações](https://mgrefrigeracoes.com.br/) é institucional e não deve ser confundido com uma demonstração pública do painel administrativo.

## Funcionalidades documentadas no código

- Cadastro, edição e consulta de clientes e serviços.
- Criação de orçamentos, geração de PDF e acompanhamento do fluxo de status: Enviado → Em andamento → Aprovado → Pago, com Recusado como saída prevista.
- Autenticação Supabase, controle de acesso e segunda etapa de verificação por e-mail na área administrativa.
- Recebimento e organização de e-mails corporativos, inclusive anexos e histórico.
- Envio de mensagens e orçamentos PDF com integração ao Resend.
- Estrutura para uso em navegador e aplicativo desktop com Tauri.

## Arquitetura e decisões técnicas

| Camada | Tecnologias e responsabilidade |
| --- | --- |
| Interface | React, TypeScript e Vite |
| Identidade e dados | Supabase Auth, PostgreSQL, políticas RLS |
| API | Rotas de servidor para autenticação adicional e serviços de e-mail |
| E-mail de entrada | AWS SES → S3 → SQS → Lambda → Supabase |
| E-mail de saída | Resend com webhook de eventos |
| Documentos e desktop | pdf-lib e Tauri |

**Cuidados de engenharia:** credenciais externas restritas ao servidor, verificação de assinatura de webhook, controle da sessão autenticada e organização por módulos. A arquitetura real e as instruções técnicas podem ser examinadas no código e na documentação do projeto.

## Minha atuação

Planejamento da solução, implementação das interfaces, fluxos de orçamento, integração com provedores externos e cuidados com autenticação e manutenção. Sem atribuir números de usuários, receita ou ganhos de produtividade que não tenham sido medidos.

[Ver código](https://github.com/samuelggds/Project-Budget) · [Ver documentação de e-mail](https://github.com/samuelggds/Project-Budget/blob/main/docs/email-tauri-production.md) · [Voltar ao perfil](https://github.com/samuelggds) · [LinkedIn](https://www.linkedin.com/in/samuel-gomes08/)
