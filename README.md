# 🔐 Encrypton

Encrypton é um aplicativo **Windows Forms** escrito em **VB.NET** direcionado ao **.NET Framework 4.5** para criptografar e descriptografar textos com **TripleDES** a partir de uma chave configurável no `App.config`.

A tela principal centralizada disponibiliza campos de entrada e saída, botões para cifrar, decifrar e limpar, com mensagens amigáveis quando o texto não é informado.

---

## 🛠️ Tecnologias Utilizadas

<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/dot-net/dot-net-original.svg" alt=".NET" width="30" height="30"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" alt="Visual Studio" width="30" height="30"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/windows8/windows8-original.svg" alt="Windows" width="30" height="30"/>
</p>

- **VB.NET** – linguagem principal
- **.NET Framework 4.5** – plataforma alvo
- **Windows Forms** – interface gráfica fixa e centralizada
- **Visual Studio** – ambiente de desenvolvimento recomendado
- **App.config** – armazenamento da chave `EncryptKey`

---

## 📂 Estrutura do Projeto

- `Encrypton/Encrypton.sln` – solução do Visual Studio 2013/2015
- `Encrypton/Encrypton/Encrypton.vbproj` – projeto principal Windows Forms
- `Encrypton/Encrypton/Encrypton.Class/Encrypton.Class.Encrypton.vb` – classe `Encryption` com TripleDES e hash MD5 da chave
- `Encrypton/Encrypton/Encrypton.Main/Encrypton.Main.Main.vb` – eventos do formulário para criptografar, descriptografar e limpar campos
- `Encrypton/Encrypton/Encrypton.Main/Encrypton.Main.Main.Designer.vb` – definição da interface com controles de entrada, saída e botões
- `Encrypton/Encrypton/App.config` – chave `EncryptKey` configurável em tempo de execução

---

## ✅ Pré-requisitos

- Windows com **.NET Framework 4.5+** instalado
- **Visual Studio 2013** (ou versão mais recente compatível) para abrir a solução
- Permissão para editar `App.config` e executar aplicativos Windows Forms

---

## ⚙️ Configuração

1. **Chave de criptografia**
   - A classe `Encryption` lê `EncryptKey` do `App.config`, gera um hash MD5 e o utiliza como chave do `TripleDESCryptoServiceProvider`. Ajuste esse valor conforme a necessidade do ambiente.

2. **Interface do formulário**
   - O formulário limpa os campos no carregamento, define a saída como somente leitura e posiciona o foco na entrada ao ser exibido.

3. **Mensagens ao usuário**
   - A interface apresenta `MsgBox` quando o texto não é informado ou se ocorrer alguma exceção durante as operações.

---

## 🛠️ Compilação

1. Abra `Encrypton.sln` no **Visual Studio**.
2. Selecione a configuração desejada (`Debug` ou `Release`).
3. Compile o projeto `Encrypton` (`Build > Build Encrypton`).

---

## ▶️ Execução

1. Execute o aplicativo pelo Visual Studio ou abra o `Encrypton.exe` gerado em `bin\<Configuration>`.
2. Digite o texto desejado no campo **Texto de Entrada**.
3. Clique em **Encrypt** para gerar o conteúdo cifrado (string Base64) exibido em **Texto de Saída**.
4. Utilize **Decrypt** para reverter um texto cifrado com a mesma chave configurada.
5. Pressione **Clear** para limpar ambos os campos e reposicionar o foco na entrada.

---

## 🔎 Funcionamento

- `MD5Hash` transforma a chave configurada em bytes UTF-8 e calcula o hash MD5 usado pelo TripleDES.
- `Encrypt` converte o texto para ASCII, aplica `TripleDES` no modo ECB e retorna a saída em Base64.
- `Decrypt` recebe uma string Base64, reverte o conteúdo para ASCII e retorna vazio se o parâmetro estiver em branco.
- `btnClear` redefine os campos para continuar novas operações rapidamente.

---

## 📌 Observações

- O campo de saída permanece somente leitura para evitar alterações acidentais no resultado.
- Mensagens de aviso orientam o usuário sempre que o texto de entrada não estiver preenchido.
- Exceções são capturadas, registradas no console e convertidas em mensagens amigáveis.

---

## 📄 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).
