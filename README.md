# Gerenciador de Arquivos PHP

Sistema web de gerenciamento de arquivos desenvolvido em PHP para upload, listagem e download de arquivos com autenticação de usuários.

## 📋 Descrição

Este projeto é um sistema de gestão de arquivos que permite:
- **Upload de arquivos** sem necessidade de autenticação
- **Visualização e download de arquivos** protegidos por login
- **Listagem detalhada** de arquivos com informações de tamanho e data de modificação

## 🚀 Funcionalidades

- ✅ Upload de arquivos para o servidor
- ✅ Sistema de autenticação com usuário e senha
- ✅ Listagem de arquivos com detalhes (nome, tamanho, data)
- ✅ Download de arquivos autenticados
- ✅ Gerenciamento de sessões PHP
- ✅ Proteção de diretório uploads via configuração do servidor

## 🛠️ Tecnologias Utilizadas

- **PHP** - Linguagem de programação backend
- **MySQL** - Banco de dados para armazenamento de usuários
- **HTML5** - Estrutura das páginas
- **CSS3** - Estilização
- **Nginx** - Servidor web (com proteção de diretórios)

## 📁 Estrutura do Projeto

```
PHP-Website/
├── index.php          # Página inicial com informações do projeto
├── upload.php         # Página de upload de arquivos
├── download.php       # Página de login para acesso aos downloads
├── listar.php         # Listagem de arquivos (requer autenticação)
├── verificar.php      # Script de verificação de login
├── menu.html          # Menu de navegação do site
├── estilos.css        # Folha de estilos CSS
└── uploads/           # Diretório para armazenamento de arquivos
```

## ⚙️ Requisitos

- PHP 7.0 ou superior
- MySQL 5.7 ou superior
- Servidor web (Apache ou Nginx)
- Extensões PHP: mysqli, fileinfo

## 🔧 Instalação

### 1. Clone o repositório
```bash
git clone https://github.com/marcelo-m7/PHP-Website.git
cd PHP-Website
```

### 2. Configure o banco de dados

Crie um banco de dados MySQL chamado `usuarios`:

```sql
CREATE DATABASE usuarios;
USE usuarios;

CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    password VARCHAR(255) NOT NULL
);

INSERT INTO usuarios (username, password) VALUES ('test', 'test');
```

### 3. Configure o servidor

**Para Nginx**, adicione a seguinte configuração para proteger o diretório uploads:

```nginx
location /uploads {
    deny all;
}
```

### 4. Ajuste as permissões

Certifique-se de que o diretório `uploads/` tem permissões de escrita:

```bash
chmod 755 uploads/
```

## 🎯 Como Usar

### Upload de Arquivos
1. Acesse a página **Upload** no menu
2. Selecione o arquivo desejado
3. Clique em **Enviar**

### Download de Arquivos
1. Acesse a página **Download** no menu
2. Faça login com as credenciais:
   - **Usuário:** test
   - **Senha:** test
3. Visualize a lista de arquivos disponíveis
4. Clique em **Download** para baixar o arquivo desejado

## 🔐 Credenciais Padrão

- **Usuário:** test
- **Senha:** test

> ⚠️ **Importante:** Altere as credenciais padrão em ambiente de produção!

## 🔒 Segurança

### Implementado:
- Autenticação via sessão PHP
- Proteção do diretório uploads via configuração do servidor
- Verificação de tipo de requisição (POST)

### ⚠️ Melhorias Recomendadas:
- [ ] Implementar hash de senha (bcrypt/password_hash)
- [ ] Adicionar validação de tipo de arquivo no upload
- [ ] Implementar proteção contra SQL Injection (prepared statements)
- [ ] Adicionar limite de tamanho de arquivo
- [ ] Implementar CSRF token nos formulários
- [ ] Adicionar validação e sanitização de inputs

## 📝 Notas do Desenvolvedor

- Desenvolvido como parte do TP3 CTESP em Sistemas Informáticos
- Autor: Marcelo Santos (a79433)
- O acesso direto aos arquivos no servidor foi bloqueado via configuração do Nginx

## 📄 Licença

Este projeto é de código aberto e está disponível para fins educacionais.

## 👤 Autor

**Marcelo Santos**
- GitHub: [@marcelo-m7](https://github.com/marcelo-m7)

---

⭐ Se este projeto foi útil para você, considere dar uma estrela no repositório!
