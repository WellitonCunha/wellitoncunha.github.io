# Site de desenvolvedor — fonte dos arquivos

Estes arquivos **não** pertencem ao app. Eles são o conteúdo do site de
desenvolvedor, que precisa existir por dois motivos:

1. O AdMob só verifica o `app-ads.txt` se ele estiver na **raiz** do domínio
   declarado como site de desenvolvedor na ficha da Play Store.
2. A Play e o AdMob esperam que esse site dê informação sobre os apps e um canal
   de suporte.

## Por que um repositório separado, com nome exato

O rastreador do AdMob busca em `https://<domínio>/app-ads.txt` — sempre na raiz,
nunca numa subpasta. A política de privacidade está em
`wellitoncunha.github.io/politicas-goat-arena/`, que é um *project site* do
GitHub Pages e serve numa subpasta; de lá **não** é possível publicar na raiz.

Para ocupar a raiz é necessário um *user site*, e o GitHub exige que ele se chame
exatamente como o usuário:

```
wellitoncunha.github.io
```

## Como publicar

1. Criar no GitHub um repositório **público** chamado `wellitoncunha.github.io`
2. Copiar para a raiz dele o `app-ads.txt` e o `index.html` desta pasta
3. Em Settings → Pages, definir a origem como a branch `main`, pasta `/ (root)`
4. Conferir no navegador que `https://wellitoncunha.github.io/app-ads.txt`
   mostra o texto
5. No Play Console: Aumentar número de usuários → Presença na loja →
   Configurações da loja → Detalhes de contato → site
   `https://wellitoncunha.github.io`

Depois disso, a Play leva até 24 horas para o AdMob perceber o site, e o
rastreamento leva pelo menos outras 24 horas. O status no AdMob só muda nesse
prazo.

## O conteúdo do app-ads.txt

A linha é o trecho personalizado que o próprio AdMob fornece, com o ID de
publisher da conta:

```
google.com, pub-8915566704035927, DIRECT, f08c47fec0942fa0
```

- `google.com` é a plataforma que vende o inventário
- `pub-8915566704035927` é o ID da conta do publisher
- `DIRECT` é a natureza da relação: a conta é a dona do inventário
- `f08c47fec0942fa0` é o identificador da Google na autoridade de certificação
  do IAB

Se um dia entrar outra rede de anúncios no app, ela precisa de uma linha própria
aqui — senão aquela rede não consegue vender o inventário.

## Atenção ao mexer

O `app-ads.txt` só vale se ficar acessível. Renomear o repositório, desligar o
GitHub Pages ou trocar o site declarado na ficha da Play derruba a verificação,
e a receita cai sem aviso. Se precisar mudar o endereço, atualize os dois lados
no mesmo dia.
