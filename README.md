# Configuração do github

## Descrição:
Processo para configurar o Github com chave SSH no seu Computador de Casa ou Trabalho.

### ✅ 1. **Configurar seu nome e e-mail no Git**
Esses dados são usados para identificar quem fez os commits.

Abra o terminal e digite:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@example.com"
```

Substitua com seu nome e e-mail reais (os mesmos do GitHub, GitLab, etc).

---

### ✅ 2. **Gerar e adicionar uma chave SSH (opcional, mas recomendado)**
Se você usa SSH para acessar o GitHub/GitLab, esse passo é importante.

#### 2.1. Gerar chave SSH:

```bash
ssh-keygen -t ed25519 -C "seuemail@example.com"
```

Aperte Enter para aceitar os caminhos padrão, e defina uma senha se quiser.

#### 2.2. Adicionar a chave ao ssh-agent:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

#### 2.3. Copiar a chave pública:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copie o conteúdo e cole nas configurações de SSH da sua conta no GitHub/GitLab/Bitbucket.

- **GitHub:** [https://github.com/settings/keys](https://github.com/settings/keys)

---

### ✅ 3. **Testar a conexão SSH com o GitHub**

```bash
ssh -T git@github.com
```

Se tudo estiver certo, vai aparecer uma mensagem de boas-vindas.

---

### ✅ 4. **Clonar seus projetos**

Agora você pode clonar seus repositórios:

```bash
git clone git@github.com:usuario/repositorio.git
```

Ou, se preferir usar HTTPS (sem SSH):

```bash
git clone https://github.com/usuario/repositorio.git
```

---

### ✅ 5. **Navegar para o projeto e começar a trabalhar**

```bash
cd repositorio
code .  # se estiver usando VS Code
```
