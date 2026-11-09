# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased](https://github.com/pointblank-club/Lang2Sim/compare/v1.0.0...HEAD)

### Added
- Add standalone live Community Roadmap and PR Tracker in `docs/` querying the GitHub REST API for milestones, pull requests, and real-time review states (`Approved`, `Changes requested`, `Review required`) [[#21](https://github.com/pointblank-club/Lang2Sim/pull/21)] @GiGiKoneti
- Add Keep a Changelog standard (`CHANGELOG.md`) and adopt comprehensive Pull Request template (`.github/pull_request_template.md`) with contributor and reviewer checklists [[#21](https://github.com/pointblank-club/Lang2Sim/pull/21)] @GiGiKoneti
- Add student pre-setup guide and 2-day technical workshop syllabus for REVA Institute open-source robotics development [[#21](https://github.com/pointblank-club/Lang2Sim/pull/21)] @GiGiKoneti

### Changed
- Relicense project under the **Apache License 2.0** in `LICENSE` and configure PEP 621 metadata in `pyproject.toml` [[#21](https://github.com/pointblank-club/Lang2Sim/pull/21)] @GiGiKoneti
- Revamp `README.md` with centered branding, auto-trimmed logo assets, architecture pipeline flowchart, CLI slash command reference, and open-source middleware acknowledgements (Gazebo Harmonic, ROS 2 Humble, Nav2, Shapely) [[#21](https://github.com/pointblank-club/Lang2Sim/pull/21)] @GiGiKoneti

### Fixed
- Enable `universe` and `restricted` package components in `docker/sim/Dockerfile` on Ubuntu 24.04 (Noble) base, resolving `apt-get` missing candidates for `tini`, `iproute2`, and `mesa-utils` [[#21](https://github.com/pointblank-club/Lang2Sim/pull/21)] @GiGiKoneti
- Fix trailing whitespace and end-of-file formatting in `docs/` files to satisfy pre-commit hooks [[#21](https://github.com/pointblank-club/Lang2Sim/pull/21)] @GiGiKoneti

---

## [v1.0.0](https://github.com/pointblank-club/Lang2Sim/releases/tag/v1.0.0)

This release represents the initial foundation of Lang2Sim — autonomously compiling natural language into procedurally generated Gazebo Harmonic simulation worlds, zero-SLAM 2D occupancy costmaps, containerized ROS 2 Nav2 runtime launches, and closed-loop telemetry benchmark evaluation ($NQI$).

### Added
- Add ReAct supervisor reasoning loop (`lang2sim/agent/react_loop.py`) with real-time `<thought>` and `<plan>` streaming demuxing, tool dispatching, and interactive permission validation [[#18](https://github.com/pointblank-club/Lang2Sim/pull/18)] @GiGiKoneti
- Add NVIDIA Nemotron 3 Ultra 550B client (`lang2sim/agent/nemotron_client.py`) with streaming token generation and structured function calling [[#18](https://github.com/pointblank-club/Lang2Sim/pull/18)] @GiGiKoneti
- Add spatial grounding engine (`lang2sim/agent/grounding.py`) translating qualitative user intent into quantitative boundary coordinates and Pydantic Spatial Intermediate Representations (SIR) [[#18](https://github.com/pointblank-club/Lang2Sim/pull/18)] @GiGiKoneti
- Add OpenCode-style full-screen Textual Terminal User Interface (`lang2sim/cli/`) featuring interactive slash commands (`/mission`, `/stress`, `/benchmark`, `/report`, `/dashboard`, `/replay`), reactive plan cards, live log streaming, and telemetry sidebars [[#15](https://github.com/pointblank-club/Lang2Sim/pull/15)] @GiGiKoneti
- Add live SLAM telemetry subscribers tapping `/odom`, `/scan`, and `/tf`, calculating Absolute Trajectory Error ($ATE$), Relative Pose Error ($RPE$), and the Navigation Quality Index ($NQI$) [[#14](https://github.com/pointblank-club/Lang2Sim/pull/14)] @TheCreeperrr
- Add FastMCP perturbation bridge and dynamic adversarial stress injection modules (`lang2sim/perturbation/`) for spawning obstacles, toggling friction, and dropping lighting conditions during navigation [[#14](https://github.com/pointblank-club/Lang2Sim/pull/14)] @TheCreeperrr
- Add procedural 2D geometry solver using Shapely (`lang2sim/world_gen/shapely_solver.py`) for collision-free bounding box arrangement with safety clearance buffers [[#11](https://github.com/pointblank-club/Lang2Sim/pull/11)] @mkumar1205-beep
- Add Zero-SLAM 2D Occupancy Map Slicer (`lang2sim/world_gen/map_slicer.py`) analytically generating `.pgm` and `.yaml` navigation grids directly from 3D world geometry [[#11](https://github.com/pointblank-club/Lang2Sim/pull/11)] @mkumar1205-beep
- Add fixture scene catalog loader and precomputed warehouse models (`catalog/`) with automated bounding volume loading [[#13](https://github.com/pointblank-club/Lang2Sim/pull/13)] @mkumar1205-beep
- Add parametric ROS 2 and Gazebo Harmonic launch synthesizer (`lang2sim/runtime/launch_builder.py`) compiling Jinja2 `.sdf` templates into executable simulation launches [[#9](https://github.com/pointblank-club/Lang2Sim/pull/9)] @DuttaNeel07
- Add programmatic Nav2 Simple Commander dispatcher (`lang2sim/runtime/nav2_dispatcher.py`) and FastAPI control server on port 9090 [[#9](https://github.com/pointblank-club/Lang2Sim/pull/9)] @DuttaNeel07
- Add containerized simulation runtime with hardware GPU/DRI detection and native X11 / WSLg display pass-through (`lang2sim/runtime/docker_runner.py`, `display.py`) [[#12](https://github.com/pointblank-club/Lang2Sim/pull/12)] @DuttaNeel07
- Add automated self-healing supervisor (`lang2sim/runtime/self_healing.py`) intercepting TF disconnects, missing topics, and Nav2 spin locks [[#9](https://github.com/pointblank-club/Lang2Sim/pull/9)] @DuttaNeel07
- Add Dockerless headless replay player (`lang2sim/telemetry/replay.py`) allowing offline visualization and benchmark scoring from logged JSONL telemetry frames [[#14](https://github.com/pointblank-club/Lang2Sim/pull/14)] @TheCreeperrr

### Changed
- Standardize simulation container to run as non-root `sim` user and pre-bake Fuel mesh assets directly into the base image [[#10](https://github.com/pointblank-club/Lang2Sim/pull/10)] @DuttaNeel07
- Wire real-time telemetry streaming through unified ROS 2 bridge WebSocket and JSONL file appender [[#16](https://github.com/pointblank-club/Lang2Sim/pull/16)] @DuttaNeel07

### Maintenance
- Add full project architecture specification and 4-person engineering implementation blueprint [[#6](https://github.com/pointblank-club/Lang2Sim/pull/6)] @GiGiKoneti
- Configure repository-wide code hygiene tooling: migrate linting and formatting to Ruff, install pre-commit hooks (`check-ast`, `check-yaml`, `end-of-file-fixer`, `codespell`), and set up GitHub Actions CI for multi-version Python testing (3.10, 3.12) and Docker container smoke tests [[#19](https://github.com/pointblank-club/Lang2Sim/pull/19)] @TheCreeperrr
- Establish comprehensive 29-suite unit test framework in `tests/` with 260 unit tests verifying Pydantic models, ReAct supervisors, control API endpoints, and self-healing error recovery [[#19](https://github.com/pointblank-club/Lang2Sim/pull/19)] @TheCreeperrr
