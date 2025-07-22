
# Orbital Computation Cloud Service: AstroTraj (Trial Operation)

- **AstroTraj**: Astrodynamics Trajectory Optimization  
    - AstroTraj is a cloud-native service that provides powerful and flexible tools for spacecraft trajectory optimization and mission design.

## Project Overview

- This service offers cloud-based trajectory optimization and computation using DDP (Differential Dynamic Programming). It primarily targets users who require multi-revolution trajectory optimization for low- or medium-thrust spacecraft, including:
    - Private orbit transfer service providers (e.g., LEO to LEO, GTO to GEO)
    - Researchers in aerospace engineering
    - Graduate-level students
    - Engineers and developers interested in astrodynamics

- Currently, **free of charge during the trial period**.

## Using AstroTraj

- Access the cloud version here: [AstroTraj](https://d3ckxaulmhak11.cloudfront.net/)
- GitHub repository (local installation version): Coming soon

### Quick Start

1. Access the service via a web browser  
    - [AstroTraj](https://d3ckxaulmhak11.cloudfront.net/)
2. Click the `Start trajectory calculation` button in the top right
3. On the `Settings` screen, enter an arbitrary name in the `TrialName` field
4. Select a configuration from the `Preset` options:
    - `DDP (Earth to Mars)`
    - `DDP (GTO to GEO)`
    - `Multishoot (Multiflyby)`
    - `Multishoot (NRHO)`
5. Click the Run button  
    - Wait from several minutes up to 120 minutes depending on the initial guess and target:
        - Approx. 5 minutes for `DDP (Earth to Mars)`
        - Approx. 120 minutes for `DDP (GTO to GEO)`

## Features

- Trajectory optimization using DDP (e.g., Earth orbit transitions, rendezvous, multi-revolution orbits)
- Input format: Orbital elements (position, velocity, time)
    - Keplerian elements: **Planned for future support**
- Output formats:
    - CSV: Trajectory, thrust time series, fuel consumption
    - Images (UI only): 3D trajectory and thrust variation (initial, intermediate, final)
- Supported formats: JSON, CSV

---

## License & Terms of Use
- T.B.D.

## Prohibited Activities
- T.B.D.

## Unauthorized Commercial Use
- T.B.D.

## Redistribution of the Service
- T.B.D.

## Unauthorized Use of Others’ API Keys
- T.B.D.

## Current Limitations

- Limits on the number of iterations per computation (details to be published soon)
- Maximum of 20 simultaneous requests (with up to 16 running in parallel)
    - The 17th and subsequent requests will be queued; requests beyond 20 will be rejected
- Escape trajectories are not currently supported

*Note: These plans are subject to change.*

## Roadmap

## Future Roadmap

| Phase | Planned Content | Timeline |
|-------|------------------|----------|
| Cloud Version Trial Release | Free release with limited time/features (at ISTS) | Q3 2025 |
| Cloud Version User Feedback Collection & Response | Feature improvements/additions based on trial feedback | Q4 2025 |
| Cloud Version Official Release | Login feature, pricing introduced (with free tier), etc. | Q1 2026 |
| Local PC Installable Version Trial Release | Limited feature release (details T.B.D.) | Q2 2026 |
| Local PC Installable Version User Feedback Collection & Response | Feature improvements/additions based on trial feedback | Q3 2026 |
| Local PC Installable Version Official Release | Released as OSS on GitHub (details T.B.D.) | Q4 2026 |

*Note: These plans are subject to change.*

## Security & Privacy

- In the trial version, user computation data is stored and currently visible to all users.
- In the future, login functionality will be implemented, and in the paid version, data will be private.
    - API keys will be issued per user or organization.

## Example Applications & Use Cases

- Spacecraft trajectory planning:
    - LEO to LEO
    - GTO to GEO

- Fuel optimization for small satellites
- Research on swarm control (cooperative multi-spacecraft operations)

## Papers & References

- Naoya Ozaki: *Tube Stochastic Differential Dynamic Programming and Application to Robust-Optimal Spacecraft Trajectory Design*, Ph.D. Thesis, The University of Tokyo, 2018.

- Gregory Lantoine and Ryan P. Russell: *A Hybrid Differential Dynamic Programming Algorithm for Constrained Optimal Control Problems. Part 1: Theory*, JOTA, Vol. 154, No. 2, pp. 382-417, 2012.

- Gregory Lantoine and Ryan P. Russell: *A Hybrid Differential Dynamic Programming Algorithm for Constrained Optimal Control Problems. Part 2: Application*, JOTA, Vol. 154, No. 2, pp. 418-442, 2012.

- Jonathan David Aziz: *Low-Thrust Many-Revolution Trajectory Optimization*, Ph.D. Thesis, University of Colorado, 2018.

- Shun Kodama, Naoya Ozaki, et al.: *A study of GPU acceleration of trajectory design software using DDP*, 64th Space Sciences and Technology Conference, 2020.

- Shun Kodama, Naoya Ozaki, et al.: *Development Status of Trajectory Design Software Using DDP - A Case Study of Trajectory Transfer from NRHO to LLO -*, 67th Space Sciences and Technology Conference, 2023.

- Shun Kodama, Naoya Ozaki, et al.: *Development Status of Trajectory Design Software Using DDP – Application Study to Trajectory Transfer from Earth Orbit to the Lunar Gravity Field -*, 68th Space Sciences and Technology Conference, 2024.

## Contact & Feedback

- Email:  
    - Kodama: s-kodama@isp.co.jp  
    - Shimizu (Toshiro): t-shimizu@isp.co.jp  

- Issue submission: (Coming soon)

## Feedback Form (Coming soon)

- This project is currently in trial operation, and its contents are subject to change without notice. Thank you for your understanding.

## Known Issues & Unexpected Behaviors

### "Home" Screen

- Sorting by `Start Time (JST)` may not work correctly in ascending/descending order  
- The pagination display (e.g., `1...2,3,4...5`) sometimes shows `...` unnecessarily (confirmed on Windows/MacOS in Chrome)
- When a process stays in the `Running` state for a long time, clicking `View` may show `No Data`, but after returning with `Go to Home`, `Status: SUCCEEDED` may appear and clicking `View` again may work properly (confirmed on MacOS/Chrome)

### "Result" Screen

- Zooming and panning can be done with the mouse wheel and dragging (explicit instruction under consideration)
    - On MacOS/Chrome, zooming with the mouse wheel can repeat and become unstable
- When changing the `step` in `Intermediate Result`, the model may spin after image rendering, which can feel unnatural (confirmed on Windows/MacOS in Chrome)
