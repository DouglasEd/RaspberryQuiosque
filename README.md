
# Configuração do Raspberry em modo quiosque

## Pré-requisitos

### 1. Certifique-se de ter instalado o sistema Raspberry Pi OS:
  
### 2. E as seguintetes ferramentas
  
- xdotool
- unclutter
- sed
  
## Instalação

### 1. Configure o sistema do raspberry para autologin
#### 1.1 Execute a seguinte linha do CMD
```bash
sudo raspi-config
```
#### 1.2 Siga o seguinte caminho
Boot Options  >  Desktop/CLI  >  Desktop Autologin

### 2. Crie um serviço para abrir o Chromium em modo quiosque
#### 2.1 Execute a linha de comando no CDM para criar/editar o arquivo kiosk.sh
```bash 	sudo nano /usr/local/bin/kiosk.sh```  
  
obs.: Caso deseje armazenar o script em outro diretorio, deve ser feita a alteração no kiosk.service
- Copie o codigo no arquivo kiosk.sh
- Troque os {User} pelo usuario que voce definiu ao instalar o sistema
- Troque o {Link a ser aberto} pelo endereço que voce gostaria que o Chromium abra

### 3. Configure o serviço no sistema
#### 3.1 Execute a linha de comando no CDM para criar/editar o arquivo kiosk.service
```bash 	sudo nano /lib/systemd/system/kiosk.service```
- Copie o codigo no arquivo kiosk.service
- Troque os {User} pelo usuario que voce definiu ao instalar o sistema

### 4. Habilite o Serviço
```bash sudo systemctl enable kiosk.service```

### 5. Inicie o Serviço
```bash sudo systemctl start kiosk.service```
