# Certificados Online - Sistema de Venda de Certificados
<img width="1858" height="869" alt="image" src="https://github.com/user-attachments/assets/a7a39186-d50d-4cc6-8397-74ff08707f6f" />

## Sobre o projeto

Este é um sistema simples e funcional de **venda de certificados** (cursos, eventos, workshops etc.).  
O objetivo principal foi **aprender PHP e MySQL na prática**, por isso:

- Eu decidi a **estrutura do banco de dados**, as tabelas, relacionamentos e fluxos
- Planejei e implementei **como cada tela deveria funcionar** (lógica de negócio, validações, fluxo do usuário)
- Escolhi e organizei a **engenharia do software** (separação de responsabilidades, pastas, segurança básica, etc.)

Para agilizar algumas partes de texto (ex: redação de mensagens, comentários no código e este próprio README), utilizei **inteligência artificial** (Grok da xAI) como assistente — mas sempre revisando, entendendo e adaptando tudo com minhas próprias mãos e decisões.

## Funcionalidades implementadas (até o momento)

- Cadastro e login de usuários com permissões (clientes e administradores)
- Catálogo de certificados disponíveis para compra
- Área do cliente: visualizar certificados comprados e baixar PDF
- Painel administrativo: gerenciar certificados, pedidos e usuários
- Sistema de carrinho gravado na session não sendo necessário login do cliente e finalização de compra
- Geração simples de certificado em PDF (usando biblioteca como FPDF)

## Tecnologias utilizadas

- **PHP** 8.x (puro, sem framework)
- **MySQL** / MariaDB
- **Apache** (servidor local e de teste)
- HTML5 + CSS3 (estilização simples e responsiva)
- JavaScript (validações leves no frontend)
- Bibliotecas auxiliares: 
  - FPDF (para geração de PDF)

# 2. Fluxo do Site
1. **Tela inicial (index.php)** → botão para escolher certificado ou consulta
2. **escolha.php** → cliente seleciona tipo (impressão ou moldura), preenche
Preços puxados da tabela precos
Aceite de Política de Privacidade e Termos de Uso (checkbox)
Dados salvos na sessão para adicionar mais itens
3. **carrinho.php** → mostra itens adicionados, total, botão finalizar
- Ao finalizar: gera código único (PED-XXXXXX), renomeia PDFs, salva cada
Mostra QR Code Pix (opcional via Mercado Pago) ou chave Pix + botão What.
4. **consulta.php** → cliente digita código → vê status e (futuro) codigo_env
5. **admin/pedidos.php** → painel admin (login via admins)
Lista pedidos agrupados por codigo_rastreio
Modais para ver dados pessoais, editar observações, ver lista de PDFS
Botão "Enviar para Pagamento" → abre WhatsApp com mensagem pronta (resum
Edita status, codigo_envio, observações
