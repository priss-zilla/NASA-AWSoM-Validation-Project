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

## 10/9/2025 Meeting
- Earth generates own B field, we call it magnetosphere. Magnetic cavity. Theoretically, anything outside of it should not penetrate it. But SW can enter Earth's magnetosphere. Significant enough SW to enter to cause space weather effects.
- Mars and Venus do not generate B field.
- SW will flow around magnetic field. Magnetosphere is bullet shaped due to this phenomenon.
- Shocks are a type of fluid phenomenon. In a dense atmosphere, information from plane to tell fluid in front of it that an object is coming, time to move around it. This information travels at the speed of sound. Information is transmitted through a compression created by the airplane, only because airplane is moving at subsonic speed. If traveling at supersonic speed, travel faster than information. Have information horizon where anything upstream of that horizon, fluid has no idea that object is coming to it. Fluid have to reduce to subsonic speed before it can flow around object. Exists a discontinuity that supersonic fluid in frame of reference of object reduces to subsonic speed. Also called information horizon. Upstream of fluid flow (solar wind plasma) outside of bow shock, downstream inside. SW carry B field lines, after it slows down, field lines compress together, so B total increases sharply after crossing the shock. Forms magnetosheath. Region between bow shock and magnetosphere. Magnetopause is a thin layer between magnetosphere and magnetosheath. Whole magnetopause layer is a current layer. Earth magnetosphere is the object here (13 Earth radii), SW is the fluid. Reduction of speed of SW is in frame of reference of object. Higher the mach number, more compressed the bow shock shape. 
- A lot of turbulence in magnetosheath B field.
- Spacecraft experiences inbound and outbound crossing. Inbound increase in B field, outbound decrease. SW speed is 400-500km/s on average. Can go up to 800-900 km/s. Temperature increases inbound. Outbound decrease. Same for density and velocity.
- Plasma environment of Mars is called induced magnetosphere.
- Colored data only for particle data (protons and electrons). This is plasma data. Instrument measurees state of the plasma. In SW envt, colour is a narrow straight line. At bow shock, particles travel at different speeds. SW got fluctuations and broadening of colour. Temp. in plasma is width of phase space distribution function. Protons can exist in magnetosphere for a lot longer.
- For protons, after crossing bow shock, red line broadens because protons heat up and fluctuate more. 2 types of bow shocks. 1 is sharper increase, 1 is gentler. Sonic mach number (of solar wind of speed of sound in solar wind) changes, bow shock moves in and out. Move faster than spacecraft. Causes small region of solar wind (non-fluctuating part) to appear in the middle of fluctuations.
- Try plotting Iowa professor's solar wind data. Both plasma and B field data. Look at density, temperature, velocity. Plot those data in the specific carrington rotation for simulation data sent to me. Plot in 2 seperate stacked data. From actual data then can identify magnetosphere regions.
- Google which carrington rotation AWSoM model data is in. Find out which date to which date. Simulation data will give 1-2 days before and after, so find exact dates.
- Come in through University of Maryland, Baltimore County, UMD College Park, Howard University, George Mason University.

## 26/9/2025 Meeting
- Reproduce Carrington Rotation CR2234 plots from slides.
- Dotted red line higher than solid red line. Last 2 columns of data is Io1 and Io2 so far just known as parameters with units of wave energy density. Don't know physical meaning. (Alfven wave energy density). There is formula to combine the 2. E field and B field perpendicular to each other. EM waves carry EM energy. Direction of propagation of energy is the Poynting vector. Magnitude of poynting vector is poynting flux energy density.
- Io1 + Io2 = total wave energy density = sum of kinetic wave energy + magnetic energy density (No electrostatic energy density because Alfven wave is pertrubations in magnetic field along magnetic field lines without electric fields). Alfven wave used to heat solar corona which expands into SW. du means change in velocity. dB cannot be translated into components. Io1 and Io2 have no direction. dB contains no info of direction, also only a scalar value. R
- Red dash line is total B field with Io1 and Io2 added. Solid red line is total B field without parameters. Black line is MAVEN detected total B field. Red lines are AWSoM predictions.
- Don't hard code, soft code to take in CR number and inputs from AWSoM files. Must be able to take in all the CRs.
- No bow shock on the mmon.
- Magnetic field lines prevented from penetrating through conductor. Take very long to diffuse.
- Comet as tail points radially from the sun.
- Go through L11 induced magentosphere to understand Mars interaction with magentic field (similar to Venus).Mars has crustal magentic field.
- How is Saturn so symmetric despite being a gas giant?
- Everything is governed by B field interaction.
- Planterary B field, ch10, cho11
- Go through everthing in Heliophysics.
- J1 visa is exchange scholar visa. Need at least bachelor degree. Only way is to get F1 visa using exchange programme. 
