# Factory BIM — Interactive 3D Building Information Model Viewer

A browser-based interactive 3D BIM viewer for an industrial factory complex, enabling stakeholders to explore, inspect, and export structural, architectural, and MEP building layers without specialist CAD software.

Built using [NebulaCloud Studio](https://nebulacloud.studio).

## What It Does

| Capability | Description |
|---|---|
| 3D Building Walkthrough | Freely orbit, pan, and zoom around a detailed industrial facility model with real-time rendering |
| BIM Layer Toggle | Show or hide 15 discipline layers including structural, architectural, MEP, equipment, and site elements |
| Click-to-Inspect | Select any building element to view its BIM classification, layer name, and world-space coordinates |
| Structural Wireframe Mode | Toggle wireframe rendering to inspect the underlying structural framework |
| GLB/GLTF Export | Export the complete model with all BIM layers and object names preserved for import into other tools |
| Building Information Dashboard | View live statistics including footprint dimensions, column count, and total triangle count |

## Why It Matters

Traditional BIM review requires licensed desktop software, restricting access to engineers with the right tools. This browser-based viewer removes that barrier — anyone with a web browser can explore the building model, toggle discipline layers, and inspect individual elements.

For project stakeholders, this means faster design reviews, easier coordination between disciplines, and more accessible client presentations. The export capability allows the model to flow into downstream tools while preserving BIM metadata.

For education and training, the interactive environment helps students and new professionals understand how structural, architectural, and MEP systems integrate within a real facility layout.

## Intended Users

| Audience | Relevant Application |
|---|---|
| Structural Engineers | Review column grids, beam layouts, foundation design, and roof truss systems |
| MEP Engineers | Inspect HVAC ductwork routing, electrical panel placement, and plumbing pipe runs |
| Architects | Evaluate spatial layout, interior wall configurations, window/door placements, and cladding |
| Project Managers | Coordinate discipline integration and present facility designs to non-technical stakeholders |
| Facility Planners | Assess equipment placement, conveyor systems, loading dock logistics, and warehouse racking |
| Educators & Students | Teach BIM concepts, building systems integration, and construction coordination |

## Technical Highlights

| Capability | Technology or Method |
|---|---|
| 3D Rendering | Three.js WebGL with PCFSoft shadow maps, ACES filmic tone mapping, and fog |
| Model Construction | Procedural geometry (BoxGeometry, CylinderGeometry) with programmatic building layout |
| BIM Layer System | Object-level classification with userData metadata and grouped visibility toggling |
| GLTF Export | Three.js GLTFExporter with organized scene graph and descriptive object naming |
| Camera Controls | OrbitControls with damping, polar angle constraints, and distance limits |
| Lighting | Ambient, hemisphere, two directional lights with shadow maps, and a spotlight |
| Deployment | Static site served via Node.js HTTP server or any static file server |

## Technical Scope and Limitations

- **Interaction Type**: This is an interactive 3D visualization, not a computational BIM authoring tool
- **Geometry**: All building elements are procedurally generated box and cylinder primitives — not imported from IFC or Revit models
- **Building Scale**: The facility layout represents a realistic industrial configuration but is illustrative, not calibrated to a specific real-world site
- **Material Properties**: Materials are visual approximations using Three.js StandardMaterial with roughness/metalness values — not physically validated
- **MEP Routing**: Ductwork, electrical, and plumbing layouts are procedurally placed for visual demonstration, not engineered to code
- **No Live Data**: The model is static with no connection to sensor data, IoT feeds, or operational databases
- **Performance**: Designed for desktop viewing; very large scene complexity may affect mobile performance
- **Not Suitable For**: Engineering sign-off, construction documentation, cost estimation, or structural analysis

## Project Structure

```
├── index.html          # Main application (Three.js BIM viewer)
├── server.js           # Minimal Node.js HTTP static server
├── README.md           # This file
├── LICENSE             # MIT License
├── .gitignore          # Git ignore rules
├── ATTRIBUTIONS.md     # Third-party attribution details
└── assets/
    ├── screenshot.png      # Application screenshot
    └── social-preview.png  # Repository preview image
```

## Quick Start

```bash
git clone https://github.com/studio-public-demos/factory-bim.git
cd factory-bim
node server.js
```

Then open: **http://localhost:8080**

Alternatively, use any static file server:

```bash
python -m http.server 8080
```

## Deployment

This project is deployed using **GitHub Pages** from the default branch root.

**Live demo:** [https://studio-public-demos.github.io/factory-bim/](https://studio-public-demos.github.io/factory-bim/)

## Attribution

- **Three.js** — 3D rendering engine ([MIT License](https://github.com/mrdoob/three.js/blob/dev/LICENSE))
- All building geometry is procedurally generated and original to this project

Detailed attribution information is available in [ATTRIBUTIONS.md](ATTRIBUTIONS.md).

## Built with NebulaCloud Studio

This project was created using [NebulaCloud Studio](https://nebulacloud.studio), an agentic application-building platform for engineering, scientific, geospatial and interactive digital workflows.

NebulaCloud Studio helps domain professionals turn ideas, models, datasets and algorithms into usable, deployable applications.

## Build Your Own Interactive Application

Working with building models, facility layouts, or construction coordination?

Explore the live demo and see how your technical workflow could be transformed into an interactive application.

**[Explore NebulaCloud Studio](https://nebulacloud.studio)**

## Related Demos

- [Cyber Hub Digital Twin](https://github.com/studio-public-demos/cyber-hub-digital-twin) — Geospatial 3D digital twin of an urban commercial hub
- [Delhi Gate Digital Twin](https://github.com/studio-public-demos/delhi-gate-digital-twin) — Heritage monument digital twin with photogrammetry integration
- [Car CFD Viewer](https://github.com/studio-public-demos/car-cfd-viewer) — Interactive computational fluid dynamics results viewer
- [Drone Simulator Pro](https://github.com/studio-public-demos/drone-simulator-pro) — Web-based UAV flight simulator with trajectory visualization
