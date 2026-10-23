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
pip install numpy
pip install matplotlib
pip install plotly
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
```
Exponential disk (visible matter): M * [1 - exp(-r / h_R) * (1 + r / h_R)]
NFW profile (dark matter): 4 * pi * p_0 * a^3 * [ln(1 + r / a) - r / (a + r)]
```
On one hand, a simulation that incorporates the total mass of the galaxy (comprising both visible and dark matter) yields a stable result, with the galaxy’s components orbiting along regular paths. This demonstrates that the observed rotational velocity of galaxy NGC 3198 is both attainable and sustainable when the mass of dark matter is taken into account. Conversely, a simulation based solely on the mass of visible matter produces an unstable result; specifically, the galaxy’s components are ejected, which shows that maintaining such a high velocity would be impossible without the presence of dark matter.

### Rotation curve comparison
In addition to the animated simulation, a more theoretical and scientific approach has been adopted to more effectively compare the consequences of a lack of dark matter in a galaxy. Specifically, the rotation curve of the two previous galaxies was simulated, and the results obtained were then compared with the actual rotation curve of the galaxy NGC 3198.

The phenomenon of flat rotation curves, as observed by Vera Rubin, has been identified, along with its discrepancy relative to the theoretical rotation curve based on visible mass. Specifically, in a galaxy lacking dark matter, the orbital velocity decreases as the radius increases. Conversely, in a galaxy containing such matter, the velocity increases slightly at larger radii. It is also worth noting that this latter curve provides a more accurate description of the observable reality of the galaxy NGC 3198.

### 3D Density Map
To conclude the project, a 3D density map of the galaxy NGC 3198, which was used to simulate the aforementioned galaxies, has been designed to analyze the distribution of dark matter according to the NFW profile. The formula used to study it is the following:
```
NFW profile (dark matter density): p_0 / ((r / a) * (1 + r / a)^2)
```
The NFW profile describes a spherically shaped dark matter halo, with higher density at smaller radii. The simulation aligns with this premise, as the halo density decreases as the radius increases, confirming that the greatest concentration of dark matter is located at the center of the galaxy.

