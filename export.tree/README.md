# Detecting Concussion with Tensor-valued Diffusion Encoding

**Current Version:** 1.0.0

**Dataset Description:** 32 young, healthy control subjects and 30 young patients recently diagnosed with concussion (scanned within 5 days of injury) underwent anatomical and diffusion imaging with to assess whether tensor-valued encoding parameters (microscopic anisotropy and normalized isotropic diffusivity variance) indicate brain structural differences between concussion vs. control groups. 

**Concussion Group:**

- Inclusion criteria: Participants must be adults between the ages of 18 – 30 (all genders, sexes, and races/ethnicities) who were recently diagnosed with concussion and could complete the study scan within five days of injury occurrence. Participants could have any history of prior head injuries. 

- Exclusion criteria: Exclusionary criteria included penetrating injury, complicated traumatic brain injury, visible signs of injury on structural MRI scan (see Clinical Imaging), and contraindications to MRI (non-removable metal, incompatible medical devices, hearing loss, tinnitus, claustrophobia), and pregnancy. While most participants had no clinically significant cardiac, neurological, pulmonary, or psychiatric diseases other than mild-moderate mood and attention deficit disorders, a few participants had other co-occurring conditions (See Rizor et al., 2026, _Imaging Neuroscience_, Supplementary Information Table S1).

**Control Group:**

  - Inclusion criteria: Participants must be adults between the ages of 18 – 30 (all genders, sexes, and races/ethnicities). 

  - Exclusion criteria: Exclusionary criteria included previous concussion diagnosis within a year prior to participation, contraindications to MRI (non-removable metal, incompatible medical devices, hearing loss/tinnitus, claustrophobia), pregnancy, or clinically significant cardiac, neurological, pulmonary, or psychiatric diseases other than mild-moderate mood (anxiety or depression) and attention deficit disorders.

**MRI Protocol**: 

- Study Imaging: Participants underwent magnetic-resonance imaging (MRI) in a Siemens 3T Prisma scanner with a 64-channel phased-array head/neck coil. First, high-resolution whole-brain T1-weighted magnetization prepared rapid gradient echo (MPRAGE) anatomical scans were acquired (TR = 2500 ms, TE = 2.22 ms, TI = 851 ms, flip angle = 7°, FOV = 241x241 mm, voxel size = 0.9 mm isotropic). Following the anatomical scan, participants underwent a series of linear (b-values: 0-2 ms/µm², directions = 1-30) and spherical (b-values: 0-1.5 ms/µm², directions = 3) tensor-valued diffusion-weighted acquisitions (for more information, see Rizor et al., 2026, _Imaging Neuroscience_, Supplementary Information Methods and Figs. S1-S5; TR = 6308 ms, TE = 80 ms, flip angle = 90°, FOV = 230x230 mm (whole-brain), voxel size = 2.0 x 2.0 x 4.0 mm, parallel imaging acceleration factor (iPAT) = 2, maximum diffusion gradient amplitude = 80.0 mT/m). 

- Clinical Imaging: All participants additionally underwent a battery of routine clinical brain MRI scans. These whole-brain scans include a T2-weighted turbo spin echo (TSE) sequence (TR = 6000 ms, TE = 100 ms, flip angle = 150°, FOV = 220x220 mm, voxel size = 4.0 mm isotropic) a T2-weighted FLAIR sequence (TR = 9000 ms, TE = 83.0 ms, flip angle = 150°, FOV = 220x220 mm, voxel size = 0.7 x 0.7 x 4.0 mm), a T2*-susceptibility weighted sequence (TR = 738.0 ms, TE = 19.90 ms, flip angle = 20°, FOV = 220 x 220 mm, voxel size = 0.7 x 0.7 x 4.0 mm), and a diffusion-weighted imaging sequence (b-values = 0, 0.5, 1 ms/µm², directions = 3, TR = 4100 ms, TE = 81 ms, flip angle = 90°, FOV = 230x230 mm, voxel size = 2.0 x 2.0 x 4.0 mm, iPAT factor = 2, max. diffusion gradient amplitude = 80.0 mT/m). Clinical MRI scans were read blinded to group membership by a licensed neurologist with expertise in neuroimaging. No participant had evidence of mass effect, micro- or macroscopic hemorrhage, diffusion abnormalities suggestive of ischemia, or other significant findings. 

**Important note on diffusion gradient directions (bvec files)**:

The .bvec files in this dataset are the original, unmodified files from the scanner. When used as-is, we found that their tensor fits give principal diffusion directions that don’t agree with the expected anatomy. For Rizor et al., 2026, _Imaging Neuroscience_, we corrected every .bvec file before any processing as shown below: 

- New row 1 (x) = −(original row 2)
- New row 2 (y) = −(original row 1)
- New row 3 (z) = original row 3

To reproduce our results, apply the same correction. 

**Rizor et al., Code**: [All code used for Rizor et al., 2026, _Imaging Neuroscience_ can be found here.](https://github.com/ejrise/tve-con) 

## Citation
Please cite the following:  

[Rizor, E.J., Dundon, N.M., Hayes, M., Sabugo, K., & Grafton, S. (2026). Characterizing white matter microstructure in acute concussion with tensor-valued diffusion encoding. _Imaging Neuroscience_.](https://doi.org/10.1162/IMAG.a.1483) 

Rizor, E. J. (2025). Mapping the human brain with multidimensional diffusion and multi-echo imaging to advance clinical insights (Order No. 31768051). Available from Dissertations & Theses @ University of California; ProQuest Dissertations & Theses A&I; ProQuest Dissertations & Theses Global. (3199000581). Retrieved from https://www.proquest.com/dissertations-theses/mapping-human-brain-with-multidimensional/docview/3199000581/se-2


