# Instalar ArchLinux no WSL (Windows subsystem Linux)

Tenha o WSL no Windows 10 ou posterior instalado e funcionando. Baixe o arquivo do ArchLinux nesse link -> [ArchLinux](https://github.com/yuk7/ArchWSL/releases/tag/22.3.18.0) é o primeiro arquivo zipado. Descompacte o o arquivo na raiz do seu HD (pode ser em outra pasta, mas eu prefiro assim).&#x20;

O ArchLinux não tem uma versão instalável pela loja do Windows (pelo menos até o momento desse post)

Dentro da pasta descompactada tem o arquivo _Arch.exe_, dê dois cliques que ele se auto registra no WSL abra novamente o Windows Terminal (se não intalou o windows terminal aproveite agora não vai se arrepender) e acesse o Arch recem instalado.

Próximas etapas:

Configurando o sudo e usuário padrão:

```
echo "%wheel ALL=(ALL) ALL" > /etc/sudoers.d/wheel
(setup sudoers file.)

useradd -m -G wheel -s /bin/bash "seu-usuario-sem-aspas"
(add user)

passwd "seu-usuario-sem-aspas"
(set default user password)

exit
```

O comando abaixo deve ser executado no cmd (prompt de comando) do windows dentro da pasta que o Arch foi descompactado. Ele vai fazer com que o WSL inicie o seu Archlinux com o usuário que acabamos de criar.

```
Arch.exe config --default-user "seu-usuario-sem-aspas"
    (setting to default user)
```

* atualizar as chaves do arch
* atualizar o sistema
* (continua)

