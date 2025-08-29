# NASA-AWSoM-Validation-Project

## 29/8/2025 ##
### Update on Tasks ###
- Exploration of pyspedas and pytplot documentations
- Tried Google Colab but found to be incompatible. Switched to Python Environment on VSCode instead
- Essential codes for setting up pyspedas and pytplot + specific functions are found on GitHub PyTplot and PySpedas
- Facing issues with compatibility between pyspedas, pytplot and numpy.

## Meeting 29/8/2025
- Stack plot: 2 plots stacked on top of each other 
- B (magnetic field): Bx, By, Bz, Btotal (magnitude of vector). tplot gives colours automatically. Split the vector components out. 
- When MAVEN is deep inside the solar wind region (not plasma environment), magnetic field becomes very small. Very common in solar wind for B field to go from negative to positive to negative. Rotation in B field vector means something is happening in the solar wind. 
- Heliospheric current sheet
- B field and plasma dynamics affect each other. Everytime cross a plasma boundary, B field will change. Fuzzy part of plot shows that MAVEN is inside plasma envrionment. Will always go back into the same plasma environment.
- Note inbound and outbound to plasma environment.
- Mars has crustal magnetic field (remains at the moment when Mars loses it's global magnetic field).
- For magnetic dipole, B field always proportional to 1/r^3. Any B field can bre represented as a gradient of a scalar potential. Can model any magnetic source as a dipole. If Btotal increases, means getting close to a source (localized crustal magnetic field on the surface of Mars -- in the Southern Hemisphere, localized at 1 region).
- International Geomagnetic Reference Field (generic equation for magnetic field). Expand first order term will get magnetic field of a dipole. So easiest to model sources as dipoles. At great distance, more likely to detect as dipole. Go closer to take more sensitive measurements of higher order terms.
- Earth's polarity reverses every 10,000 years.
- Dipole moment free to move around in molten state. When cools down, become solid. Locking dipole moment in 1 direction. New magma comes out, Earth's magnetic field pointing in other direction, now magentic field all points in other direction except solidified states that spread out and B field pointing in opposite direction.
- Don't see crustal magnetic field on Venus due to high tectonic activity. 
