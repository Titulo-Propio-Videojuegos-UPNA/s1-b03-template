# B03 - C++ Nativo en Unreal Engine 5: Componentes, Memoria GC, Data Assets y Delegates

Consolidación de arquitectura C++ modular en Unreal Engine 5 construyendo el Juego 3 de S1 («Arena Arcade 3D» de combate táctico y torretas estilo Toon Tanks y Stanford CS193U): anatomía de módulos (.Build.cs, Unreal Header Tool), macros de reflexión (UCLASS, UPROPERTY, UFUNCTION), protocolo Escudo Anti-Crash frente al Garbage Collector (TObjectPtr, TWeakObjectPtr y guard clauses con ensure() para que un puntero nulo nunca cierre el editor), componentes reutilizables en C++ (UHealthComponent, UWeaponComponent), configuración con UPrimaryDataAsset, UGameInstanceSubsystem de oleadas y comunicación por eventos C++ ↔ UMG con DECLARE_DYNAMIC_MULTICAST_DELEGATE.

---

## Cápsulas de Sesión y Etiquetas de Paracaídas (`s1-b03-template`)

- **Proyecto / Toybox:** Juego 3 (Pieza 2): «Arena Arcade / Toon Tanks 3D» — Juego de combate táctico 3D por oleadas en UE5 C++ modular (tanques/mechas, torretas, proyectiles, escudos y HUD reactivo por Delegates).
- **Capas 70 / 20 / 10:** • 70 % Base (completado en las 14 h de aula): Arena Arcade 3D funcionando con UHealthComponent en C++, TObjectPtr/TWeakObjectPtr con ensure() anti-crash, Data Asset de arma y HUD por Delegates (0 Tick en UI). · • 20 % Reto autónomo: Segundo arquetipo de enemigo/torreta configurado por UPrimaryDataAsset y UGameInstanceSubsystem de racha/puntuación. · • 10 % Extra Portfolio: Efectos de impacto dinámicos desde C++, oleadas progresivas y vídeo de 60 s de la Pieza 2 en GitHub.
- **Plataforma docente (vídeo indexado y entregas):** [https://ikasyn.com/titulo-videojuegos](https://ikasyn.com/titulo-videojuegos)

| Sesión | Subbloque | Horas | Título | Tag Inicio (`sync_checkpoint`) | Tag Fin |
|:---:|:---:|:---:|---|---|---|
| `S1-21` | `B03.1` | 2 h | Juego 3 / Pieza 2 (Arena Arcade 3D / Toon Tanks) · Módulos (.Build.cs, UHT) y Escudo Anti-Crash | `scripts\sync_checkpoint.bat s1-21-start` | `s1-21-end` |
| `S1-22` | `B03.1` | 2 h | Juego 3 · Memoria frente al Garbage Collector: TObjectPtr, TWeakObjectPtr y proyectiles C++ | `scripts\sync_checkpoint.bat s1-22-start` | `s1-22-end` |
| `S1-23` | `B03.2` | 2 h | Juego 3 · UHealthComponent en C++, UPrimaryDataAsset de armas y torretas IA [Cierre materia nueva S1] | `scripts\sync_checkpoint.bat s1-23-start` | `s1-23-end` |
| `S1-24` | `B03.2` | 2 h | Clínica en aula I (0 h casa): TArray, barridos espaciales y UGameInstanceSubsystem de oleadas | `scripts\sync_checkpoint.bat s1-24-start` | `s1-24-end` |
| `S1-25` | `B03.2` | 2 h | Clínica en aula II (0 h casa): Delegates Multicast C++ ↔ UMG (cero Tick en UI) | `scripts\sync_checkpoint.bat s1-25-start` | `s1-25-end` |
| `S1-26` | `B03.3` | 2 h | Clínica de cierre y pre-defensa anticipada de la Pieza 2 en el aula (0 h casa) | `scripts\sync_checkpoint.bat s1-26-start` | `s1-26-end` |
| `S1-27` | `B03.3` | 2 h | Defensa individual en puesto de la Pieza 2 (5 min) y entrega de guía opcional de consolidación | `scripts\sync_checkpoint.bat s1-27-end` | `s1-27-end` |
