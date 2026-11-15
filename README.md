# Birfree Beta

A área de trabalho da Neovanguard para Arch Linux x86_64 (Wayland), em beta.
Pacotes prontos: nada é compilado no seu computador.

**Versão atual: 0.6.3** — ainda incompleta; a 1.0 sai quando não houver defeito
conhecido.

## Instalar

Baixe a Release mais nova, confira e instale:

```sh
curl -fLO https://github.com/NEOpisa/birfree-beta/releases/latest/download/Birfree-Beta-x86_64.tar.gz
curl -fLO https://github.com/NEOpisa/birfree-beta/releases/latest/download/SHA256SUMS
sha256sum --check SHA256SUMS
tar -xf Birfree-Beta-x86_64.tar.gz
cd Birfree-Beta-x86_64
./instalar-birfree
```

Depois, saia da sessão e entre em **Birfree**.

## Atualizar

```sh
curl -fLO https://raw.githubusercontent.com/NEOpisa/birfree-beta/main/atualizar-birfree
chmod +x atualizar-birfree
./atualizar-birfree
```

Funciona também para quem tem um dos testes antigos (1.0 teste 6.x): a Beta
0.5 entra por cima deles.

## O que vem no arquivo

Os pacotes `birfree`, `birfree-icons` e `birfree-terminal`, os instaladores,
`VERSOES.txt` (versões e a pilha KDE/Qt usada na compilação), `SHA256SUMS` e
os fontes em `fontes/Birfree-fontes.tar.gz` (GPL-3.0-or-later).

O instalador confere a integridade e a versão do KWin/Qt; se o sistema estiver
em outra, ele atualiza o sistema uma vez antes. O `pacman -Syu` depois disso
não atualiza o KDE nem o Qt (`/etc/pacman.d/birfree-congelar.conf`).
