## Autenticação da conta do GitHub via SSH

Agora vamos autenticar a sua conta e criar uma conexão entre o `Git` da sua máquina e a sua conta no `Github`.

Primeiro vamos checar se você já tem chaves SSH em sua máquina:

```bash
ls -al ~/.ssh
```
Se você receber um erro informando que ~/.ssh não existe, quer dizer que você não tem chaves `SSH`, então precisamos criar uma nova com o comando abaixo. Note que o seu endereço de email deve estar entre aspas.

```bash
ssh-keygen -t rsa -C "<seu email>"
```

Quando for solicitado "Enter file in which to save the key" (Inserir um arquivo no qual deseja salvar a chave), pressione Enter para aceitar o local padrão para salvar o arquivo com a chave. Em seguida, será solicitado "Enter passphrase", e no terminal, digite uma senha segura.

Dentre as mensagens que serão mostradas na tela, uma indicará onde a chave foi salva. Busque algo parecido com:

```
Your public key has been saved in <caminho para arquivo .pub>
```

Agora abra o arquivo contendo a chave, **selecione** todo o seu conteúdo e **copie** para o seu **clipboard**.

```bash
cat <caminho para arquivo onde está a chave> 
```

Pronto! Agora só precisamos adicionar essa chave na sua conta do Github. Para isso, vá nas [configurações da sua conta do github](https://github.com/settings/profile), clique em "SSH and GPG keys" à esquerda e depois em "New SSH key" à direita. Adicione um label à chave (você pode usar algo como "Meu Computador Pessoal") e depois cole a chave no local indicado.

![](https://raw.githubusercontent.com/WomenBioinfoDataScLA/Workshops/master/Git_%26GitHub/assets/paste_ssh.png)

Vamos testar a conexão, só pra ver se deu tudo certo? No terminal, corra:

```bash
ssh -T git@github.com
```

Você deve ver um aviso como este:

```
> The authenticity of host 'github.com (IP ADDRESS)' can't be established.
> RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
> Are you sure you want to continue connecting (yes/no)?
```

Digite `yes`. Se disser algo como o seguinte, funcionou:

```
Hi <seu login>! You've successfully authenticated, but Github does not provide shell access.
```
