# dark-matter-ngc3198-simulation
This project consists of a stability simulation, a comparison of rotation curves and a 3D density map of galaxy NGC 3198's dark matter halo, using the exponential disk and NFW profile. 
The main objective is to determine the existence of dark matter and study its distribution within the galaxy. To run the simulations, data for spiral galaxy NGC 3198 were obtained from the SPARC database (such as the maximum radius or the mass of baryonic matter) or from scientific studies (such as the parameters of the exponential disk and NFW profile formulas).

## Scientific context
The existence of dark matter has not been fully proven yet, but theories have emerged from observations of phenomena that cannot be explained by the physical laws currently in place. One of the most classic examples involves observed rotation curves that remain flat, whereas theoretical curves, taking into account only visible mass, usually decline. 

## Libraries used
To develop this project, some libraries have been used:
* **NumPy**: Used for the creation of arrays, vectorization and calculations.
* **Matplotlib**: Utilized to generate the visualization of the simulations.
* **Plotly**: Used to create interactive 3D graphics.
  
Make sure to previously install these libraries.
```
pip install -r requirements.txt
```
## Empirical data and exact values
To simulate galaxy NGC 3198, data pertaining to this exact galaxy have been collected. These data are presented in the following table.

| Parameter | Code notation | Value in Source Table | Value in SI Units | Scientific Source |
| :--- | :---: | :---:| :---:| :--- |
| **HI radius** | r_max | 35.66 kpc | 1.1e21 m | SPARC Database (Lelli et al., 2016) |
| **Total HI mass** | - | 10.869e9 solMass | 2.162e40 kg | SPARC Database (Lelli et al., 2016) |
| **Total Luminosity at [3,6]** | - | 38.279e9 solLum | - | SPARC Database (Lelli et al., 2016) |
| **Mass-to-light ratio** | - | 0.5 solMass/solLum | - | Li et al., 2022 |
| **Asymptotically Flat Rotation Velocity** | - | 150.1 km/s | 150100 m/s | SPARC Database (Lelli et al., 2016) |
| **Scale length disk** | h_R | 2.68 kpc | 8.2696e19 m | Van Albada et al., 1985 |
| **Scale radius** | a | 31.56 kpc | 9.7384e20 m | Li et al., 2022 |
| **Central Halo Density** | p_0 | 1.55e6 solMass/kpc3 | 1.049e-22 kg/m3 | Li et al., 2022 |

Some of these data were used directly in the simulations, while others were used to calculate other necessary values. 

# Parts of the simulation
The project is divided in three parts with different objectives.
### Stability simulation
The simulation consists of two galaxies based on the galaxy NGC 3198: one of them includes the galaxy's total mass (visible and dark), while the other includes only the visible mass. The aim is to see if such high speeds could be reached and maintained without the existence of dark matter. 

To do this, the mass of the baryonic matter is represented by the exponential disk model, while the dark matter distribution follows the NFW profile. The following formulas were used to calculate the enclosed mass of each type of matter:

**Exponential disk (visible matter):**

