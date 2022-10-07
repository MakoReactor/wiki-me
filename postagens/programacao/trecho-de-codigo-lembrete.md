# Trecho de código lembrete

Shhell script para decodificar video em mp3\
e youtube dl baixando direto em mp3 playlists



```bash
for FILE in *.webm; do
    echo -e "Processing video '\e[32m$FILE\e[0m'";
    ffmpeg -i "${FILE}" -vn -ab 128k -ar 44100 -y "${FILE%.webm}.mp3";
done;


youtube-dl --extract-audio --audio-format mp3 -o "%(title)s.%(ext)s" https://www.youtube.com/playlist?list=PLiSzxQJ4pCKzj_rCvdJ5xRIzq02ROG5bh

```
