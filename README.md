
# Guía de Instalación de Hipervisores: VirtualBox y VMware Workstation Player

---

## 1. Instalación en Windows

### 1.1 VirtualBox en Windows
1. Descargar el instalador desde la página oficial:  
   👉 [Descargar VirtualBox](https://www.virtualbox.org/wiki/Downloads)  
	click en:
	```bash
	VirtualBox 7.2.0 platform packages
	Windows hosts
	```
2. Ejecutar el archivo `.exe`.  
3. Seleccionar componentes (normalmente dejar los predeterminados).  
4. Aceptar la instalación de controladores de red.  
5. Finalizar la instalación.  

#### Verificación
Buscar en el menú inicio **Oracle VM VirtualBox** y abrirlo.  

---

### 1.2 VMware Workstation Player en Windows
1. Descargar desde la página oficial:  
   👉 [Descargar VMware Workstation Player](https://www.vmware.com/go/downloadplayer)  pide registro  👉 [Ver video tutorial en youtube](https://www.youtube.com/watch?v=UbhQsY1WzRk&t=86s)
2. Descargar de google drive:  
   👉 [Descargar VMware Workstation 17 desde Drive](https://drive.google.com/file/d/1jI-PjG5gnu4UvIeLSp7zAXCazbgokkMn/view?usp=sharing)  
3. Ejecutar el instalador `.exe`.  
4. Seguir el asistente de instalación (Next → Next → Install).  
5. Reiniciar el sistema si es necesario.  

#### Verificación
Buscar en el menú inicio **VMware Workstation Player** y abrirlo.  

---

## 2. Instalación en Linux (Debian/Ubuntu)

### 2.1 VirtualBox en Linux

#### Método 1: Repositorios oficiales
```bash
sudo apt update
sudo apt install virtualbox -y
```
Para soporte adicional (USB, RDP, PXE, etc.):
```bash
sudo apt install virtualbox-ext-pack -y
```
#### Método 2: Repositorio de Oracle (última versión)
```bash
echo "deb [arch=amd64] https://download.virtualbox.org/virtualbox/debian $(lsb_release -cs) contrib" | sudo tee -a /etc/apt/sources.list.d/virtualbox.list
wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
sudo apt update
sudo apt install virtualbox-7.0 -y
```
### Verificación
Ejecutar en terminal o buscar en menú:
```bash
virtualbox
```
### 2.2 VMware Workstation Player en Linux
1.  Descargar el instalador `.bundle` desde VMware:  
    👉 [Descargar VMware Player Linux](https://support.broadcom.com/)
2.   Dar permisos de ejecución e instalar:
```bash
chmod +x VMware-Player-*.bundle
sudo ./VMware-Player-*.bundle
```
3. Seguir el asistente gráfico.
### Dependencias necesarias en Debian/Ubuntu
```bash
sudo apt update
sudo apt install build-essential gcc make perl -y
```
### Verificación
```bash
vmplayer
```
# 3. Comparación rápida
| **Característica**       | **VirtualBox**                                   | **VMware Workstation Player**             |
|---------------------------|-------------------------------------------------|-------------------------------------------|
| **Licencia**             | GPL v2 (gratuito) + extensiones propietarias     | Gratuito para uso personal (no comercial) |
| **Rendimiento**          | Bueno                                            | Excelente (mejor manejo de drivers)       |
| **Compatibilidad**       | Multiplataforma (Windows, Linux, macOS, Solaris) | Windows y Linux                           |
| **Facilidad de uso**     | Intuitivo                                        | Muy intuitivo                             |
| **Integración Guest OS** | Media (Guest Additions)                          | Alta (VMware Tools)                       |
