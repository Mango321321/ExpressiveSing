
# <center>EXPRESSIVESING: SINGING VOICE SYNTHESIS WITH VIBRATO MODELING AND LATENT SPECTROGRAM REPRESENTATION</center>

<center>Yingjie Song<sup>1</sup>, Wei Song<sup>3</sup>, Wei Zhang<sup>3</sup>, Zhengchen Zhang<sup>3</sup>, Youzheng Wu<sup>3</sup>, <br> Dan Zeng<sup>1</sup>, Zhi Liu<sup>1</sup>, Yang Yu<sup>4</sup>, Xiaoping Zhang<sup>1,2</sup> <br><br></center>

<center><sup>1</sup> School of Communication and Information Engineering, Shanghai University, China<br>  
<sup>2</sup> Ryerson University, Toronto, Canada<br>
<sup>3</sup> JD AI Research, Beijing, China<br>
<sup>4</sup> Shanghai Conservatory Of Music, China</center>


## Abstract
-----------

 <div style="text-align: justify">This paper proposes an expressive singing voice synthesis system by introducing explicit vibrato modeling and latent spectrogram
representation. Vibrato is essential to the naturalness of synthesized sound, due to the inherent characteristics of human singing. Hence, a deep learning based vibrato model is introduced in this paper to control the vibrato’s likeliness, rate, extent, phase in singing. In particular, the vibrato likeliness is proposed to control if vibrato should
be added to a music note, which would help improve the singing voice naturalness. Since the vibrato likeliness label is hard to be extracted accurately from training data, a novel vibrato likeliness labeling method is proposed, and the simulated data is used to train the vibrato likeliness labeling network. Meanwhile, the power spectrogram of audio contains rich information that can improve the expressiveness of singing. An auto-encoder based latent spectrogram bottleneck feature is proposed for expressive singing voice synthesis. Experimental results on the open dataset NUS48E show that both the vibrato modeling and the latent power spectrogram representation could significantly improve the expressiveness of singing voice. The audio samples are shown in the demo website.</div>
 
<div align=center><img src="./image/overall.jpg"></div>

## Overall Performance
-----------
<div align=center><img src="./image/mos.jpg" width="60%"></div>
<br>

<table align="center">
  <thead>
    <tr>
      <th></th>
      <th>Sample 1</th>
      <th>Sample 2</th>
      <th>Sample 3</th>
      <th>Sample 4</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><b>Baseline</b></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/baseline/VKOW_20_JLEE_1.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/baseline/VKOW_20_JLEE_2.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/baseline/VKOW_20_JTAN_1.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/baseline/VKOW_20_JTAN_1.wav"></audio></td>
    </tr>
  </tbody>

  <tbody>
    <tr>
     <td><b>USVC</b> </td>
       <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/USVC/VKOW_20_JLEE_1.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/USVC/VKOW_20_JLEE_2.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/USVC/VKOW_20_JTAN_1.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/USVC/VKOW_20_JTAN_1.wav"></audio></td>
    </tr>
  </tbody>

  <tbody>
    <tr>
     <td><b>WGANSing</b> </td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/WGANSing/VKOW_20_JLEE_1.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/WGANSing/VKOW_20_JLEE_2.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/WGANSing/VKOW_20_JTAN_1.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/WGANSing/VKOW_20_JTAN_1.wav"></audio></td>
    </tr>
   </tbody>
   
   <tbody>
    <tr>
     <td><b>UCSVC</b> </td>
       <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/UCSVC/VKOW_20_JLEE_1.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/UCSVC/VKOW_20_JLEE_2.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/UCSVC/VKOW_20_JTAN_1.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/UCSVC/VKOW_20_JTAN_1.wav"></audio></td>
    </tr>
  </tbody>
 
 <tbody>
    <tr>
     <td><b>ExpressiveSing</b> </td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/ours/VKOW_20_JLEE_1.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/ours/VKOW_20_JLEE_2.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/ours/VKOW_20_JTAN_1.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/mos_demo_web/ours/VKOW_20_JTAN_1.wav"></audio></td>
    </tr>
   </tbody>
