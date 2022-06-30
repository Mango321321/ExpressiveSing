# <center>Singing Voice Synthesis with Vibrato Modeling and Latent Energy Representation</center>

<!-- <center>Yingjie Song<sup>1</sup>, Wei Song<sup>3</sup>, Wei Zhang<sup>3</sup>, Zhengchen Zhang<sup>3</sup>, Youzheng Wu<sup>3</sup>, <br> Dan Zeng<sup>1</sup>, Zhi Liu<sup>1</sup>, Yang Yu<sup>4</sup>, Xiaoping Zhang<sup>1,2</sup> <br><br></center>

<center><sup>1</sup> School of Communication and Information Engineering, Shanghai University, China<br>  
<sup>2</sup> Ryerson University, Toronto, Canada<br>
<sup>3</sup> JD AI Research, Beijing, China<br>
<sup>4</sup> Shanghai Conservatory of Music, China</center>  -->

<br>

- [Abstract](#abstract)
- [Overall Performance](#overall-performance)
    + [Samples of Different Systems](#samples-of-different-systems)
<!--     + [Additional experiment](#additional-experiment) -->
- [Ablation Study](#ablation-study)
    + [ES-V vs ES](#es-v-vs-es)
    + [ES-E1 vs ES](#es-e1-vs-es)
    + [Examples of Different Pitch Models](#examples-of-different-pitch-models)
<!-- - [Details of Vibrato Likeliness Labeling Model](#details-of-vibrato-likeliness-labeling-model) -->

## Abstract
-----------

 <div style="text-align: justify">This paper proposes an expressive singing voice synthesis system by introducing explicit vibrato modeling and latent energy representation. Vibrato is essential to the naturalness of synthesized sound, due to the inherent characteristics of human singing. Hence, a deep learning-based vibrato model is introduced in this paper to control the vibrato’s likeliness, rate, depth and phase in singing, where the vibrato likeliness represents the existence probability of vibrato and it would help improve the singing voice’s naturalness. Actually, there is no annotated label about vibrato likeliness in existing singing
corpus. We adopt a novel vibrato likeliness labeling method to label the vibrato likeliness automatically. Meanwhile, the power spectrogram of audio contains rich information that can improve the expressiveness of singing. An autoencoder-based latent energy bottleneck feature is proposed for expressive singing voice synthesis. Experimental results on the open dataset NUS48E show that both the vibrato modeling and the latent energy representation could significantly improve the expressiveness of singing voice. The audio samples are shown in the demo website1.</div>
 
<div align=center><img src="./image/overall.jpg"></div>

## Overall Performance
-----------

#### Samples of Different Systems
<div align=center><img src="./image/mos.jpg" width="60%"></div>
<br>

<table align="center">
  <thead>
    <tr>
      <th>/</th>
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
            <source src="audio/mos_demo_web/baseline/VKOW_20_JTAN_2.wav"></audio></td>
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
            <source src="audio/mos_demo_web/USVC/VKOW_20_JTAN_2.wav"></audio></td>
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
            <source src="audio/mos_demo_web/WGANSing/VKOW_20_JTAN_2.wav"></audio></td>
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
            <source src="audio/mos_demo_web/UCSVC/VKOW_20_JTAN_2.wav"></audio></td>
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
            <source src="audio/mos_demo_web/ours/VKOW_20_JTAN_2.wav"></audio></td>
    </tr>
   </tbody>
</table>

<p>
P.S. 1)<b>USVC</b>, the audios from this <a href="https://enk100.github.io/Unsupervised_Singing_Voice_Conversion/">link</a>; 
     2)<b>WGANSing</b>, where we retrained the model on the same training set as ExpressiveSing. The original web is <a href="https://pc2752.github.io/sing_synth_examples/">here</a>; 
     3)<b>UCSVC</b>, the audios from this <a href="https://singing-conversion.github.io/">link</a>.
</p>
<br>

<!-- #### Additional Experiment
<table align="center">
  <thead>
    <tr>
      <th>/</th>
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
<br> -->

##  Ablation Study
-----------
<div align=center><img src="./image/abtest_1.jpg" width="65%" ></div>

#### ES-V vs ES
<table align="center">
  <thead>
    <tr>
      <th>/</th>
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

#### ES-E1 vs ES 
<table align="center">
  <thead>
    <tr>
      <th>/</th>
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

<br>

#### Examples of Different Pitch Models 

<table><thead>
<tr>
<th style="text-align: center"> / </th>
<th style="text-align: center">Sample 1</th>
<th style="text-align: center">Sample 2</th>
<th style="text-align: center">Sample 3</th>
</tr></thead><tbody>
<tr>
<td nowrap="nowrap"><b>Parametric F0</b></td>
<td><audio controls="controls" ><source src="./audio/pitch_show_audio/output_Parametric_F0/ADIZ_01_7_output.wav" autoplay/>Your browser does not support the audio element.</audio><br> <div align=center><img src="./image/pitch_show_pic/output_Parametric_F0/ADIZ_01_7.jpg" width="100%" ></div> </td>
<td><audio controls="controls" ><source src="./audio/pitch_show_audio/output_Parametric_F0/ADIZ_18_1_output.wav" autoplay/>Your browser does not support the audio element.</audio><br> <div align=center><img src="./image/pitch_show_pic/output_Parametric_F0/ADIZ_18_1.jpg" width="100%" ></div> </td>
<td><audio controls="controls" ><source src="./audio/pitch_show_audio/output_Parametric_F0/PMAR_15_6_output_web.wav" autoplay/>Your browser does not support the audio element.</audio><div align=center><img src="./image/pitch_show_pic/output_Parametric_F0/PMAR_15_6.jpg" width="100%" ></div> </td>
</tr>
    
<tr>
<td nowrap="nowrap"><b>ES-V</b></td>
<td><audio controls="controls" ><source src="./audio/pitch_show_audio/output_whole_vibrato/ADIZ_01_7_output.wav" autoplay/>Your browser does not support the audio element.</audio><br> <div align=center><img src="./image/pitch_show_pic/output_whole_vibrato/ADIZ_01_7.jpg" width="100%" ></div> </td>
<td><audio controls="controls" ><source src="./audio/pitch_show_audio/output_whole_vibrato/ADIZ_18_1_output.wav" autoplay/>Your browser does not support the audio element.</audio><br> <div align=center><img src="./image/pitch_show_pic/output_whole_vibrato/ADIZ_18_1.jpg" width="100%" ></div> </td>
<td><audio controls="controls" ><source src="./audio/pitch_show_audio/output_whole_vibrato/PMAR_15_6_output_web.wav" autoplay/>Your browser does not support the audio element.</audio><div align=center><img src="./image/pitch_show_pic/output_whole_vibrato/PMAR_15_6.jpg" width="100%" ></div> </td>
</tr>
 
<tr>
<td nowrap="nowrap"><b>ES</b></td>
<td><audio controls="controls" ><source src="./audio/pitch_show_audio/output_our_pitch/ADIZ_01_7_output.wav" autoplay/>Your browser does not support the audio element.</audio><br> <div align=center><img src="./image/pitch_show_pic/output_our_pitch/ADIZ_01_7.jpg" width="100%" ></div> </td>
<td><audio controls="controls" ><source src="./audio/pitch_show_audio/output_our_pitch/ADIZ_18_1_output.wav" autoplay/>Your browser does not support the audio element.</audio><br> <div align=center><img src="./image/pitch_show_pic/output_our_pitch/ADIZ_18_1.jpg" width="100%" ></div> </td>
<td><audio controls="controls" ><source src="./audio/pitch_show_audio/output_our_pitch/PMAR_15_6_output_web.wav" autoplay/>Your browser does not support the audio element.</audio><div align=center><img src="./image/pitch_show_pic/output_our_pitch/PMAR_15_6.jpg" width="100%" ></div> </td>
</tr>

</tbody></table>

<br>

<!-- ## Details of Vibrato Likeliness Labeling Model
-----------
<img src="./image/pitch_likeliness.png" width="100%" >
<br>
During the training stage, the ground-truth pitch is extracted from the singing voice first. Secondly, the pitch value is convolved with a triangular window to remove vibrato,
and to get a smooth pitch trajectory. According to our observation, vibrato normally appears in notes with a longer duration. Hence, we select notes with durations longer than one second to add simulated vibrato in frame level. To simulate vibrato on the selected music notes, a random normalized vibrato extent in range 0 to 3 is generated and then multiplied with a sinusoid noise in 6 Hz. Then the synthesized vibrato is combined with the smoothed pitch trajectory to generate the final pitch trajectory with vibrato. Then frame-level labels (0 or 1) are obtained because we know which segment has vibrato. During the inference stage, the real pitches of audios in the singing corpus are fed into the vibrato labeling model. Then the vibrato likeliness can be predicted by the vibrato labeling model. -->
