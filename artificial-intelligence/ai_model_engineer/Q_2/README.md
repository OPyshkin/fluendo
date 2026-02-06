
# Pose Estimation for Padel Hits — Analytical Reasoning Test

## Context

You are evaluating a Deep Learning system designed to detect padel hits using **pose estimation** from video. The model predicts player keypoints and derives hit events (forehand, backhand, smash, volley, serve) from body and arm motion. The system is already trained and partially deployed, but several performance and reliability issues have appeared in real scenarios.

<div style="text-align: center;">
  <img src="../imagery/padel.jpg" alt="Padel" width="30%" style="display: inline-block; margin-right: 2%;">
</div>

### Assumptions:
- We want to reduce computational cost so the lighter the models, the better 

### Questions:
1. The model shows strong performance on validation data but fails on new matches recorded in different clubs with different camera heights and angles. Hit detection accuracy drops significantly.
<br>Explain the most likely root causes of this failure and describe how you would systematically investigate and isolate the problem.

2. After reviewing some samples, you discover that different annotators labeled keypoints slightly differently (especially wrists and elbows), and hit timestamps are sometimes shifted by a few frames.
<br>Analyze how inconsistent annotations affect both pose estimation and hit classification, how you would detect label-quality problems at scale and how you would decide whether to relabel, filter, or reweight parts of the dataset. Justify your decision criteria.

3. Smashes are rare in the dataset but very important for the product. The model often misses them while performing well on common hits.
<br>Without changing the model architecture, explain which dataset, training, and evaluation strategy changes you would consider. Here, the idea is to discuss tradeoffs and risks of each approach and how you would verify that improvements are real and not overfitting artifacts.

4. Two training runs with the same configuration produce noticeably different results. One model is stable but less accurate; another is more accurate but produces jittery keypoints and inconsistent hit timing.
<br>Provide a reasoning to decide which model is actually better for production. What additional tests, metrics, and scenario-based evaluations would you design to support the decision?

5. Which model would you propose for this application? Why?
