# Instalar ArchLinux no WSL (Windows subsystem Linux)

Tenha o WSL no Windows 10 ou posterior instalado e funcionando. Baixe o arquivo do ArchLinux nesse link -> [ArchLinux](https://github.com/yuk7/ArchWSL/releases/tag/22.3.18.0) é o primeiro arquivo zipado. Descompacte o o arquivo na raiz do seu HD (pode ser em outra pasta, mas eu prefiro assim).

O ArchLinux não tem uma versão instalável pela loja do Windows (pelo menos até o momento desse post)

Dentro da pasta descompactada tem o arquivo _Arch.exe_, dê dois cliques que ele se auto registra no WSL abra novamente o Windows Terminal (se não intalou o windows terminal aproveite agora não vai se arrepender) e acesse o Arch recem instalado.

Próximas etapas:

Configurando o sudo e usuário padrão como root um de cada vez.

```
echo "%wheel ALL=(ALL) ALL" > /etc/sudoers.d/wheel

useradd -m -G wheel -s /bin/bash "seu-usuario-sem-aspas"

passwd "seu-usuario-sem-aspas"

exit
```

O comando abaixo deve ser executado no cmd (prompt de comando) do windows dentro da pasta que o Arch foi descompactado. Ele vai fazer com que o WSL inicie o seu Archlinux com o usuário padrão que acabamos de criar.

```
Arch.exe config --default-user "seu-usuario-sem-aspas"
    (setting to default user)
```

Agora antes de atualizar o sistema é bom rodar os comandos abaixo para o arch atualizar as chaves de verificação dos repositórios.

```
sudo pacman-key --init

sudo pacman-key --populate

sudo pacman -Syy archlinux-keyring
```

Agora já podemos atualizar o sistema.

A opção _**'--noconfirm'**_ serve para o Arch não ficar parando esperando a confirmação do usuário.

```
sudo pacman -Syu --noconfirm
```

Agora é só esperar o sistema terminar de atualizar e pronto já está pronto para as configurações e instalações de programas.

Fontes: [ArchWSL Documentation](https://wsldl-pg.github.io/ArchW-docs/How-to-Setup/)
