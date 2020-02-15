# LiteFlowNet2
This repository (<strong>https://github.com/twhui/LiteFlowNet2</strong>) is the offical release of <strong>LiteFlowNet2</strong> for my paper <a href="https://arxiv.org/abs/1903.07414.pdf"><strong>A Lightweight Optical Flow CNN - Revisiting Data Fidelity and Regularization</strong></a> in TPAMI 2020. 

LiteFlowNet2, another lightweight convolutional network, is evolved from our earlier work in CVPR 2018 (<strong>https://github.com/twhui/LiteFlowNet</strong>) to better address the problem of optical flow estimation by improving flow accuracy and computation time. Comparing to our earlier work, LiteFlowNet2 improves the optical flow accuracy on Sintel clean pass by 23.3%, Sintel final pass by 12.8%, KITTI 2012 by 19.6%, and KITTI 2015 by 18.8%. Its runtime is 2.2 times faster!

</ul>
<table>
<thead>
<tr>
<th align="center"></th>
<th align="center">Sintel Clean Testing Set</th>
<th align="center">Sintel Final Testing Set</th>
<th align="center">KITTI12 Testing Set (Out-Noc)</th>
<th align="center">KITTI15 Testing Set (Fl-all)</th>
<th align="center">Model Size (M)</th> 
<th align="center">Runtime* (ms) GTX 1080</th> 
</tr>
<tr>
<td align="center">FlowNet2 (CVPR17)</td>
<td align="center">4.16</td>
<td align="center">5.74</td>
<td align="center">4.82%</td>
<td align="center">10.41%</td>
<td align="center">162</td>
<td align="center">121</td>
</tr> 
<tr>
<td align="center">PWC-Net+</td>
<td align="center"><strong>3.45</strong></td>
<td align="center"><strong>4.60</strong></td>
<td align="center">3.36%</td>
<td align="center">7.72%
<td align="center">8.75</td> 
<td align="center"><strong>40</strong></td>
</tr> 
<tr>
<td align="center"><strong>LiteFlowNet2 (TPAMI)</strong></td>
<td align="center"><strong>3.48</strong></td>
<td align="center"><strong>4.69</strong></td>
<td align="center"><strong>2.63%</strong></td>
<td align="center"><strong>7.62%</strong></td>
<td align="center"><strong>6.42</strong></td>
<td align="center"><strong>40</strong></td>
</tr>    
</tbody></table>

Note: *Runtime is averaged over 100 runs for a Sintel's image pair of size 1024 × 436. 

# License and Citation 
This software and associated documentation files (the "Software"), and the research paper (A Lightweight Optical Flow CNN - Revisiting Data Fidelity and Regularization) including but not limited to the figures, and tables (the "Paper") are provided for research purposes only and without any warranty. Any commercial use requires my consent. When using any parts of the Software or the Paper in your work, please cite the following paper:

<pre><code>@InProceedings{hui20liteflownet2,    
 author = {Tak-Wai Hui and Xiaoou Tang and Chen Change Loy},    
 title = {A {L}ightweight {O}ptical {F}low {CNN} - {R}evisiting {D}ata {F}idelity and {R}egularization}, 
 journal = {IEEE Transactions on Pattern Analysis and Machine Intelligence},
 year = {2020},    
 url = {http://mmlab.ie.cuhk.edu.hk/projects/LiteFlowNet/} 
}</code></pre>

<pre><code>@InProceedings{hui18liteflownet,    
 author = {Tak-Wai Hui and Xiaoou Tang and Chen Change Loy},    
 title = {LiteFlowNet: A Lightweight Convolutional Neural Network for Optical Flow Estimation},    
 booktitle  = {Proceedings of IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},    
 year = {2018},    
 pages = {8981--8989},
 url = {http://mmlab.ie.cuhk.edu.hk/projects/LiteFlowNet/} 
}</code></pre>

# Prerequisite and Compiling
LiteFlowNet2 uses the same Caffe package as LiteFlowNet. Please refer to the details in <a href="https://github.com/twhui/LiteFlowNet#Prerequisite"> LiteFlowNet GitHub repository</a>.

# Training
Please refer to the training steps in <a href="https://github.com/twhui/LiteFlowNet#Training"> LiteFlowNet GitHub repository</a> and adopt the training prtocols in <a href="https://arxiv.org/abs/1903.07414.pdf"> LiteFlowNet2 paper</a>.

# Trained models	
The trained models (<code>LiteFlowNet2-ft-sintel</code>, <code>LiteFlowNet2-ft-kitti</code>) are available in the folder <code>/models/trained</code>. Untar the files to the same folder before you use it.

<code>LiteFlowNet2-ft-sintel</code>: Model used for Sintel benchmark.

<code>LiteFlowNet2-ft-kitti</code>: Model used for KITTI benchmark.

# Testing 
1. Open the testing folder
<pre><code>$ cd LiteFlowNet2/models/testing</pre></code>

2. Create a soft link in the folder <code>/testing</code>
<pre><code>$ ln -s ../../build/tools bin</code></pre>

3. Replace <code>MODE</code> in <code>./test_MODE.py</code> to <code>batch</code> if all the images has the same resolution (e.g. Sintel dataset), otherwise replace it to <code>iter</code> (e.g. KITTI dataset).

4. Replace <code>MODEL</code> in line 10 (<code>cnn_model = 'MODEL'</code>) of <code>test_MODE.py</code> to one of the trained models (e.g. <code>LiteFlowNet2-ft-sintel</code>).

5. Run the testing script. Flow fields (<code>MODEL</code>-0000000.flo, <code>MODEL</code>-0000001.flo, ... etc) are stored in the folder <code>/testing/results</code> having the same order as the image pair sequence. 
<pre><code>$ test_MODE.py img1_pathList.txt img2_pathList.txt results</code></pre>
