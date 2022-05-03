---
description: Procedimento feito no ArchLinux.
---

# asdf - Gerenciador de versões de linguagens de programação

## O que é?

[**asdf-vm**](https://asdf-vm.com) é uma ferramenta de linha de comando para gerenciar versões de execução de múltiplas linguagens por projeto. É similar a outras ferramentas de gerenciamento por linha de comando, como [RVM](https://rvm.io) para Ruby e [nvm](https://github.com/nvm-sh/nvm) para Node.js, com a vantagem de um arquitetura de plugin extensível para lidar com múltiplas linguagens.

## Preparando o terreno para instalação.

Primeiro instalaremos o yay, que é um gerenciador de pacotes da base AUR do archlinux.

Mas antes as dependências.

```
sudo packman -S --needed base-devel git
```

Agora clonamos o projeto no github.

Como vamos usar só por esse momento fazemos isso na pasta **/tmp**.

```
cd /tmp
git clone https://aur.archlinux.org/yay-git.git
```

Depois entramos no diretório.

```
cd yay-git
```

E então compilamos o programa.

```
makepkg -si
```

Depois de compilado podemos testar com o comando de atualização do sistema.

```
yay -Syu
```

**\*OBS: Não use o yay com o sudo ou root, ele é esperto o suficiente para pedir a senha na hora certa.**

## **Instalando o asdf de fato.**

Após o procedimento acima vamos à instalação do asdf.

```
yay -S asdf-vm
```

O yay vai baixar, compilar e instalar o programa, pode ser necessário alguma confirmação do usuário ou pedido de senha e pode demorar mais ou menos dependendo da eficiência do computador.

Agora para carregar o **asdf** toda vez que o terminal for aberto faça o seguinte, usando o seu editor de preferência. Aqui eu vou estou usando o **zsh**, mas pode ser feito no **bash** padrão ou qualquer outro terminal que você tenha instalado.

```
# no meu caso eu uso o nvim
nvim ~/.zshrc

# ou se for bash padrão
nvim ~/.basrh

# adicione esse linha no final do arquivo
source /opt/asdf-vm/asdf.sh
```

Agora bastar salvar o arquivo e fechar o terminal. Quando abrir o terminal novamente o asdf já estará funcionando.

### Comandos básicos do asdf.

```
# Adicionar plugins para a linguagem, usei pythyon mas pode ser outra.
asdf plugin add python

# Verificar as versõs disponíveis da linguagem.
asdf list all python

# Instalar versão específica
asdf install python 3.10.4

# Instalar versão diferente sem conflitos.
asdf install python 3.9.12

# Usar uma versão local que só vai funcionar dentro da pasta que foi iniciada.
asdf local python 3.9.12

# Configurar uma versão do python para ser Global.
asddf global python 3.10.4
```

Da forma que foi descrita no quadro acima, na pasta que foi feito o comando asdf local vai ser usada a versão 3.9.12 do python e em qualquer outra pasta que não tenha a versão local vai ser usada a versão global 3.10.4, desta forma eu posso ter várias versões da mesma linguagem de programação e diferentes projetos.

O asdf pode gerenciar várias linguagens de programação:

* Java
* nodejs
* Ruby
* Python
* Elixir
* Fluter
* Golang
* R
* e muitas outras.

Para a listar os plugins instaláveis e os instalado digite:

```
# Listar todas linguagens passiveis de serem instaladas.
asdf plugin list all

# Listar somente os plugins instalados.
asdf plugin list
```
