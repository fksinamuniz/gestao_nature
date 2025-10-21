Gestão de Suplementos - App de Estoque e Vendas

Este é um aplicativo completo para gerenciar a revenda de suplementos, controlando estoque, clientes, pedidos e finanças. Os dados são salvos em tempo real usando o Firebase.

Como Publicar seu Aplicativo no GitHub (Grátis)

Siga estes passos para ter seu próprio aplicativo online e funcionando com seu banco de dados.

Parte 1: Configurar o Banco de Dados (Firebase)

Você precisa de uma conta gratuita do Google para isso.

Criar um Projeto no Firebase:

Acesse o Firebase Console.

Clique em "Criar um projeto".

Dê um nome ao seu projeto (ex: "gestao-suplementos") e siga os passos na tela.

Ativar o Banco de Dados Firestore:

No menu à esquerda, clique em Build > Firestore Database.

Clique em "Criar banco de dados".

Selecione "Iniciar em modo de produção" e clique em "Avançar".

Escolha uma localização para o servidor (recomenda-se southamerica-east1 para o Brasil) e clique em "Ativar".

Ativar a Autenticação Anônima:

No menu à esquerda, clique em Build > Authentication.

Vá para a aba "Sign-in method".

Na lista, clique em "Anônimo", ative a chave e clique em "Salvar".

Configurar as Regras de Segurança:

Volte para o Firestore Database e clique na aba "Regras".

Substitua o conteúdo existente pelas regras abaixo e clique em "Publicar":

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Permite que qualquer pessoa leia e escreva os dados do app.
    // ATENÇÃO: Ideal para demonstração, mas para um app real,
    // você deve configurar regras mais seguras.
    match /artifacts/{appId}/public/data/{document=**} {
      allow read, write: if true;
    }
  }
}


Obter a Configuração do Firebase:

No menu, clique no ícone de engrenagem (ao lado de "Visão geral do projeto") e vá para "Configurações do Projeto".

Role a página para baixo até a seção "Seus apps".

Clique no ícone da web </>.

Dê um apelido para o seu aplicativo (ex: "Meu App Web") e clique em "Registrar app".

O Firebase mostrará um objeto chamado firebaseConfig. Copie todo esse bloco de código.

Parte 2: Atualizar o Código do Aplicativo

Cole sua Configuração:

Abra o arquivo index.html.

Procure pela seção que começa com // --- INÍCIO: CONFIGURAÇÃO DO FIREBASE ---.

Substitua o bloco de código de exemplo pelo firebaseConfig que você copiou do seu projeto.

Parte 3: Publicar no GitHub Pages

Crie um Repositório no GitHub:

Faça login no GitHub.

Crie um novo repositório público. Dê um nome a ele (ex: "app-gestao").

Faça o Upload dos Arquivos:

No seu novo repositório, clique em "Add file" > "Upload files".

Arraste os arquivos index.html e README.md para a área de upload.

Clique em "Commit changes".

Ative o GitHub Pages:

No seu repositório, vá para "Settings" (Configurações).

No menu lateral, clique em "Pages".

Em "Branch", selecione main e clique em "Save".

Acesse seu App!

Aguarde alguns minutos. O GitHub publicará seu site no endereço:
https://<seu-usuario>.github.io/<nome-do-repositorio>/

Pronto! Agora seu aplicativo está online, e todos os dados inseridos serão salvos permanentemente no seu banco de dados Firebase.
