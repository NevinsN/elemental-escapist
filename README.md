# Elemental Escapist: Technical UE5 Prototype
## Project Overview

Elemental Escapist is a first-person technical prototype built in Unreal Engine 5 that focuses on escape-room style puzzle solving rather than traditional combat. The project serves as a "test bed" to validate the reliability of the NexusGate orchestration layer by generating granular player state data during environmental interactions.

### Technical Narrative: The Logic-Gate Pipeline
This prototype is designed to test how player progression flags are preserved during server handoffs.  

- The "Powerizer" System: Players collect elemental projectiles (Chair/Stone) required to solve environmental puzzles.
- State Generation: When a player unlocks a "Powerizer" or reaches a level milestone, a C++ event is triggered.
- Cloud Integration: These events serve as the data payload for NexusGate, ensuring that "Elemental States" (e.g., ammunition counts and puzzle progress) are persisted to a Redis cache for synchronization across server instances. 

### Gameplay & Interface
- Non-Violent Mechanics: Uses standard FPS controls (WASD, Sprint, Crouch) but focuses on "collision-based" puzzle interaction.
- Streamlined HUD: Tracks essential metrics including a game timer, ammunition counters for two types of projectiles, and contextual hints for the next objective.
- Escapist Flow: Players navigate through the Mountain Cliff and Hidden Office Lab levels, using critical thinking to solve puzzles and unlock new abilities.

### Design Objectives
- Atmospheric Immersion: A stylized, "whimsical" art direction intended to provide a calm yet challenging experience.
- Predictable Data Persistence: The game is architected to ensure that once a puzzle is solved, the state is locked and globally recognized by the backend infrastructure.

### Repository Structure
- /Source: C++ implementation of the "Powerizer" and logic-gate event triggers.
- /Content: UE5 assets, including the "Mountain Cliff" and "Hidden Office Lab" environments.
- /Docs: Original design documentation and user experience briefs.
