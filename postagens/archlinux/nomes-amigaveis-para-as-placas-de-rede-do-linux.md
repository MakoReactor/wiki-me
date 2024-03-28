---
description: >-
  Trocar os nomes das placas de rede do Linux para nomes mais amigáveis como
  eth0 e wlan0.
---

# Nomes amigáveis para as placas de rede do Linux

Essa abordagem visa mudar os nomes das placas de rede no linux, pois muitos sistemas agora trazem nomes estranhos diferentes daqueles que estávamos acostumados.

Esse procedimento foi feito no Manjaro Linux, mas creio que possa ser feito em outras distros.

Para esse procedimento dar certo é necessário que o Grub esteja instalado.

Eu usei o nvim, mas pode ser usado o editor da sua preferência.

```bash
sudo nvim /etc/default/grub
```

Procurar a Linha:

```bash
GRUB_CMDLINE_LINUX=""
```

E modificar para ficar dessa forma:

```bash
GRUB_CMDLINE_LINUX="net.ifnames=0 biosdevname=0"
```

Depois salvar e fechar o arquivo e então digite o comando:

```bash
sudo update-grub
```

Agora basta reniciar o computador.

Se tudo deu certo agora as placas de rede do seu sistema aparecerão com os nomes mais amigáveis como eth0, eth1 e wlan0.
