# Verano 2027 — Consolidación C++ en Unreal Engine 5 (Puente Opcional entre S1 y S2)

> **Fecha de verificación y consolidación:** `2026-10-25`

Pack **autónomo y 100 % opcional**, **0 ECTS**, **~10–15 horas** (`12 h` estimadas). No consume horas de las 200 h lectivas del título de Especialista. Quien no lo realice **entra en igualdad de condiciones a S2**; su objetivo es mantener fresco lo construido en el primer semestre y llegar con soltura al arranque del Semestre 2 en septiembre de 2027.

A diferencia de `M0` (que era C++ estándar de base antes de febrero), aquí trabajas directamente **sobre tu Pieza 2 de final de S1 (`B02` + `B03`)**: los dos juegos 3D que construiste en **Unreal Engine 5 con lógica 100 % en C++ (`AActor`, `UActorComponent`, `UGameInstanceSubsystem`, `UDataAsset`, `UPROPERTY`, `UFUNCTION`) y Prefabs de Datos (*Data-Only Blueprints*, sin lógica en grafos de nodos)**.

---

## Tres ideas clave para el verano

1. **Punto de partida real (`B01` + `B02` + `B03` de S1):** ya has cerrado el primer semestre con tres juegos 3D jugables verificados en tu portfolio: tu Arcade Espacial 3D en C++20 a paso fijo (`B01`, **Pieza 1 — Juego 1**) y tus dos juegos 3D en Unreal Engine 5 C++ (`B02` Obstáculos 3D + `B03` Arena Arcade 3D, **Pieza 2 — Juegos 2 y 3**). Este pack sirve para pulir el proyecto de UE5 antes de abordar `S2`.
2. **Preparación directa para los tres bloques de `S2` (`Plan Definitivo · 2026-10-25`):**
   - **`B04` (`21 h`, C++ Avanzado en Tiempo Real: Plugins, Concurrencia Segura y Gemelos Digitales HTTP/JSON + Python):** construiremos `TelemetrySimPlugin` conectando UE5 en tiempo real con un emisor de datos en Python.
   - **`B05` (`15 h`, Arquitectura Multijugador Autoritativa y Replicación):** sincronizaremos estado y movimiento en red bajo latencia simulada.
   - **`B06` (`20 h`, Pipeline GPU, Materiales/Shaders HLSL y Clínica de Optimización Empírica):** diagnosticaremos y optimizaremos cuellos de botella de CPU y GPU con *Unreal Insights* y *RenderDoc*.
3. **Portfolio personal verificable:** el verano (julio–agosto, una vez terminados los exámenes de mayo/junio del Grado) es el momento ideal para publicar y documentar tus piezas de S1 en tu cuenta personal de GitHub con un `README.md` técnico y un vídeo corto de 60 s.

---

## Cinco mejoras opcionales sobre tu Pieza 2 (`B02` + `B03`) (~10–12 h)

Aplícalas sobre tu proyecto de `B03` haciendo un *commit* limpio por mejora:

| # | Horas | Mejora técnica y cómo conecta con S2 (`B04–B06`) |
|---|---|---|
| 1 | 2–3 | **Auditoría *Zero Event-Graph Logic* (`B03` → `B04`):** verifica que todos los Blueprints de tu proyecto sean estrictamente *Data-Only Prefabs* (mallas, materiales, sonidos, `UDataAsset`) y que toda reacción visual del HUD provenga de delegados C++ (`DECLARE_DYNAMIC_MULTICAST_DELEGATE`). |
| 2 | 2 | **Parametrización con `UDataAsset` y `UPROPERTY` (`B03` → `B04`):** asegura que las velocidades, tiempos de recarga o umbrales de tu mecánica estén en un `UDataAsset` o expuestos con `EditDefaultsOnly` / `BlueprintReadOnly`, sin números mágicos (*hardcoded*) en el `.cpp`. |
| 3 | 2–3 | **Auditoría del `Tick` y de tiempos de fotograma (`B03` → `B06`):** identifica qué actores o componentes tienen `PrimaryActorTick.bCanEverTick = true` sin necesitarlo cada *frame* (sustitúyelo por eventos o `FTimerHandle`) y mide el tiempo de fotograma con `stat unit` y `stat game` como preparación directa para `B06`. |
| 4 | 2 | **Contenedores y punteros seguros de Unreal (`B03` → `B04`):** gestiona la colección de elementos o *pool* de proyectiles de tu prototipo con `TArray` o `TMap` y punteros supervisados (`TObjectPtr<UObject>` / `TWeakObjectPtr`), sin ningún `new`/`delete` crudo sobre objetos del motor. |
| 5 | 2–3 | **Publicación en tu GitHub personal:** publica el repositorio respetando el `.gitignore` de Unreal (sin subir `Binaries/`, `Intermediate/`, `Saved/` ni `DerivedDataCache/`), añade un `README.md` de una página explicando la arquitectura C++ y enlaza un vídeo de 60 s. |

No hay entrega calificable en verano: en la primera sesión de `B04` (septiembre de 2027) partiremos de la plantilla limpia del semestre.
