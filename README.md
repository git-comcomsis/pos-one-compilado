# POS One Pro — compilados

Aquí se publican las versiones compiladas de POS One Pro, listas para instalar. Este repositorio
no tiene código fuente ni llaves: solo los archivos que instala cada caja y el manifiesto que le
dice a la app cuál es la versión vigente.

**No se escribe a mano.** Todo lo publica el flujo de versiones del repositorio de código, a
partir del tag de cada corte.

## Marcas

Hay una compilación por marca del WMS y por sistema. La lista está en [marcas.json](marcas.json).

| Marca | Servidor | Estado |
|---|---|---|
| Weech | `app.weech.com.mx` | Primera en publicarse |
| LSDTA | `app.lasombradetusalas.com` | Pendiente |
| Makolet | `app.makolet.mx` | Pendiente |
| Comsis HUB | `hub.comsis.space` | Pendiente |

## Qué hay

| Qué | Dónde |
|---|---|
| Archivos compilados | [Versiones (Releases)](../../releases), una por tag `vX.Y.Z` |
| Manifiesto de cada marca y canal | `manifiestos/<marca>/<canal>.jws` |
| Catálogo de marcas | `marcas.json` |

Nombre de cada archivo: `postone-<marca>-<sistema>-vX.Y.Z-b<compilación>.<ext>`

| Sistema | Archivo |
|---|---|
| `windows-x64` | Instalador `.exe` |
| `android` | `.apk` para teléfono y tableta |
| `ubuntu-x64` | `.tar.gz` |
| `macos` | `.dmg` |

## Cómo se actualiza una caja

La app, con su cuenta en la nube activa, lee el manifiesto de su marca, comprueba su firma, baja
el archivo de su sistema y comprueba su huella sha256 antes de instalar. Un archivo que no
coincide con el manifiesto firmado no se instala.

## Instalar a mano

Baja de [Versiones](../../releases) el archivo de tu marca y tu sistema. Para comprobarlo, compara
su huella con la que aparece en las notas de la versión:

```
Windows (PowerShell):  Get-FileHash .\postone-weech-windows-x64-v0.1.0-b40.exe -Algorithm SHA256
Mac y Linux:           shasum -a 256 postone-weech-android-v0.1.0-b40.apk
```
