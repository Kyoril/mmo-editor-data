# Gold Mine Greybox

`gold_mine_greybox.glb` is a first playable, low-poly mine shell. It uses metres and Y-up coordinates. Import it using **Model Import** in `mmo_edit`; GLB is one of the importer's supported formats. The generator authors in engine coordinates, converts to Blender's native Z-up space, and lets the GLB exporter produce the final Y-up asset.

Layout: exterior entrance, an entry tunnel, arrival hall, work chamber, extraction hall, and side chamber. Their centers and connecting passages are deliberately diagonal rather than grid aligned. Tunnels are 5.5–5.8 m wide and 4.9–5.2 m high; rooms are 11–18 m across. This allows players moving at 7 m/s to cross a room in roughly 2 seconds, while retaining a deliberately compact WoW-inspired dungeon rhythm.

The editable source is `gold_mine_greybox.blend`. Regenerate it with Blender 4.x:

```powershell
& 'C:\Program Files\Blender Foundation\Blender 4.3\blender.exe' --background --python tools\generate_gold_mine_greybox.py
```

The chambers use irregular 32-sided perimeters, bowed wall rings, smoothed vertex normals, domed ceilings, and arched tunnel sweeps. Every room floor and wall share one indexed boundary ring. Passage ends use closed, manifold stone transition collars matched to the tunnel profile and oversized into the chamber shell, preventing cracks even when the engine culls backfaces. Timber support frames provide the deliberately straight architectural contrast. The model intentionally omits loose props, rails, lights, collision, and navmesh until the scale and silhouette are approved.
