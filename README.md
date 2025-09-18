🎮 "Guerrero vs Zombies" - Descripción Detallada
Tipo de Juego:
Es un juego de supervivencia en 2D tipo "top-down shooter" donde un guerrero debe sobrevivir oleadas infinitas de zombies que lo persiguen constantemente.

🏗️ Arquitectura del Código:
Clases Principales:
1. Clase Jugador (Guerrero):

Atributos: Posición (x,y), velocidad, vida (100 HP), dimensiones
Métodos:

mover(): Movimiento con WASD o flechas, con límites de pantalla
disparar(): Crea proyectiles hacia la posición del mouse
recibir_dano(): Reduce vida al ser atacado
dibujar_guerrero(): Sprite detallado (armadura marrón, casco, espada, botas)



2. Clase Zombie:

Atributos: Posición, velocidad variable, 30 HP, daño de 20, contador de animación
Métodos:

mover_hacia_jugador(): IA que persigue al jugador usando vectores direccionales
recibir_dano(): Sistema de salud con muerte
dibujar_zombie(): Sprite animado (ojos rojos, cuerpo verde, animación de caminar)



3. Clase Bala:

Atributos: Posición, dirección vectorial, velocidad 10, daño 25
Métodos:

mover(): Movimiento lineal en dirección del disparo
colisiona_con(): Detección de colisiones por distancia
dibujar_proyectil(): Efecto visual dorado con rastro de energía



4. Clase Juego (Motor principal):

Maneja todos los estados y la lógica del juego


🎯 Sistema de Estados:
MENU (0): Pantalla inicial con selección de dificultad
JUGANDO (1): Gameplay activo
GAME_OVER (2): Pantalla de muerte con estadísticas
PAUSADO (3): Juego pausado con overlay

⚙️ Mecánicas de Juego:
Sistema de Dificultad:

Fácil: 3 zombies/oleada, velocidad 1
Normal: 5 zombies/oleada, velocidad 1.5
Difícil: 7 zombies/oleada, velocidad 2

Sistema de Oleadas:

Cada oleada aumenta +1 zombie adicional
Los zombies aparecen desde los bordes de la pantalla
Nueva oleada al eliminar todos los zombies

Sistema de Combat:

Disparo: Clic izquierdo con cooldown de 200ms
Daño: Balas hacen 25 HP, zombies 20 HP
Colisiones: Detección por distancia euclidiana

Sistema de Puntuación:

+10 puntos por zombie eliminado
Contador de oleadas sobrevividas


🎨 Elementos Visuales:
Sprites Detallados:

Guerrero: Armadura, casco con corona, espada, barra de vida
Zombies: Cuerpo descompuesto, ojos rojos brillantes, animación de caminar
Balas: Proyectiles dorados con rastro de energía y brillo

Ambiente:

Fondo nocturno verde oscuro
Estrellas decorativas
HUD completo con información del juego


🎮 Controles:
Movimiento: WASD o flechas direccionales
Disparo: Clic izquierdo del mouse
Pausa: Tecla P
Menú: ESC
Selección dificultad: Teclas 1, 2, 3
Reiniciar: R (en game over)

🔄 Flujo de Juego:

Inicio: Menú de selección de dificultad
Spawn: Jugador en el centro, zombies en los bordes
Gameplay: Sobrevivir eliminando oleadas infinitas
Muerte: Cuando la vida llega a 0
Game Over: Mostrar estadísticas y opciones


🚀 Características Técnicas:

Framerate: 60 FPS constante
Resolución: 800x600 píxeles
Detección de colisiones: Algoritmo de distancia euclidiana
Animaciones: Sprites animados para zombies y efectos de balas
Sistema de tiempo: Cooldowns y temporizadores precisos


🎯 Objetivo del Juego:
Sobrevivir el mayor tiempo posible eliminando oleadas infinitas de zombies, acumulando puntos y progresando en dificultad. Es un juego de supervivencia sin final definido, donde el desafío aumenta constantemente.
El proyecto está bien estructurado con separación clara de responsabilidades, mecánicas balanceadas y una experiencia de usuario pulida con múltiples estados de juego y controles intuitivos.