![Exponential disk](https://latex.codecogs.com/svg.latex?M_{\text{visible}}(r)%20=%20M%20\left[%201%20-%20\exp\left(-\frac{r}{h_R}\right)%20\left(1%20+%20\frac{r}{h_R}\right)%20\right])

**NFW profile (dark matter mass):**

![NFW profile mass](https://latex.codecogs.com/svg.latex?M_{\text{NFW}}(r)%20=%204%20\pi%20\rho_0%20a^3%20\left[%20\ln\left(1%20+%20\frac{r}{a}\right)%20-%20\frac{r}{a%20+%20r}%20\right])

In the images below, the evolution of the two simulated galaxies can be observed.

Galaxy WITHOUT dark matter:

<img width="281" height="201" alt="Captura de Pantalla 2026-10-27 a las 17 21 44" src="https://github.com/user-attachments/assets/90aad27d-d443-40e0-b572-7f02eab065a5" />
<img width="281" height="201" alt="Captura de Pantalla 2026-10-27 a las 17 22 09" src="https://github.com/user-attachments/assets/79653dde-61f6-4fdc-9be0-879723f6f68d" />
<img width="281" height="201" alt="Captura de Pantalla 2026-10-27 a las 17 23 02" src="https://github.com/user-attachments/assets/5dd8b3d1-facd-4caf-9ff6-ffc092f2dabd" />

Galaxy WITH dark matter:

<img width="281" height="201" alt="Captura de Pantalla 2026-10-27 a las 17 23 43" src="https://github.com/user-attachments/assets/e94e429c-ea04-49af-aaeb-ec4e22ab9db5" />
<img width="281" height="201" alt="Captura de Pantalla 2026-10-27 a las 17 24 08" src="https://github.com/user-attachments/assets/24ccfa9f-cd5f-435f-9dae-962b942ddd86" />
<img width="281" height="201" alt="Captura de Pantalla 2026-10-27 a las 17 24 27" src="https://github.com/user-attachments/assets/3d859d2f-88c0-428c-a775-bca173b07aa5" />

On one hand, the simulation that incorporates the total mass of the galaxy (comprising both visible and dark matter) yields a stable result, with the galaxy’s components orbiting along regular paths. This demonstrates that the observed rotational velocity of galaxy NGC 3198 is both attainable and sustainable when the mass of dark matter is taken into account. Conversely, a simulation based solely on the mass of visible matter produces an unstable result; specifically, the galaxy’s components are ejected, which shows that maintaining such a high velocity would be impossible without the presence of dark matter.

### Rotation curve comparison
In addition to the animated simulation, a more theoretical and scientific approach has been adopted to more effectively compare the consequences of a lack of dark matter in a galaxy. Specifically, the rotation curve of the two previous galaxies was simulated, and the results obtained were then compared with the actual rotation curve of the galaxy NGC 3198.

<img width="687" height="468" alt="Captura de Pantalla 2026-10-27 a las 17 27 14" src="https://github.com/user-attachments/assets/40c926f9-a1e3-4c8b-81f6-fb4bd5e7af30" />

The phenomenon of flat rotation curves, as observed by Vera Rubin, has been identified, along with its discrepancy relative to the theoretical rotation curve based on visible mass. Specifically, in a galaxy lacking dark matter, the orbital velocity decreases as the radius increases. Instead, in a galaxy containing such matter, the velocity increases slightly at larger radii. It is also worth noting that this latter curve provides a more accurate description of the observable reality of the galaxy NGC 3198.

These are the errors of both simulated galaxies:

<img width="454" height="143" alt="Captura de Pantalla 2026-10-27 a las 17 29 25" src="https://github.com/user-attachments/assets/5f8b048e-a2d4-40a3-88b1-51c6ec69a1a2" />

### 3D Density Map
To conclude the project, a 3D density map of the galaxy NGC 3198, which was used to simulate the aforementioned galaxies, has been designed to analyze the distribution of dark matter according to the NFW profile. The formula used to study it is the following:

**NFW profile (dark matter density):**

![NFW density](https://latex.codecogs.com/svg.latex?\rho(r)%20=%20\frac{\rho_0}{\left(\frac{r}{a}\right)\left(1%20+%20\frac{r}{a}\right)^2})

This is the obtained result:

<img width="840" height="641" alt="Captura de Pantalla 2026-10-27 a las 17 30 23" src="https://github.com/user-attachments/assets/f463b0ed-6e8c-4161-adb8-0dd8cc00d474" />

The NFW profile describes a spherically shaped dark matter halo, with higher density at smaller radii. The simulation aligns with this premise, as the halo density decreases as the radius increases, confirming that the greatest concentration of dark matter is located at the center of the galaxy.

## File structure
This repository follows the following structure:
* **README.md**: Scientific context, libraries, used data, parts of the simulation, results,
* **requirements.txt**: Libraries that need to be installed before running the code.
* **baryonic_matter_stability.ipynb**: Stability simulation (galaxy without dark matter).
* **dark_matter_stability.ipynb**: Stability simulation (galaxy with dark matter).
* **comparison_rotation_curve.ipynb**: Comparison of rotation curves and error calculation.
* **3d_density_heatmap.ipynb**: 3D density map (dark matter halo distribution).

## How to run the project
This project was developed using **Jupyter Notebook**. There are two options to run the code:
### Option 1 (Google Colab)
Open the file that contains the code you want to run and click on the *Open in Colab* button. By doing that, a Google Colab file will be created where you will be able to run the simulation. You can also click these buttons:
* **3d_density_heatmap.ipynb**: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/adrianamimo/dark-matter-ngc3198-simulation/blob/main/3d_density_map.ipynb)
* **Comparison_rotation_curve.ipynb**: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/adrianamimo/dark-matter-ngc3198-simulation/blob/main/comparison_rotation_curve.ipynb)
* **baryonic_matter_stability.ipynb**: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/adrianamimo/dark-matter-ngc3198-simulation/blob/main/baryonic_matter_stability.ipynb)
* **dark_matter_stability.ipynb**: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/adrianamimo/dark-matter-ngc3198-simulation/blob/main/dark_matter_stability.ipynb)
### Option 2 (Locally) 
Clone the repository and run the commands below in your terminal:
```bash
  git clone https://github.com/adrianamimo/dark-matter-ngc3198-simulation.git
  cd dark-matter-ngc3198-simulation
  pip install -r requirements.txt
  jupyter notebook
```
## Author & Information
**Author**: Adriana Mimo Carrasco

**Project Title**: Demonstration of the existence of dark matter through rotation curve comparison, halo generation, and galaxy simulations. 


