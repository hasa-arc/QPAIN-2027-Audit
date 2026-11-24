# QPAIN-2027-Audit

# Title: Auditing the Clinical Readiness of AI Diagnostics in Low-Resource Settings: A Domain Shift and Edge-Deployment Study 

The Profile
The Deliverable: A 4-6 page IEEE double-blind conference paper.
The Core Thesis: "State-of-the-art AI models fail when deployed on out-of-distribution data from low-resource settings; however, lightweight models offer a necessary, albeit imperfect, compromise for edge deployment."
The Methodology: Train ResNet-50 (Heavy) on AbdomenAtlas. Test on Kaggle (Bangladesh). Train MobileNetV2 (Lightweight) on AbdomenAtlas. Test on Kaggle. Compare accuracy drop vs. latency gain.
The Deadline: December 20, 2026.

The 4-Phase Strategic Roadmap
Phase 1: The "Data Moat" (Days 1–5)
Strategic Goal: Lock down the data pipeline so it is repeatable and error-free.
Action: You are not writing PyTorch yet. You are doing Data Engineering.
The Task: Manually extract 150 healthy 2D slices from the AbdomenAtlas Mini dataset. Download and categorize 150 normal and 150 abnormal slices from the Kaggle dataset into the train/ and test/ folder structure.
The Milestone: You have a folder structure on your computer that PyTorch's ImageFolder can read without throwing an error.

Phase 2: The "Execution" (Days 6–10)
Strategic Goal: Generate the empirical numbers for your paper.
Action: Run the training and benchmarking.
The Task: You will run the ResNet and MobileNet scripts. You will intentionally overfit the training data (keep training until the model memorizes the AbdomenAtlas data). Then, you will run the test on the Kaggle data. You will record the accuracy drop and the CPU latency.
The Milestone: You have a .csv file or a notebook with the final numbers: ResNet Accuracy (Atlas vs. Kaggle), MobileNet Accuracy (Atlas vs. Kaggle), ResNet Latency, MobileNet Latency.

Phase 3: The "Narrative" (Days 11–18)
Strategic Goal: Translate numbers into an IEEE paper.
Action: Writing, not coding.
The Task:
Methodology: Explain the domain shift axes (contrast protocols, demographics in Bangladesh).
Results: Create the Pareto Frontier scatter plot (Latency on X, Accuracy on Y).
Discussion (The most important part): Why did the model fail? Is the accuracy drop due to Bangladeshi scanners having different noise profiles? Is the MobileNet compromise worth it for a rural clinic?
The Milestone: A complete 4-page draft.

Phase 4: The "Packaging" (Days 19–25)
Strategic Goal: Ensure compliance and submit without crashing the server.
Action: Mentor review, IEEE formatting, and double-blind scrubbing.
The Task: Remove your name, university, and GitHub links from the PDF. Format citations in IEEE style. Submit to QPAIN by December 18 (do not wait for the 20th).
The Milestone: Submission confirmation email.


Risk Management (The "What If" Scenarios)
Risk 1: The Kaggle Dataset doesn't download properly.
Mitigation: If Kaggle fails by Day 3, pivot immediately to another public dataset from a different country (e.g., a dataset from India or Africa). The narrative remains the same: High-resource training vs. Low-resource testing.
Risk 2: The accuracy on Kaggle is 50% (random guessing).
Mitigation: This is actually a success for your paper. If the heavy model completely fails (catastrophic forgetting/domain shift), it proves your thesis that these models are not ready for deployment.
Risk 3: MobileNet performs exactly the same as ResNet.
Mitigation: You can still publish the paper. You would argue that "given the equality in accuracy, MobileNet is the objectively superior choice for resource-constrained settings due to its lower latency."

🚦 The Immediate Next Step
Before you touch a single line of Python, we need to verify the data.
Download the AbdomenAtlas and Kaggle datasets. 
How to extract the 2D slices from the AbdomenAtlas 3D files?


