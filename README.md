# Alias_dev

🎭 O que é um alias na AWS?
Um alias é tipo um apelido amigável que você dá pra um recurso, em vez de usar um nome ou ID todo complicado.

Pensa assim: o nome verdadeiro é “Maria das Graças Oliveira da Silva Costa Souza”,
mas você chama de “Graça”. Isso é um alias! 😂

💡 Onde a AWS usa aliases?
🟢 1. AWS KMS (Key Management Service) – 💥 o mais famoso!
Quando você cria uma chave (CMK), ela tem um ID feioso:

go
Copiar
Editar
1234abcd-56ef-78gh-90ij-1234567890kl
Você pode criar um alias mais amigável, tipo:

bash
Copiar
Editar
alias/minha-chave-decriptacao
🔐 Então, ao invés de ficar decorando esse ID feio, você só usa o alias. Muito mais tranquilo na hora de referenciar a chave, né?

🟢 2. AWS Lambda – 👩‍💻 outro lugar onde alias brilha!
No Lambda, você pode criar versões da sua função (v1, v2, etc.).

Um alias serve pra apontar pra uma dessas versões.

💡 Exemplo:

Você tem:

v1 (em produção)

v2 (teste com novos códigos)

Cria:

alias/prod → aponta pra v1

alias/dev → aponta pra v2

👉 Assim, você pode atualizar o alias prod pra apontar pra outra versão sem mudar a URL da função. Lindão pra fazer deploy com segurança!

🟢 3. IAM, Route 53, e outros
Às vezes, "alias" também pode ser só um nome alternativo amigável, por exemplo em domínios no Route 53 (tipo um "alias record" apontando pro S3 ou Load Balancer).

✅ TL;DR:
Onde?	O que faz?	Exemplo prático
KMS	Apelido pra chave	alias/producao-kms
Lambda	Apelido pra versão	alias/prod aponta pra v1
Route 53	Redirecionamento	www.site.com → S3 bucket
IAM às vezes	Nome alternativo pra roles/users (exibição)	

Se cair na prova:

“Como facilitar a referência a uma chave no KMS sem precisar do ID completo?”

💬 Você responde:

“Criando um alias com nome amigável, tipo alias/nome-da-chave.”
