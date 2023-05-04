Download Link: https://assignmentchef.com/product/solved-cs524-homework-5-least-squares
<br>
<h1>Homework 5:</h1>

<ol>

 <li><strong>Spline tting. </strong>We are running a series of experiments to evaluate the properties of a new uorescent material. As we vary the intensity of the incident light, the material should uoresce dierent amounts. Unfortunately, the material isn’t perfectly uniform and our method for measuring uorescence is not very accurate. After testing 200 dierent intensities, we obtained the result below (also available in xy_dat a. csv). The intensities <em>x <sub>i </sub></em>and uorescences <em>y<sub>i </sub></em>are recorded in the rst and second columns of the data matrix, respectively.</li>

</ol>

<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2020/06/622.png?w=980&amp;ssl=1" class="lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2020/06/622.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>The material has interesting nonlinear properties, and we would like to characterize the relationship between intensity and uorescence by using an approximate model that agrees well with the trend of our experimental data. Although there is noise in the data, we know from physics that <em>the uorescence must be zero when the intensity is zero</em>. This fact must be reected in all of our models!

<ol>

 <li><strong>Polynomial t. </strong>Find the best cubic polynomial t to the data. In other words, look for a function of the form <em>y </em>= <em>a</em><sub>1</sub><em>x</em><sup>3 </sup>+ <em>a</em><sub>2</sub><em>x</em><sup>2 </sup>+ <em>a</em><sub>3</sub><em>x </em>+ <em>a</em><sub>4 </sub>that has the best possible agreement with the data. Remember that the model should have (exactly) zero uorescence when the intensity is zero! Include a plot of the data along with your best-t cubic on the same axes.</li>

 <li><strong>Spline t. </strong>Instead of using a single cubic polynomial, we will look for a t to the data using two quadratic polynomials. Specically, we want to nd coecients <em>p<sub>i </sub></em>and <em>q<sub>i </sub></em>so that our data is well modeled by the piecewise quadratic function:</li>

</ol>

<sup>( </sup><em>p</em><sub>1</sub><em>x</em><sup>2 </sup>+ <em>p</em><sub>2</sub><em>x </em>+ <em>p</em><sub>3            </sub>if 0       <em>x &lt; </em>4

<em>y </em>= <em>q</em><sub>1</sub><em>x</em><sup>2 </sup>+ <em>q</em><sub>2</sub><em>x </em>+ <em>q</em><sub>3 </sub>if 4 <em>x &lt; </em>10

These quadratic functions must be designed so that: as in the cubic model, there is zero uorescence when the intensity is zero.

both quadratic pieces have the same value at <em>x </em>= 4.

both quadratic pieces have the same slope at <em>x </em>= 4.

In other words, we are looking for a <em>smooth </em>piecewise quadratic. This is also known as a <em>spline </em>(this is just one type of spline, there are many other types). Include a plot of the data along with your best-t model.

<ol start="2">

 <li><strong>Voltage smoothing. </strong>We would like to send a sequence of voltage inputs to the manipulator arm of a robot. The desired signal is shown in the plot below (also available in vol t ages. csv).</li>

</ol>

Unfortunately, abrupt changes in voltage cause undue wear and tear on the motors over time, so we would like to create a new signal that is similar to the one above but with smoother transitions. If the voltages above are given by <em>v</em><sub>1</sub><em>;v</em><sub>2</sub><em>;:::;v</em><sub>200</sub>, one way to characterize smoothness is via the sum of squared dierences:

<em>R </em>(<em>v</em>) = (<em>v</em>2            <em>v</em>1)2 + (<em>v</em>3           <em>v</em>2)2 +          + (<em>v</em>200           <em>v</em>199)2

When <em>R </em>(<em>v</em>) is smaller, the voltage is smoother. Solve a regularized least squares problem that explores the tradeo between matching the desired signal perfectly and making the signal smooth. Include a plot comparing the original signal to a few dierent smoothed versions obtained using regularized least squares and with varying degrees of smoothness.