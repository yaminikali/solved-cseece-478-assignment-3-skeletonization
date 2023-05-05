Download Link: https://assignmentchef.com/product/solved-cse_ece-478-assignment-3-skeletonization
<br>
For <strong>skeletonization</strong>, the basic idea is to remove any pixel on the boundary of the foreground which has more than one foreground neighbor. But this needs to be done in such a way that removing the pixel does not split the connected component, to which the pixel belongs, into two.

Consider the following structuring elements:

Here, ∗ stands for <strong>don’t care</strong>; whether image pixel underneath is foreground or background. In morphological operations, note that a structuring element whose origin is placed on a pixel will be compared to the corresponding neighborhood and if they match, then the corresponding pixel in the output image is usually set to foreground.

In this case, suppose that we change the rule and set the pixel to background (i.e. to value 0). Suppose <em>S</em>(<em>θ</em>) stands for structuring element S rotated by angle <em>θ </em>degrees.

<em>I</em><sub>1 </sub>−→<em><sup>S </sup>I</em><sub>2 </sub>denote that <em>I</em><sub>2 </sub>is a result of applying structuring element <em>S </em>on image <em>I</em><sub>1</sub>. A single skeletonization pass is defined as:

<em>S</em><sup>1</sup>(0)                 <em>S</em><sup>2</sup>(0)                 <em>S</em><sup>1</sup>(90)                 <em>S</em><sup>2</sup>(90)                 <em>S</em><sup>1</sup>(180)                 <em>S</em><sup>2</sup>(180)                 <em>S</em><sup>1</sup>(270)                 <em>S</em><sup>2</sup>(270)

<h1><em>I</em><sub>1 </sub>−−−→ <em>I</em><sub>2 </sub>−−−→ <em>I</em><sub>3 </sub>−−−→ <em>I</em><sub>4 </sub>−−−→ <em>I</em><sub>5 </sub>−−−−→ <em>I</em><sub>6 </sub>−−−−→ <em>I</em><sub>7 </sub>−−−−→ <em>I</em><sub>8 </sub>−−−−→ <em>I</em><sub>9</sub></h1>

To obtain the skeleton, the operations defined by the above skeletonization pass need to be repeated until a particular structuring element pass leaves the image unchanged.

<ol>

 <li> Write code for the above skeletonization process and display the computed skeleton for the image thumb print.jpg. Note that the image will need to be binarized first ! You can use threshold or any other inbuilt function for binarization.</li>

 <li>Explain the role of structuring elements <em>S</em><sub>1</sub><em>,S</em><sub>2</sub>.</li>

 <li> By analyzing the outputs at the end of each skeletonization pass, explain why multiple passes are/may be required.</li>

 <li> Try out the skeletonization algorithm described above on jpg, butterfly.jpg and keyhole.jpg and comment on what you observe.</li>

</ol>




<ol start="2">

 <li>Find the organs of interest in the provided CT image jpg. The organs of interest are as shown below.</li>

</ol>

(a) Original kidney image                                                          (b) Isolated organs

Hint: Use thresholding and morphological operations.

Note: You need to implement the connected components for this question.

<ol start="3">

 <li> Read in the binary image jpg and write a script which uses the image as input and outputs a new image containing

  <ol>

   <li>only the coins touching the boundary of the image</li>

   <li>only the coins which overlap with each other</li>

   <li>only non-overlapping coins</li>

  </ol></li>

</ol>

Hint: You can use the previously implemented connected components function for this question.

<ol start="4">

 <li>Read in the binary image png and write a script which uses the image as input and uses morphological and logical operations to answer the questions below.

  <ol>

   <li>How many objects have one or more holes?</li>

   <li>How many square objects are in the image?</li>

   <li>Identify the square objects that have holes.</li>

   <li>Identify the circular objects that have no holes</li>

  </ol></li>

</ol>




Hint: You can use the previously implemented connected components function for this question.

The questions below pertain to connected components. In the questions below, assume 8-connectivity.

<ol>

 <li style="list-style-type: none;">

  <ol>

   <li>The image colourful text.png contains text characters in five different colors. Write a script which takes the image as input and outputs the number of components for each of the five colors. Note that the components may be non-letters (e.g. . and |).</li>

   <li> For jpeg and tamil.jpeg write a script which produces a binary image containing

    <ul>

     <li>Only those letters that enclose one empty region (e.g. examples of English letters containing a single empty region are – o,e,a)</li>

     <li>only those letters that enclose two empty regions (e.g. example letter from English – g, B)</li>

    </ul></li>

   <li> Given the label map of a scene,

    <ol>

     <li>How do you upscale the label map by factor k?</li>

     <li>How do you rotate the label map by <em>θ</em>?</li>

    </ol></li>

  </ol></li>

</ol>

The before/after label maps should look meaningful when visualized using <a href="https://scikit-image.org/docs/dev/api/skimage.color.html#skimage.color.label2rgb">label2rgb</a><a href="https://scikit-image.org/docs/dev/api/skimage.color.html#skimage.color.label2rgb">.</a>

<ol start="7">

 <li>Image rotation:

  <ol>

   <li>Write a function rotImage which rotates an input image about its center and takes the following parameters:

    <ul>

     <li>Input image</li>

     <li>Angle of rotation in degrees</li>

     <li>A boolean parameter, retain, such that,

      <ul>

       <li>If it is true, you retain the original dimensions of the input image and crop out all pixels that map to locations outside of these dimensions.</li>

       <li>If it is false, your output dimensions should accommodate the entire image (<strong>without cropping</strong>) after rotation.</li>

      </ul></li>

    </ul></li>

  </ol></li>

</ol>

<ol start="2">

 <li>Show outputs of a rectangular image of your choice with angle 30<sup>◦</sup>, 45<sup>◦</sup>, 90<sup>◦ </sup>and 2 other angles of your choice.</li>

</ol>