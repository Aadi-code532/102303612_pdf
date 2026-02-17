🌫️ Personalized Air Quality Distribution Modeling using Roll-Based Non-Linear Transformation

This project implements a Roll-Number-Parameterized Non-Linear Transformation Model to learn the parameters of a Gaussian Probability Density Function (PDF) from real-world air quality data.

The transformation is uniquely generated using:

🎓 Roll Number: 102303612

The dataset used is the India Air Quality Dataset, with NO₂ concentration selected as the feature for modeling.

📂 Dataset

Source: Kaggle – India Air Quality Data

Feature Used: NO2

File Required: data.csv

⚠ Ensure data.csv is placed in the same directory before running the notebook.

🔢 Roll-Based Parameter Calculation

Given:

𝑟
=
102303612
r=102303612

We compute:

𝑎
𝑟
=
0.05
×
(
𝑟
 
m
o
d
 
7
)
a
r
	​

=0.05×(rmod7)
𝑏
𝑟
=
0.3
×
(
(
𝑟
 
m
o
d
 
5
)
+
1
)
b
r
	​

=0.3×((rmod5)+1)

For r = 102303612:

𝑟
 
m
o
d
 
7
=
6
rmod7=6

𝑟
 
m
o
d
 
5
=
2
rmod5=2

Therefore:

𝑎
𝑟
=
0.30
a
r
	​

=0.30
𝑏
𝑟
=
0.90
b
r
	​

=0.90
🔄 Non-Linear Transformation

Each NO₂ value 
𝑥
x is transformed as:

𝑧
=
𝑥
+
0.30
sin
⁡
(
0.90
𝑥
)
z=x+0.30sin(0.90x)

This ensures the model is personalized and unique to the roll number.

💻 Code Snippet
r = 102303612

a_r = 0.05 * (r % 7)
b_r = 0.3 * ((r % 5) + 1)

z = x + a_r * np.sin(b_r * x)

📈 Gaussian PDF Learning

The transformed data 
𝑧
z is modeled as:

𝑝
^
(
𝑧
)
=
𝑐
⋅
𝑒
−
𝜆
(
𝑧
−
𝜇
)
2
p
^
	​

(z)=c⋅e
−λ(z−μ)
2

Using Maximum Likelihood Estimation (MLE):

𝜇
=
mean
(
𝑧
)
μ=mean(z)

𝜎
2
=
variance
(
𝑧
)
σ
2
=variance(z)

𝜆
=
1
2
𝜎
2
λ=
2σ
2
1
	​


𝑐
=
1
2
𝜋
𝜎
2
c=
2πσ
2
	​

1
	​


📊 Output

✔ Roll-based transformation
✔ Gaussian parameter estimation
✔ Histogram visualization
✔ Fitted PDF overlay
✔ Final learned probability model

🛠 Technologies Used

Python 3

NumPy

Pandas

Matplotlib

Google Colab

🚀 How to Run

Clone the repository

Place data.csv inside the project directory

Open in Google Colab / Jupyter

Run all cells

If you want, I can suggest 3–4 more high-level research-style names that sound even stronger for resume or LinkedIn 🚀
