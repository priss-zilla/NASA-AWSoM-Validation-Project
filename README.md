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

## Update on Tasks 1/10/2025 
- Plotted Carrington Rotation CR2234 for AWSoM data sent to me by Gang Kai and MAVEN data by Uni of Iowa professor https://homepage.physics.uiowa.edu/~jhalekas/drivers.html
- Did unit conversions for AWSoM data according to email details sent my Gang Kai.
- Did conversion from eV to K for MAVEN data.
- To clarify: Proton temp = ion temp? In most cases yes, but not always true. SW mostly protons. 
- Comment on data plots: Dashed line for B field magnitude with wave energy parameters matches original B field exactly (does not follow slides despite following Gang Kai's equations below. Problem with db^2 being too small?). All AWSoM data does not capture subtle patterns in slides (but rough overall patterns are there). MAVEN data matches slides perfectly. 

I = I01+I02 = 1/2*rho*du^2 (the kinetic energy) + 1/2 db^2/mu_0 (the magnetic energy)
and du = db/sqrt(mu_0 * rho) (the Alfven wave equation), then we can get
I = db^2/mu_0 (well, if we already know that turbulent kinetic energy is equal to the magnetic energy, we can skip all the derivations)
So this formula can give an estimate of db, the total magnetic field is then given by
B^2 = B_average^2 + db^2
B_average is the average magnetic field simulated in MHD (bx by bz in the file).

## Meeting 1/10/2025
- Lectures 3-9, 11 (most important).
- Next step is to interpolate MAVEN data.
- Plots match well! AWSoM data given was for ADAPT-HMI.
- AWSoM got more data points so lines look smoother
- Numerical thing will linearly interpolate lacking MAVEN data points based on AWSoM data points by creating linear functions for time data points to match AWSoM's. At the end, MAVEN will have same no. of data points as AWSoM.
- Code for interpolation already done up by Python. Quadratic, cubic interpolations etc. Limitations of higher order interpolations is that they will give you functions that vary a lot. Need to use instincts to see whether interpolation is good. Use naked eyes to see if interpolation makes sense (best-fit, not too many fluctuations). Can try find numerical code that gives best-fit interpolation.
- Need same number of data points to compare euclidean distances for every data point pair.
- Dynamic time warping python code exists. Do this after interpolation.
- Gang Kai's plots in slides for MAVEN are already interpolated.
- Interpolations will create variations in data that are numerical and not real. So decrease order of interpolation to reduce that. Use ready made packages in Python. 
- Interpolations is different from smoothing. Gang Kai's plots not smoothed out.
- Smoothing (type of signal processing): Can and don't need to downsize data points, low-pass filter (filter out high frequency fluctuations), moving boxcar averages. Find ready packages to use.
- For now, AWSoM can only simulate fluctuations across a few days. So we remove higher frequency fluctuations in MAVEN data to match with AWSoM data. 

(Linear interpolation drawing) ![C865A133-119B-4119-9A82-55DDC15E69CC_1_105_c](https://github.com/user-attachments/assets/b64bbc40-1e04-430f-9cff-ecc4786d44aa)
(Quadratic intepolation drawing) ![B574E8F9-E338-4CF8-928A-9C496F97253B](https://github.com/user-attachments/assets/b9156ea3-ede5-4349-926a-669fdf64ea09)
(Dynamic Time Warping drawing) ![0A9FF8B4-7435-41AE-A9E8-88CE54E79FA5_1_105_c](https://github.com/user-attachments/assets/f1a83a09-3266-496b-8a87-85a5864c4e06)

## Task Updates 8/10/2025 ##
- Tried 2 methods of interpolation in Python: interp1d and pChip.
- interp1d gives too drastic fluctuations, very bad interpolations for all 'kinds' including quadratic and cubic.
- pChip is better, but fluctuations still obvious in B field plot, different from Gang Kai's plots

Logistics: 
Must still register under F1 visa. J1 visa can only for graduates to be visiting scholar. So must go through university. Goddard is not a private company, so cannot go through J1 visa. 
Need to know what OEP will pay for. 
Contact GEM discoverer first regarding if they got any programme with UoM.

## Meeting 15/10/2025

For CR2235, Mars and Earth and Sun are radially aligned, Mars is on the Earth-Sun line. Magnetic field data not good due to poor Earth and Mars magnetic connection, input from Earth to generation Mars predictions is bad. But solar wind data is good so plasma data is good. We have not tested/proven when Mars and Earth are magnetically aligned, how is their comparison. We have only proven that when they're radially aligned, the magnetic field comparison is terrible.  Parker spiral so solar wind 
xyz coordinates are wrt to Earth. x is in Sun-Earth line, radial coordinate equivalent. Satellite measure negative B field first then positive B field. Opposite magnetic fields connect somewhere at infinity, produces a curl that using RHR, current points outwards. Heliospheric current sheet. Wavers around like a ballerina skirt. At solar maximum, skirt becomes very complex. But at solar minimum it's well-defined. CR2234 at solar minimum. Bx, By, Bz doesn't fluctuate a lot. 
Solar minimum --> don't see a lot of sunspots on surface of sun
Solar maximum --> see a lot. 
High speed streams: pocket of solar wind moving very fast. Will catch up with slower solar wind. Compress together to create compression solar wind region. 
Do not need a coronal mass ejection to cause a geomagnetic storm. Compression region can also cause geo storm. Occurs a lot more oftern than CME. Sun rotating so high speed stream structure will hit spacecraft. 
See more interplanetary shocks on planets further from sun. Cause geomagnetic storms. Occurs when fast SW compresses slow SW. Creates a forward and reverse shock (behind fast SW there is rarefaction, low plasma density). Release of pressure happens when spacecraft goes through reverse shock. Shock can accelerate particles to become solar energetic particles. 
CR2235 does not really experience shocks as it is in quieter region of solar wind speed during sun's rotation. 
Parker spiral formed by interplanetary magnetic field line.
SW velocity the same in radial direction, strongest component in x, not much variation in y or z direction. As sun rotates, magnetic field lines will form the parker spiral. PLasma itself does not do this spiral motion. 
If the sun were not moving, magnetic field will go out radially. But solar wind only just always go out radially. 
It is always the plasma that controls magnetic field. 
Since B field is connected to Sun, shape will change, will no longer go out radially. Parker spiral indicates whether planets are magnetically connected. 
Magnetic field and ballerina skirt permeate entire space. 
Part 1: Test data when Mars and Earth are magnetically aligned. Test hypothesis that B field comparison is better. 
Part 2: Earth and Mars sometimes magnetically connected and disconnected. But what happens when they are both not radially aligned and not magnetically connected. 
Part 3: Find an event where Earth and Mars is aligned, if there is a CME going through Earth and Mars. See if arrival time at Mars predicted by AWSoM is the same as what was observed by data. CME goes in straight line, does not care if planets are magnetically connected or not. If Earth and Mars are not aligned but CME goes through Mars, see whether CME predictions by AWSoM with Earth inputs are accurate. Also see if magntiude as predicted by the model itself is the same as what was observed on Earth and Mars. 

Task for this week: Attempt Euclidean matching between 2 curves (AWSoM and interpolated MAVEN). Try time warping matching. Code on GitHub for time warping sent to me. GK will send 2235. Do same thing as 2234. 

## Meeting 22/10/2025 ##
URECA grant should cover flights, lodging, food. 
European Geophysical Conference in Vienna. Nice place to travel solo. 3 - 8 May. Deadline of abstract submission in January 15. 
- Come up with metric to compare the 2 curves.
- To calculate Euclidean distance, need to remove fluctuations with period of 1 day. Things fluctuating in AWSoM data are in 2-3 days. What is the cut-off frequency of fluctuations?
- Low-pass filter: filter out high frequencies. Use FFT to transform into frequency domain, then select the frequency, zero out the power for the higher frequency then inverse fourier transform back. If signal is periodic, LPF would be good. When doing FFT, look at power in frequency domain, if have very strong signal look at peak in power. We want to keep lower frequencies with higher powers. Plot power as function of frequency with log scale. Some higher frequencies may give spikes in powers which need to be filtered out. If power spectrum does not show obvious threshold to cut off, then use moving boxcar. 
- Also look into moving box car average, easier than LPF.
- Further smooth out MAVEN data first being doing Euclidean matching. 
- don't have to weight nor normalize for 4 seperate variables Euclidean distances. Then figure out how to optimise weights when combining Euclidean distances. What is your rationale behind using certain weights? Should it go to the variable with lowest or highest agreement with MAVEN data?
- GK will send me a couple of papers regarding point-to-point comparison metrics.
- Look at what methods the papers use to compare observations and predictions on Earth. We are trying with Euclidean first as everyone uses that in the beginning. If you can a better metric of comparison, use that instead.
- For DTW to work, interval between indexes must be the same. So doing warping for indexes is also doing warping for time. My DTW is mapping in an unintuitive way.
- Look at paper and Github sent to me to look at how to properly do DTW.
https://iopscience.iop.org/article/10.3847/1538-4357/ac4af6
https://github.com/SamaraEvangelia/DTW_ForSolarWindEvaluation
