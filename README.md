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

## 5/9/2025 Meeting
- Load and plot AWSoM model data files.
- By end of this semester, get to the point where we can start analyzing the data itself, go beyond plotting. Using stats techniques learnt in mathematics class to compare data.
- Mid-term goal to stack plots properly, plot data out together.
- Simulation data all in text data.
- Gang Kai will send email on what each column means.
- n_proton is in /cm^3. convert to /m^3 for plotting. T_proton is proton temp (change to Kelvin). Use high resolution data. Cannot fit plasma measurement to the magnetic field measurement. Need to downsample magnetic field data. Only want SW measurements. Only use High-resolution upstream driver data (already filtered out solar wind data). Try plotting out plasma data to see how it looks like. next week will go through which data represents magnetosphere and SW.
- Must calculate B total from data, then plot. Plot Bx, By, Bz, B_total, Vx, Vy, Vz, V_total, temperature. Only plot out the time interval that they ran the simulation for.
- 2 carringtons worth of data to send me. They are sequential. But he will send me 1 (the prior) first. 27 days (1 carrington rotation) worth of data. SE? Figure out how to get specific date range from all the data. Try to construct a sub-routine that will automatically input start and end date, code will pick out all the data needed. Soft code to be allow generalized inputs.
- Magnetic field data measured by magnetometer, SWIA measures all densities of plasma, velocities of plasma, and temp of plasmas. SW mostly protons and elctrons, but has 4% of alpha particles. Plasma velocity (bulk velocity) is not particle velocity. Inside plasma, each particle moving in random directions. Calculate bulk velocity by integrating over phase space, over al particles' velocities. Each velocity plot out, will come out in a distribution of velocities. Integrate -infinity to infinity. Temperature is defined as width of velocity distribution. Concept of temp very different for plasma from our normal understanding.
- ASWR 401/601 and 402/602. First 2 lecture notes got basic plasma physics. Will show how to calculate ion energy distribution functions integrate across phase space, to get densities, velocities, temperatures. Go and understand it then GK will go through. Look at the video recording and lecture slides. Ion analyzer measures individual particles at specific velocities, collect them then output of analyzer is to construct velocity distribution function of the collective plasma at the specific location. Then integrate it. Working of plasma analyzer is in Lecture 4 Electrostatic Analyzer in 401/601 (can skip). Go through Lecture 2 401/601 parts.
- Solaw wind is a plasma. L6 on solar wind, will see why we got magnetic field. SW contains Sun's magnetic field. Magnetic fields frozen in the plasma. L2 on particle motion.
- 1 measurement of plasma data takes 4 secs. Take 4 secs worth of B field data then average it out, Give same time stamp to that 1 value of B field data to that 1 value of plasma data. 32 B field data components taken per sec. Iowa prof averaged across 4 secs, so 128. 
