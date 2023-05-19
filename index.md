# MC-SpEx: Towards Effective Speaker Extraction with Multi-Scale Interfusion and Conditional Speaker Modulation

### *Jun Chen, Wei Rao, Zilin Wang, Jiuxin Lin, Yukai Ju, Shulin He, Yannan Wang, Zhiyong Wu*

<h2 id = "1">Abstract</h2>

The previous SpEx+ has yielded outstanding performance in speaker extraction and attracted much attention. However, it still encounters inadequate utilization of multi-scale information and speaker embedding. To this end, this paper proposes a new effective speaker extraction system with multi-scale interfusion and conditional speaker modulation (ConSM), which is called MC-SpEx. First of all, we design the weight-share multi-scale fusers (ScaleFusers) for efficiently leveraging multi-scale information as well as ensuring consistency of the model's feature space. Then, to consider different scale information while generating masks, the multi-scale interactive mask generator (ScaleInterMG) is presented. Moreover, we introduce ConSM module to fully exploit speaker embedding in the speech extractor. Experimental results on the Libri2Mix dataset demonstrate the effectiveness of our improvements and the state-of-the-art performance of our proposed MC-SpEx.


<center>
    <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
	<script id="MathJax-script" async
        src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>
    <img style="zoom: 55%; " 
    src="./data/fig/total_arch_new.jpg">
    <br>
    <div class="caption" style="max-width: 600px;"> Fig.1: The overall diagram of the MC-SpEx. The dotted border represents the module with shared weights. The "\(\otimes\)" means element-wise multiplication. The “SI-SDR Loss" and ”CE Loss" refer to the scale-invariant signal-to-distortion ratio loss and cross-entropy loss in multi-task learning.
    </div>
</center>



## Cases

We compare the performance of our proposed MC-SpEx and SpEx on Libri2Mix test set. In this test set. The cases are divided into **"different gender"** and **"same gender"**, where "same gender" is further classified as **"female mixed with female"** and **"male mixed with male"**.

<h3 id = "3">Different Gender</h3>

#### case 1

|                            case 1                            |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Mixture** <br><audio controls><source src="./data/diff_gen/case1/mix.wav" type="audio/wav" >Your browser does not support the audio element.</audio> | **SpEx+** <br>  <audio controls><source src="./data/diff_gen/case1/spex_plus.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/diff_gen/case1/mix.jpg" alt="mixture" width="100%"/> | <img src="./data/diff_gen/case1/spex_plus.jpg" alt="baseline" width="100%"/> |
| **MC-SpEx**<br>  <audio controls><source src="./data/diff_gen/case1/ours.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Ground truth** <br> <audio controls><source src="./data/diff_gen/case1/gt.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/diff_gen/case1/ours.jpg" alt="proposed" width="100%" /> | <img src="./data/diff_gen/case1/gt.jpg" alt="ground truth" width="100%"/> |



#### case 2

|                            case 2                            |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Mixture** <br><audio controls><source src="./data/diff_gen/case2/mix.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **SpEx+** <br>  <audio controls><source src="./data/diff_gen/case2/spex_plus.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/diff_gen/case2/mix.jpg" alt="mixture" width="100%" /> | <img src="./data/diff_gen/case2/spex_plus.jpg" alt="baseline" width="100%" /> |
| **MC-SpEx**<br>  <audio controls><source src="./data/diff_gen/case2/ours.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Ground truth** <br> <audio controls><source src="./data/diff_gen/case2/gt.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/diff_gen/case2/ours.jpg" alt="proposed" width="100%" /> | <img src="./data/diff_gen/case2/gt.jpg" alt="ground truth" width="100%" /> |



<h3 id = "3"> Same Gender</h3>

<h4 id = "4">Female mixed with female</h4>

|                   Female mixed with female                   |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Mixture**  <br/><audio controls><source src="./data/same_gen/female_female/mix.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **SpEx+**   <br/><audio controls><source src="./data/same_gen/female_female/spex_plus.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/same_gen/female_female/mix.jpg" alt="mixture" width="100%" /> | <img src="./data/same_gen/female_female/spex_plus.jpg" alt="baseline" width="100%" /> |
| **MC-SpEx**  <br/><audio controls><source src="./data/same_gen/female_female/ours.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Ground truth**  <br/><audio controls><source src="./data/same_gen/female_female/gt.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/same_gen/female_female/ours.jpg" alt="proposed" width="100%" /> | <img src="./data/same_gen/female_female/gt.jpg" alt="ground truth" width="100%" /> |



<h4 id = "3">Male mixed with male</h4>

|                     Male mixed with male                     |                                                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| **Mixture**  <br/><audio controls><source src="./data/same_gen/male_male/mix.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **SpEx+**   <br/><audio controls><source src="./data/same_gen/male_male/spex_plus.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/same_gen/male_male/mix.jpg" alt="mixture" width="100%" /> | <img src="./data/same_gen/male_male/spex_plus.jpg" alt="baseline" width="100%" /> |
| **MC-SpEx**  <br/><audio controls><source src="./data/same_gen/male_male/ours.wav" type="audio/wav">Your browser does not support the audio element.</audio> | **Ground truth**  <br/><audio controls><source src="./data/same_gen/male_male/gt.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| <img src="./data/same_gen/male_male/ours.jpg" alt="proposed" width="100%" /> | <img src="./data/same_gen/male_male/gt.jpg" alt="ground truth" width="100%" /> |
