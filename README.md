# Birfree Beta

A área de trabalho da Neovanguard para Arch Linux x86_64 (Wayland), em beta.
Pacotes prontos: nada é compilado no seu computador.

**Versão atual: 0.6.6** — ainda incompleta; a 1.0 sai quando não houver defeito
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

## Requisitos

- Arch Linux x86_64 (ou derivado com pacman), com sudo.
- Placa de vídeo com Wayland funcionando (o Birfree é só Wayland; apps X11
  abrem pelo XWayland).
- SDDM como tela de entrada (o instalador põe o tema do Birfree nela).

## Birfree e KDE Plasma lado a lado

Pode ter os dois. O `./instalar-birfree` sem opção instala o Birfree por cima
do que já existe e não tira o Plasma: na tela de entrada, escolha **Birfree**
ou **Plasma** na lista de sessões.

- O Birfree usa peças do KDE (KWin, Configurações do Sistema, Dolphin...);
  elas continuam servindo ao Plasma.
- A aparência do Birfree (decoração, ícones, cursor, tema GTK, cores) vale só
  na sessão Birfree. Ao entrar no Plasma, ele volta com a aparência que tinha;
  o que você mudar dentro do Plasma fica.
- Ficam valendo nos dois: o tema da tela de entrada (SDDM), o modo escuro dos
  navegadores (Firefox com Dark Reader, Chrome/Chromium/Brave escuros) e a
  trava do KDE/Qt no `pacman -Syu` (o Plasma fica na mesma versão do KDE que
  o Birfree usa).
- `./instalar-birfree --migrar` é outra coisa: deixa a máquina **só** com o
  Birfree e tira o Plasma (`--desfazer` traz de volta).

## Monitor do sistema

Vem na barra, ao lado da bandeja: CPU, temperatura, memória e bateria.
Clique direito nele para escolher o que mostrar (também swap, GPU,
temperatura da GPU, rede, disco e espaço) e para mover para a **dock** ou para
a **área de trabalho**. Clique para abrir o Monitor do Sistema. Pelo terminal:

```sh
birfree-sysmon dock              # muda de lugar: barra | dock | mesa | tirar
birfree-sysmon mostrar cpu,ram   # o que aparece
```

O mesmo widget funciona no Plasma: **Adicionar widgets › Monitor do sistema
(Birfree)**, na área de trabalho ou num painel.

## Remover

Entre no Plasma e rode, na pasta do arquivo baixado:

```sh
./instalar-birfree --remover
```

Tira os pacotes do Birfree, devolve a aparência do Plasma, desfaz a trava do
KDE/Qt no `pacman -Syu` e a tela de entrada anterior. Suas configurações em
`~/.config/birfree*` ficam (apague à mão se quiser).
