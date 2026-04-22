# Auditoria CFTV Pro

Script PowerShell 5.1+ para auditoria de rede CFTV em Windows 10/11.

## O que ele faz

- Descobre automaticamente gateway, IP local, máscara, CIDR e rede principal.
- Verifica se o Nmap está instalado.
- Instala o Nmap via winget, se necessário.
- Executa varredura controlada em portas típicas de CFTV.
- Classifica dispositivos como DVR/NVR, Câmera IP ou Outro.
- Exporta CSV UTF-8 no Desktop por padrão.

## Requisitos

- Windows 10/11.
- PowerShell 5.1 ou superior.
- Executar como Administrador.
- Winget disponível, caso o Nmap precise ser instalado automaticamente.

## Execução rápida

Executar diretamente do GitHub:

```powershell
irm https://raw.githubusercontent.com/USUARIO/REPOSITORIO/main/Auditoria_CFTV_Pro.ps1 | iex
```

Executar com parâmetros:

```powershell
irm https://raw.githubusercontent.com/USUARIO/REPOSITORIO/main/Auditoria_CFTV_Pro.ps1 | iex
```

Executar localmente:

```powershell
.\Auditoria_CFTV_Pro.ps1 -TargetCidr 192.168.1.0/24 -Ports "80,443,554,8000,8080,37777"
```

## Parâmetros

- `-TargetCidr`: sub-rede alvo em CIDR. Se omitido, usa a rede principal detectada automaticamente.
- `-Ports`: portas a varrer.
- `-OutputPath`: pasta de saída do CSV.
- `-LogLevel`: `INFO` ou `DEBUG`.
- `-SkipInstall`: não tenta instalar o Nmap via winget.

## Exemplo de uso

```powershell
powershell.exe -NoProfile -ExecutionPolicy Bypass -Command "irm https://raw.githubusercontent.com/USUARIO/REPOSITORIO/main/Auditoria_CFTV_Pro.ps1 | iex"
```

## Segurança

Use somente em redes sob sua responsabilidade. O script executa varredura controlada e requer privilégios administrativos para operações mais precisas.
