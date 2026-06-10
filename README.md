# Emberwood 🔥

Playing around with Anthropic's new Fable 5 to build **"Emberwood"**, a Zelda-like top-down adventure in a single HTML file. HTML5 canvas, hand-authored pixel art, synthesized WebAudio, stealth AI with vision cones and A\* pathfinding. No engine, no assets, no dependencies.

<img width="890" height="665" alt="Screenshot 2026-06-10 at 9 39 42 AM" src="https://github.com/user-attachments/assets/06a3e8c9-91fc-4db3-96b3-7ce5e02aa878" />

<img width="889" height="662" alt="Screenshot 2026-06-10 at 9 41 31 AM" src="https://github.com/user-attachments/assets/9f85a371-eb11-426f-bec3-e68c8c771287" />

<img width="888" height="668" alt="Screenshot 2026-06-10 at 9 40 43 AM" src="https://github.com/user-attachments/assets/d7444b9b-9ddb-41d9-9919-71538c711fdb" />

<img width="887" height="660" alt="Screenshot 2026-06-10 at 9 45 47 AM" src="https://github.com/user-attachments/assets/358e26b0-dab2-4f50-9e0c-e40ee48f42f4" />

<img width="810" height="606" alt="Screenshot 2026-06-10 at 9 51 15 AM" src="https://github.com/user-attachments/assets/eaf33b53-fb4d-40db-ab6b-9aaa55edf457" />

<img width="810" height="605" alt="Screenshot 2026-06-10 at 9 51 41 AM" src="https://github.com/user-attachments/assets/fde4f291-9bdc-40a4-b39b-d5facec2d8b4" />

## Play

**[▶ Play it in your browser](https://karamvirr.github.io/fable5-canvas-game/)**

Or open `index.html` locally. That's it: the entire game (engine, art, audio, AI) lives in that one file.

## Controls

| Key | Action |
| --- | ------ |
| ↑ ↓ ← → | Move |
| Space / Z | Sword |
| X | Bow |
| V | AI debug overlay (vision cones + planned paths) |
| M | Mute |
| Enter | Restart (after game over / victory) |

## The game

You are the **Ember Warden**. Three **Ember Shards** lie hidden in the glade: one amid the snortling patrols of the north woods, one deep in the thornspitter nest of the south thicket, one on the lake's far shore. Collect all three to unseal the shrine on the north path and step through to win.

Finish without ever being seen and you'll earn the hidden accolade: **Shadow of the Glade**.

### Things to know

- **Snortlings** patrol with directional vision cones. Sneak behind them, or behind cover; trees, rocks, and bushes block their sight. When one spots you: **"!"** Then it hunts, pathfinding around water and walls (it *will* use the bridge). Lose it and it investigates your last-seen position before giving up with a **"?"**.
- **Some bushes blink back.** Thornspitters disguise themselves as cover and spit thorn volleys. Deflect a thorn with your sword swing and it flies back. A reflected thorn kills anything it touches, even a ducked spitter.
- **Arrows are scavenged**, not infinite. Cut bushes and fell foes to refill the quiver. An arrow into an *unaware* enemy is a one-shot kill.
- Press **V** to see the AI thinking: occlusion-aware vision cones, A\* routes, last-seen markers.

## How it was built

Every system was written in conversation with [Claude](https://claude.com/claude-code) (Fable 5), iterating feature by feature:

1. Tile map, camera, player movement and sword
2. Arc-swing sword animation with slash trail
3. Stealth enemies: vision cones, line-of-sight raycasts, Pokémon-style "!" alerts
4. Thornspitters: bush-mimic ranged enemies with deflectable projectiles
5. Combat feel: hit-stop, screen shake, squash & stretch, telegraphed lunges
6. AI debug overlay: vision cones and simulated/planned paths
7. Synthesized audio: every sound generated live with WebAudio, plus ambient wind and birdsong
8. Bow & scavenged-ammo economy
9. A\* pathfinding: hunters route around the river; stymied enemies pace the bank and give up honestly
10. The Ember Shard quest, sealed shrine, and victory stats

All pixel art is authored as text grids and baked to canvases at load. All audio is oscillators and filtered noise. There isn't a single binary asset in the repo.

🤖 Built with [Claude Code](https://claude.com/claude-code)
