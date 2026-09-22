# SNOOPY OBB Remote Control

Site separado para enviar ao APK comandos de bloqueio remoto por aparelho.

## Comandos enviados

Os comandos são gravados no Realtime Database em `SNOOPY_REMOTE_COMMANDS/{accessKey}`.

```json
{
  "mode": "ALLOWLIST",
  "allowPackages": ["com.dts.freefireth", "com.dts.freefiremax"],
  "requestId": "uuid-unico",
  "updatedAt": 0
}
```

`ALLOWLIST` solicita bloqueio dos demais aplicativos e libera os pacotes oficiais do Free Fire. `OFF` solicita a desativação do modo remoto.

## Limitações do Android

O site não consegue criar ou controlar uma VPN diretamente. O APK precisa receber o comando, ter autorização da VPN do Android e executar a filtragem localmente. A primeira autorização sempre exige confirmação do usuário no aparelho. O APK deve validar o chave de acesso do aparelho e consumir cada `requestId` uma única vez.

## Publicação

A página pode ser publicada pelo GitHub Pages em:

`https://guif63265-afk.github.io/SNOOPYOBB-Remote-Control/`

Como o GitHub Pages ainda não está habilitado na conta, a versão online está disponível em:

`https://raw.githack.com/guif63265-afk/SNOOPYOBB-Remote-Control/main/index.html`

Antes de usar em produção, configure regras do Firebase para impedir que qualquer pessoa escreva comandos para qualquer aparelho. O ideal é usar autenticação e regras por usuário/aparelho, não deixar o nó de comandos aberto.
