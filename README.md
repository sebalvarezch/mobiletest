# mobiletest

SAST Snyk Windows
$json = snyk code test --json
[System.IO.File]::WriteAllText("$PWD\results.json", $json, [System.Text.UTF8Encoding]::new($false))

snyk-to-html -i .\results.json -o .\report.html

SAST MobSF Kali Linux
┌──(sevastos㉿STVALSEG02)-[~]
└─$ sudo docker run -it -p 8001:8000 \
  -v ~/mobsf_data:/home/mobsf/.MobSF \
  opensecurity/mobile-security-framework-mobsf:latest
[INFO] 29/May/2026 18:55:25 - Loading User config from: /home/mobsf/.MobSF/config.py
[INFO] 29/May/2026 18:55:28 -
  __  __       _    ____  _____       _  _    ____
 |  \/  | ___ | |__/ ___||  ___|_   _| || |  | ___|
 | |\/| |/ _ \| '_ \___ \| |_  \ \ / / || |_ |___ \
 | |  | | (_) | |_) |__) |  _|  \ V /|__   _| ___) |
 |_|  |_|\___/|_.__/____/|_|     \_/    |_|(_)____/

[INFO] 29/May/2026 18:55:28 - Author: Ajin Abraham | opensecurity.in
[INFO] 29/May/2026 18:55:28 - Mobile Security Framework v4.5.0
REST API Key: a767b6ea14f6b2040b9671c547639777c0b0a3a0ddf15cc37272912ade5069c5
Default Credentials: mobsf/mobsf
[INFO] 29/May/2026 18:55:28 - OS Environment: Linux (debian 12 bookworm) Linux-6.6.87.2-microsoft-standard-WSL2-x86_64-with-glibc2.36
[INFO] 29/May/2026 18:55:28 - Python Version: 3.13.12
[INFO] 29/May/2026 18:55:28 - CPU Cores: 6, Threads: 12, RAM: 7.60 GB
[INFO] 29/May/2026 18:55:28 - MobSF Basic Environment Check
No changes detected

Para extraer APK
adb shell pm list packages
adb shell pm path com.app.nombreapp
adb pull /data/app/fsdfsdaf/base.apk ./nombreapp.apk

Para usar jadx

jadx-gui /home/sevastos/ruta/aplicacion.apk

Para listar AVDs desde CMD
C:\Users\<TU_USUARIO>\AppData\Local\Android\Sdk\emulator\emulator.exe -list-avds

Ejecutar AVD luego de seleccionar uno e interceptar con BurpSuite capturando en puerto 8080
C:\Users\<TU_USUARIO>\AppData\Local\Android\Sdk\emulator\emulator.exe -avd Pixel_6_API_34 -http-proxy http://127.0.0.1:8080 -writable-system

Drozer: Instalar agente APK en el AVD
Hacer que el puerto tcp 31415 del AVD tenga comunicación directa con el puerto 31415 del computador
adb forward tcp:31415 tcp:31415

