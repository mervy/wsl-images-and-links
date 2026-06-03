# Links para imagens WSL e comandos atualizados

Catálogo de links diretos para imagens WSL em `.wsl`, com downloads atualizados de várias distribuições Linux.

Este repositório reúne URLs para instalar Debian, Fedora, Arch, openSUSE, NixOS e outras distros no WSL sem precisar passar pela Microsoft Store.

Também inclui os comandos para instalar com nome e localização personalizados, permitindo usar distros do catálogo sem ficar preso ao AppData padrão do WSL.

## Como usar

1. Baixe o arquivo `.wsl` desejado.
2. Instale com:

```powershell
wsl --install --from-file <arquivo>.wsl
```

3. Se preferir importar manualmente para um local específico:

```powershell
wsl --import <Nome> <Diretório> <arquivo>.wsl
```

## Links de imagens

### Debian (v1.26.0.0)
- amd64: `https://salsa.debian.org/debian/WSL/-/jobs/9606244/artifacts/raw/Debian_WSL_AMD64_v1.26.0.0.wsl`
- arm64: `https://salsa.debian.org/debian/WSL/-/jobs/9606244/artifacts/raw/Debian_WSL_ARM64_v1.26.0.0.wsl`

### openSUSE Tumbleweed
- amd64: `https://github.com/openSUSE/WSL-instarball/releases/download/v20260423.0/openSUSE-Tumbleweed-20260422.x86_64-2.97-Build2.97.wsl`
- arm64: `https://github.com/openSUSE/WSL-instarball/releases/download/v20260423.0/openSUSE-Tumbleweed-20260422.aarch64-3.82-Build3.82.wsl`

### openSUSE Leap 16.0
- amd64: `https://github.com/openSUSE/WSL-instarball/releases/download/v20251001.0/openSUSE-Leap-16.0-16.0.x86_64-22.57-Build22.57.wsl`
- arm64: `https://github.com/openSUSE/WSL-instarball/releases/download/v20251001.0/openSUSE-Leap-16.0-16.0.aarch64-22.57-Build22.57.wsl`

### Fedora 44
- amd64: `https://download.fedoraproject.org/pub/fedora/linux/releases/44/Container/x86_64/images/Fedora-WSL-Base-44-1.7.x86_64.wsl`
- arm64: `https://download.fedoraproject.org/pub/fedora/linux/releases/44/Container/aarch64/images/Fedora-WSL-Base-44-1.7.aarch64.wsl`

### Fedora 43
- amd64: `https://download.fedoraproject.org/pub/fedora/linux/releases/43/Container/x86_64/images/Fedora-WSL-Base-43-1.6.x86_64.wsl`
- arm64: `https://download.fedoraproject.org/pub/fedora/linux/releases/43/Container/aarch64/images/Fedora-WSL-Base-43-1.6.aarch64.wsl`

### AlmaLinux 10
- amd64: `https://github.com/AlmaLinux/wsl-images/releases/download/v10.2.20260526.0/AlmaLinux-10.2_x64_20260526.0.wsl`
- arm64: `https://github.com/AlmaLinux/wsl-images/releases/download/v10.2.20260526.0/AlmaLinux-10.2_ARM64_20260526.0.wsl`

### AlmaLinux 9
- amd64: `https://github.com/AlmaLinux/wsl-images/releases/download/v9.8.20260526.0/AlmaLinux-9.8_x64_20260526.0.wsl`
- arm64: `https://github.com/AlmaLinux/wsl-images/releases/download/v9.8.20260526.0/AlmaLinux-9.8_ARM64_20260526.0.wsl`

### Arch Linux
- amd64: `https://fastly.mirror.pkgbuild.com/wsl/2026.06.01.169366/archlinux-2026.06.01.169366.wsl`

### NixOS
- amd64: `https://github.com/nix-community/NixOS-WSL/releases/latest/download/nixos.wsl`
- arm64: `https://github.com/nix-community/NixOS-WSL/releases/latest/download/nixos.wsl`

### Gentoo (não oficial)
- amd64: `https://github.com/HUSTLUG/Gentoo-wsl/releases/latest/download/gentoo.wsl`

## Detalhes de instalação avançada

**Direto do catálogo ("store"), já escolhendo local e nome:**

```powershell
wsl --install archlinux --name arch1 --location X:\Linux\arch1
```

Um detalhe sobre o "direto da store": quando você passa `--name` ou `--location`, o WSL **não usa o pacote MSIX da Microsoft Store** (esse fica preso numa pasta fixa do AppData e não dá pra renomear/realocar). Ele baixa o tarball do catálogo e registra ali onde você mandou. O resultado final é idêntico — só muda o mecanismo por baixo.

Para instalações limpas ou múltiplas instâncias:

```powershell
wsl --import arch1 Z:\ze-wsl\arch1 .\wsl-images\arch.wsl
wsl --import arch2 Z:\ze-wsl\arch2 .\wsl-images\arch.wsl
```

Para listar, usar ou remover instâncias:

```powershell
wsl -l -v
wsl -d arch1
wsl --unregister arch1
```

## Observações

- O Gentoo não está no catálogo oficial da Microsoft; o link acima é uma imagem `.wsl` mantida pela comunidade HUSTLUG.
- Para Gentoo, outra alternativa é importar um stage3 do Gentoo com `wsl --import <Distro> <Local> <Arquivo>`.
- `arch` e `gentoo` estão disponíveis apenas em `amd64` neste catálogo.
