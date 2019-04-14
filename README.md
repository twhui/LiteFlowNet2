# LiteFlowNet2
This repository (<strong>https://github.com/twhui/LiteFlowNet2</strong>) is the offical release of <strong>LiteFlowNet2</strong> for my paper <a href="https://arxiv.org/abs/1903.07414.pdf"><strong>A Lightweight Optical Flow CNN - Revisiting Data Fidelity and Regularization</strong></a>. 

LiteFlowNet2, another lightweight convolutional network, is evolved from our earlier work in CVPR 2018 (<strong>https://github.com/twhui/LiteFlowNet</strong>) to better address the problem of optical flow estimation by improving flow accuracy and computation time. Comparing to our earlier work, LiteFlowNet2 improves the optical flow accuracy on Sintel clean pass by 24%, Sintel final pass by 8.9%, KITTI 2012 by 16.8%, and KITTI 2015 by 17.5%. Its runtime is 2.2 times faster!

</ul>
<table>
<thead>
<tr>
<th align="center"></th>
<th align="center">Sintel Clean Testing Set</th>
<th align="center">Sintel Final Testing Set</th>
<th align="center">KITTI12 Testing Set (Out-Noc)</th>
<th align="center">KITTI15 Testing Set (Fl-fg / Fl-all)</th>
<th align="center">Model Size (M)</th> 
<th align="center">Runtime* (ms) GTX 1080</th> 
</tr>
<tr>
<td align="center">FlowNet2 (CVPR17)</td>
<td align="center">4.16</td>
<td align="center">5.74</td>
<td align="center">4.82%</td>
<td align="center">8.75% / 10.41%</td>
<td align="center">162</td>
<td align="center">121</td>
</tr> 
<tr>
<td align="center">PWC-Net+</td>
<td align="center"><strong>3.45</strong></td>
<td align="center"><strong>4.60</strong></td>
<td align="center">3.36%</td>
<td align="center"><strong>7.88%</strong> / <strong>7.72%</strong></td>
<td align="center">8.75</td> 
<td align="center"><strong>40</strong></td>
</tr> 
<tr>
<td align="center"><strong>LiteFlowNet2</strong></td>
<td align="center"><strong>3.45</strong></td>
<td align="center">4.90</td>
<td align="center"><strong>2.72%</strong></td>
<td align="center"><strong>7.20%</strong> / <strong>7.74%</strong></td>
<td align="center"><strong>6.42</strong></td>
<td align="center"><strong>40</strong></td>
</tr>    
</tbody></table>

Note: *Runtime is averaged over 100 runs for a Sintel's image pair of size 1024 × 436. 

# License and Citation 
All code and other materials (including but not limited to the paper, figures, and tables) are provided for research purposes only and without any warranty. Any commercial use requires our consent. When using any parts of the code package or the paper (<i>A Lightweight Optical Flow CNN - Revisiting Data Fidelity and Regularization</i>) in your work, please cite the following paper:

<pre><code>@InProceedings{hui19liteflownet2,    
 author = {Tak-Wai Hui and Xiaoou Tang and Chen Change Loy},    
 title = {A {L}ightweight {O}ptical {F}low {CNN} - {R}evisiting {D}ata {F}idelity and {R}egularization}, 
 journal = {arXiv preprint arXiv:1903.07414},
 year = {2019},    
 url = {http://mmlab.ie.cuhk.edu.hk/projects/LiteFlowNet/} 
}</code></pre>

# We will release the trained models and codes soon.
