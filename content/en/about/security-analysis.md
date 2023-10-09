---
title: "Security Analysis Overview"
description: "Learn more about the Khronos Project"
---

# Security Analysis Overview

Time-samples that are at most w away from UTC are considered "good", whereas other samples are considered "malicious". Two scenarios are considered:

1. Less than 2/3 of the queried servers are under the attacker's control.
2. The attacker controls more than 2/3 of the queried servers.

The first scenario, where there are more than 1/3 good samples, consists of two cases:
* (i) there is at least one good sample in the set of samples not eliminated by Khronos (in the middle third of samples)
* (ii) there are no good samples in the remaining set of samples.

***

<div class="container-fluid">
  <div class="row">
    <div class="col-xl-6 col-lg-6 col-md-6">
	  <br>
      <p>In the first of these two cases (at least one good sample in the set of samples that was not eliminated by Khronos), the other remaining samples, including those provided by the attacker, must be close to a good sample (otherwise, the <a href="/about/how-khronos-works/">first condition of Khronos</a> is violated, and a new set of servers is chosen. This implies that the average of the remaining samples must be close to UTC.</p>
	</div>
    <div class="col-xl-6 col-lg-6 col-md-6">
	  <figure class="figure">
        <img src="/about/scenario1-case1.jpg" class="figure-img img-fluid">
	    <figcaption class="figure-caption">
          Scenario 1 Case 1 - at least one of the remaining samples is good.</a>
        </figcaption>
      </figure>
    </div>
  </div>
</div>
<hr>
<div class="container-fluid">
  <div class="row">
    <div class="col-xl-6 col-lg-6 col-md-6">
	  <br>
      <p>In the second sub-case (where there are no good samples in the set of remaining samples), since more than a third of the initial samples were good, both the (discarded) third lowest-value samples and the (discarded) third highest-value samples must each contain a good sample. Hence, all the remaining samples are bounded from both above and below by good samples, and so is their average value, implying that this value is close to UTC.</p>
	</div>
    <div class="col-xl-6 col-lg-6 col-md-6">
	  <figure class="figure">
        <img src="/about/scenario1-case2.jpg" class="figure-img img-fluid">
	    <figcaption class="figure-caption">
          Scenario 1 Case 2 - non of the remaining samples is good.</a>
        </figcaption>
      </figure>
    </div>
  </div>
</div>
<hr>
<div class="container-fluid">
  <div class="row">
    <div class="col-xl-6 col-lg-6 col-md-6">
	  <br>
      <p>In the second scenario, where the attacker controls more than 2/3 of the queried servers, the worst possibility for the client is that all remaining samples are malicious (i.e., more than w away from UTC). However, as proved in <a href="/downloads/ndss18-final231.pdf">Preventing (Network) Time Travel with Khronos</a>, the probability of this scenario is extremely low even if the attacker controls a large fraction (e.g., 1/4) of the n servers in the local Khronos pool. Therefore, the probability that the attacker repeatedly reaches this scenario decreases exponentially, rendering the probability of a significant time shift negligible. We can express the improvement ratio of Khronos over NTPv4 by the ratios of their single shift probabilities.</p>
	</div>
    <div class="col-xl-6 col-lg-6 col-md-6">
	  <figure class="figure">
        <img src="/about/case2.jpg" class="figure-img img-fluid">
	    <figcaption class="figure-caption">
          Case 2 - all surviving samples are malicious.</a>
        </figcaption>
      </figure>
    </div>
  </div>
</div>


***