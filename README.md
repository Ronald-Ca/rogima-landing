# ROGIMA — Landing page

Site institucional da **ROGIMA Tecnologia**. Página estática (HTML + CSS, sem build),
servida por nginx e publicada no Dokploy.

## Estrutura

```
index.html      # a página (tudo inline: CSS + JS)
assets/mark.png # marca ROGIMA (duplo check) usada como favicon e máscara do gradiente
Dockerfile      # imagem nginx que serve a página
nginx.conf      # gzip + cache de assets
```

## Rodar local

```bash
# qualquer servidor estático
python -m http.server 8777
# abra http://localhost:8777

# ou via Docker (igual produção)
docker build -t rogima-landing .
docker run --rm -p 8080:80 rogima-landing
# abra http://localhost:8080
```

## Deploy

Hospedado no Dokploy (`dokploy.rogima.com.br`) via **custom git + Dockerfile**.
Um `git push` na branch `main` dispara o redeploy quando o webhook está ativo.
