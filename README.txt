# 🔐 Restricción de Dispositivos USB en Windows usando VirtualBox

Este proyecto muestra cómo configurar una máquina virtual en VirtualBox y aplicar restricciones de acceso a dispositivos USB mediante políticas de grupo en Windows.

---

## 🧩 1. Instalación de VirtualBox Extension Pack

1. Ve al sitio oficial de VirtualBox y descarga el **Extension Pack** compatible con tu versión.
2. Abre VirtualBox.
3. Dirígete a:
   **Archivo > Herramientas > Extensiones**
4. Añade el archivo descargado e instálalo.

---

## 🔌 2. Habilitar soporte USB en la máquina virtual

1. Apaga la máquina virtual si está en ejecución.
2. Selecciona la VM en VirtualBox.
3. Ve a:
   **Configuración > Puertos > USB**
4. Activa:

   * Controlador USB 2.0 (EHCI) o
   * Controlador USB 3.0 (xHCI)

---

## 🔗 3. Conectar un dispositivo USB a la VM

1. Inicia la máquina virtual.
2. Conecta el dispositivo USB a tu equipo físico.
3. En el menú de la VM:
   **Dispositivos > USB**
4. Selecciona el dispositivo para que la VM tome control.

---

## 🚀 4. Restricción de dispositivos USB en Windows

### 🛠 Abrir el Editor de Políticas de Grupo

1. Presiona `Win + R`
2. Escribe:

   ```
   gpedit.msc
   ```
3. Presiona Enter

---

### 📂 Navegar a las políticas

Ir a:

```
Configuración del equipo 
→ Plantillas administrativas 
→ Sistema 
→ Acceso de almacenamiento removible
```

---

### 🔒 Configurar restricciones

Activar las siguientes políticas:

* **Discos extraíbles: denegar acceso de lectura**
* **Discos extraíbles: denegar acceso de escritura**

---

### ⚡ Aplicar los cambios (IMPORTANTE)

Abrir PowerShell o CMD como administrador y ejecutar:

```
gpupdate /force
```

Esto fuerza la actualización inmediata de las políticas de grupo.

---

## ✅ Resultado

Después de aplicar estas configuraciones:

* Los dispositivos USB conectados no podrán leer ni escribir datos.
* Se mejora la seguridad del sistema frente a uso de dispositivos externos.

---

## 📁 Estructura del repositorio

```
command/
imagenes/
informe/
```

---

## 📌 Notas

* Asegúrate de usar versiones compatibles entre VirtualBox y el Extension Pack.
* Algunas opciones pueden variar dependiendo de la versión de Windows.

---
