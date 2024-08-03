# [CII] vs FIR Intensity correlation for the FEEDBACK sources #

Perform a greybody fit of Herschel PACS, SPIRE and other continuum lines in order to calculate the FIR Intensity from 40-500 microns. 
Writes a .csv file with the intensities which can be used in the plotting script, also creates dust temperature, tau and FIR .fits maps based on the fitting.
Some switches are included to allow for cropping of the input files and plotting outputs. The CII Intensity is propagated, because the output is used for CII vs FIR Intensity relations for the FEEDBACK (Schneider et al., 2020) project.

The modified blackbody function is the one from Pabst et al. 2021 (https://ui.adsabs.harvard.edu/abs/2021A%26A...651A.111P/abstract) and can be expressed mathematically as follows:

*Planck function*
  
$B_\lambda = \frac{2 h c^2}{\lambda^5} \cdot \frac{1}{e^{\frac{h c}{k_B T_{\text{dust}} \lambda}} - 1}$

   Where:
   - $h$ is the Planck constant,
   - $c$ is the speed of light,
   - $\lambda$ is the wavelength in meters,
   - $k_B$ is the Boltzmann constant,
   - $T_{\text{dust}}$ is the dust temperature in Kelvin.

*Modified Blackbody Intensity:*
   
$I_\lambda = B_\lambda \left(1 - e^{-\tau_{160} \left(\frac{160}{\lambda}\right)^\beta}\right)$

   Where:
   - $\tau_{160}$ is the optical depth at 160 microns,
   - $\beta$ is the emissivity index (default is `beta_fixed`),
   - $\lambda$ is the wavelength in microns, can select the `wavelengths` used in the fitting as a user input.

in case of questions contact Simon Dannhauer via dannhauer@ph1.uni-koeln.de or dannhauer@mpifr-bonn.mpg.de





by S. Dannhauer, 2024