</table>
<br>

#### · Additional experiment
<table align="center">
  <thead>
    <tr>
      <th></th>
      <th>Sample 1</th>
      <th>Sample 2</th>
      <th>Sample 3</th>
      <th>Sample 4</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><b>Fastspeech2</b></td>
      <td><audio controls="" preload="auto">
            <source src="audio/ADIZ_01_7.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/ADIZ_01_8.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/ADIZ_09_2.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/ADIZ_09_2.wav"></audio></td>
    </tr>
  </tbody>

  <tbody>
    <tr>
      <td><b>ExpressiveSing</b></td>
      <td><audio controls="" preload="auto">
            <source src="audio/ADIZ_01_7.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/ADIZ_01_8.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/ADIZ_09_2.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/ADIZ_09_2.wav"></audio></td>
    </tr>
  </tbody>
</table>
<br>

##  Ablation Study
-----------
<div align=center><img src="./image/abtest.jpg" width="60%" ></div>

#### · ES-V vs  ES
<table align="center">
  <thead>
    <tr>
      <th></th>
      <th>Sample 1</th>
      <th>Sample 2</th>
      <th>Sample 3</th>
      <th>Sample 4</th>
      <th>Sample 5</th>
      <th>Sample 6</th>
      <th>Sample 7</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td nowrap="nowrap"><b>ES-V</b></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_whole_vibrato/ADIZ_01_7_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_whole_vibrato/ADIZ_09_2_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_whole_vibrato/ADIZ_18_1_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_whole_vibrato/JLEE_08_12_output.wav"></audio></td>
     <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_whole_vibrato/PMAR_11_11_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_whole_vibrato/PMAR_15_6_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_whole_vibrato/VKOW_20_2_output.wav"></audio></td>
    </tr>
  </tbody>
 
  <tbody>
    <tr>
      <td><b>ES</b></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_our_pitch/ADIZ_01_7_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_our_pitch/ADIZ_09_2_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_our_pitch/ADIZ_18_1_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_our_pitch/JLEE_08_12_output.wav"></audio></td>
     <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_our_pitch/PMAR_11_11_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_our_pitch/PMAR_15_6_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/pitch/output_our_pitch/VKOW_20_2_output.wav"></audio></td>
    </tr>
  </tbody>

 
</table>
<br>

#### · ES-E1 vs  ES 
<table align="center">
  <thead>
    <tr>
      <th></th>
      <th>Sample 1</th>
      <th>Sample 2</th>
      <th>Sample 3</th>
      <th>Sample 4</th>
      <th>Sample 5</th>
      <th>Sample 6</th>
      <th>Sample 7</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td nowrap="nowrap"><b>ES-E1</b></td>
         <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_1d_energy/ADIZ_09_7_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_1d_energy/MCUR_10_2_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_1d_energy/MCUR_10_4_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_1d_energy/MPUR_03_3_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_1d_energy/PMAR_15_12_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_1d_energy/VKOW_11_14_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_1d_energy/ZHIY_02_8_output.wav"></audio></td>
    </tr>
  </tbody>
 
  <tbody>
    <tr>
      <td nowrap="nowrap"><b>ES</b></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_energy_multitask/ADIZ_09_7_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_energy_multitask/MCUR_10_2_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_energy_multitask/MCUR_10_4_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_energy_multitask/MPUR_03_3_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_energy_multitask/PMAR_15_12_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_energy_multitask/VKOW_11_14_output.wav"></audio></td>
      <td><audio controls="" preload="auto">
            <source src="audio/abtest/energy/Dian_energy_multitask/ZHIY_02_8_output.wav"></audio></td>
    </tr>
  </tbody>

</table>
