Repo-escalera-mecánica

Integrantes:Olivares Garcia Maria del Carmen, Alvarez Ochoa Rodrigo Emiliano,
Ortiz Garcia Diego, Alvarez Saavedra Alexis Ivan

DIAGRAMA DE FLUJO: FUNCIONAMIENTO DE ESCALERAS MECÁNICAS

Inicio
 Verificación de seguridad del sistema
 Encendido del motor
 Activación de sensores de presencia
¿Hay personas en la escalera?
   (Sí) → Inicia el movimiento de la banda
    → Ciclo de transporte (subida o bajada)
    → Monitoreo constante de operación (velocidad, carga, obstáculos)
    → ¿Se detecta algún error?
      → (Sí) → Detención de emergencia
        → Notificación al sistema de control
      → (No) → Continua el ciclo
    → ¿Ya no hay personas en la escalera?
      → (Sí) → Detención automática tras unos segundos
      → (No) → Continua operando
→ (No) → Espera en reposo con sensores activos
Fin

SISTEMA MECÁNICO

Componentes:

Escalones móviles

Cadena de tracción

Rieles guía

Rodillos y ejes

Plataforma de entrada y salida
Función:

Transportar personas entre dos niveles de forma continua.

Guía y soporte del movimiento de los escalones.


SISTEMA ELÉCTRICO

Componentes:

Motor eléctrico (AC)

Fuente de alimentación

Sistema de iluminación (opcional)

Cableado y conectores
Función:

Suministrar energía al motor.

Permitir el encendido/apagado del sistema.


SISTEMA DE CONTROL

Componentes:

Sensores de presencia

Interruptores de encendido/apagado

Temporizador de parada automática
Función:

Detectar usuarios para activar el movimiento.

Detener la escalera cuando no hay usuarios.

Asegurar eficiencia energética.


SISTEMA DE SEGURIDAD

Componentes:

Botón de paro de emergencia

Sensores antiobstrucción

Alarmas sonoras/visuales

Freno mecánico
Función:

Detener la escalera ante fallos o bloqueos.

Alertar a usuarios sobre emergencias.

Evitar accidentes por objetos o caídas.


PSEUDOCÓDIGO

INICIO

Definir estado ← "apagado"
Definir usuario_presente ← FALSO
Definir error ← FALSO

MIENTRAS sistema_encendido HACER

    Revisar_sensor_usuario()
    Revisar_sistema_seguridad()

    SI error = VERDADERO ENTONCES
        Detener_escalera()
        Mostrar("ERROR: Escalera detenida")
    SINO SI usuario_presente = VERDADERO ENTONCES
        Activar_escalera()
    SINO
        Detener_escalera()
    FIN SI

    Esperar(1 segundo)

FIN MIENTRAS

FIN

PROCEDIMIENTO Revisar_sensor_usuario()
    SI sensor detecta persona en escalón inicial
        usuario_presente ← VERDADERO
    SINO
        usuario_presente ← FALSO
    FIN SI
FIN PROCEDIMIENTO

PROCEDIMIENTO Revisar_sistema_seguridad()
    SI sensor detecta obstrucción o malfunción
        error ← VERDADERO
    SINO
        error ← FALSO
    FIN SI
FIN PROCEDIMIENTO

PROCEDIMIENTO Activar_escalera()
    estado ← "encendido"
    Mostrar("Escalera en movimiento")
FIN PROCEDIMIENTO

PROCEDIMIENTO Detener_escalera()
    estado ← "apagado"
    Mostrar("Escalera detenida")
FIN PROCEDIMIENTO
