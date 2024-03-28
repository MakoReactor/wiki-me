---
description: >-
  Trocar os nomes das placas de rede do Linux para nomes mais amigáveis como
  eth0 e wlan0.
---

# Nomes amigáveis para placas de rede no Linux.

Essa abordagem visa mudar os nomes das placas de rede no linux, pois muitos sistemas agora trazem nomes estranhos diferentes daqueles que estávamos acostumados.

Esse procedimento foi feito no Manjaro Linux, mas creio que possa ser feito em outras distros.

Para esse procedimento dar certo é necessário que o Grub esteja instalado.

Eu usei o neovim como editor de texto, mas você pode usar o seu editor de texto preferido.

Abra o arquivo com a linha de comando a seguir:

```bash
sudo nvim /etc/default/grub
```

Procure a Linha:

```bash
GRUB_CMDLINE_LINUX=""
```

E modifique essa linha para ficar igual abaixo.

```bash
GRUB_CMDLINE_LINUX="net.ifnames=0 biosdevname=0"
```

Salve o arquivo e feche o mesmo.

Agora digite o seguinte comando para atualizar o Grub com as novas regras.

```bash
sudo update-grub
```

Reinicie o seu computador.

Se tudo deu certo agora as placas de rede do seu sistema aparecerão com os nomes mais amigáveis como eth0, eth1 e wlan0.
