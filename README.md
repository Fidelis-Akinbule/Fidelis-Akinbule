# Hi there, I'm Fidelis Akinbule 👋

<div align="center">

### Data Scientist & ML Engineer | Nigerian fintech and telecom analytics

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/fidelis-akinbule/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Fidelis-Akinbule)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:Fakinbule@gmail.com)

</div>

---

## About

I'm a data scientist and ML engineer in Lagos, with a BSc in Industrial Chemistry and no formal computer science training. I taught myself Python, SQL, and machine learning by building things across telecom analytics, agricultural forecasting, credit risk, fraud detection, and algorithmic trading.

NigeriaRGI and NigeriaAgriScope are the two I'd lead with, and the two closest to where I want to keep working: both grounded in real published benchmarks (NCC quality-of-service reports, NBS population data, FAOSTAT crop records) instead of a generic template with the country's name swapped in. These are specific Nigerian problems, not generic ones wearing a Nigerian label.

I build with AI tools as a normal part of my workflow, and I document that rather than pretending every line came from nowhere. I won't put a number in this README that I can't defend, unprompted, in an interview.

---

## Tech stack

<div align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-orange?style=flat)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)
![SHAP](https://img.shields.io/badge/SHAP-blue?style=flat)
![Prophet](https://img.shields.io/badge/Prophet-4285F4?style=flat)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)

</div>

---

## Featured projects

### NigeriaRGI: Regional Growth Intelligence Platform
[Live dashboard](https://nigeriargi-hv7avwbkxycrxkzvc4irsm.streamlit.app/) · [Code](https://github.com/Fidelis-Akinbule/NigeriaRGI)

I built this to cover the full toolkit a Regional BI & Analytics lead at a Nigerian telecom operator would need: an automated data pipeline, twelve SQL queries spanning revenue, subscriber, network-quality, and site-economics analytics, a five-page dashboard, two predictive models, and a go-to-market scoring engine, all running on 3,690 rows across 41 LGAs in 12 states over 90 days. (The underlying LGA-day data is simulated and calibrated against real NCC quality-of-service reports, NBS population figures, and post-2025 MTN/Airtel ARPU data, rather than pulled from a live operator system I don't have access to.)

**Results**
- Churn model (logistic regression): 0.989 AUC and 96% recall on the at-risk class, built from week-over-week subscriber and ARPU movement plus network signals like MOS score and drop-call rate
- Site profitability model (gradient boosting): R² 0.83, MAE ₦1.34M per site per day, so a flagged site comes with a number attached to it instead of a guess
- GTM scoring across all 41 LGAs, weighted on population whitespace, income, POI density, penetration gap, and site economics: Sagamu, Nnewi North, and Ogbomoso lead on unmet demand; Lekki and Ikeja lead on income and footfall

**Stack:** Python, SQLite, Pandas, Scikit-learn, Streamlit, Plotly, Power BI (DAX)

### NigeriaAgriScope
[Live dashboard](https://nigeriaagriscope-yd7pxpdaacoupjsgylhj5f.streamlit.app) · [Code](https://github.com/Fidelis-Akinbule/NigeriaAgriScope)

Nigeria grows more cassava than any other country and still gets 1.2 tonnes of maize per hectare against a global average of 5.8. It comes down to information: smallholder farmers don't have reliable data on when to plant or how much fertilizer pays off, and the resulting yield gap runs an estimated ₦2.3 trillion a year. This pulls 24 years of real FAOSTAT, NASA POWER, World Bank, and USDA data across 7 crops and 6 geopolitical zones to see how much of that gap a model can close.

**Results**
- Yield model (XGBoost): R² 0.991 on next-year yield, MAE 2,900 hg/ha on a 2019 to 2023 holdout set. Lagged yield and rolling 3-year rainfall matter more than any single season's inputs
- Fertilizer response curves across all 42 crop-zone pairs put North Central yam at the top of the list: +30,538 hg/ha available at the optimal 172 kg/ha application rate, the largest single opportunity in the dataset
- South South oil palm farmers apply 9.1 kg/ha of fertilizer against a computed optimum of 95 kg/ha, a tenfold gap worth an estimated +153 hg/ha in unrealized yield
- Rainfall onset in the South East and North West posted a 1.00 reliability score across all 24 years, so for those two zones the planting calendar alone removes timing risk

Prophet extends production forecasts for cassava, oil palm, and maize out to 2026 for supply-chain planning.

**Stack:** Python, XGBoost, Prophet, SHAP, Pandas, Streamlit, SQLite, Power BI

### Credit Risk Scoring Model
[Code](https://github.com/Fidelis-Akinbule/credit_risk_model)

An end-to-end default prediction system that converts model output into industry-standard 300 to 900 credit scores. It reaches 86.75% AUC, calibrated to within 0.00001% of perfect, and catches 84.2% of actual defaults within the riskiest 30% of applicants scored, the number that matters if you're deciding where to spend review time. SHAP attributes 59% of that explanatory power to engineered delinquency features. Run against a full loan portfolio, it holds the approval rate at 95.1% while cutting defaults by 25.1%, a $3.45M annual reduction in losses. Built to Basel III and IFRS 9 documentation standards throughout.

The part I'm gladdest I built: a distribution-shift check that caught a 60.7% jump in test-set risk before deployment, catching an estimated $162M in losses a static model would have walked straight into.

**Stack:** Python, XGBoost, SHAP, Scikit-learn, Streamlit

### Fraud Detection Pipeline
[Code](https://github.com/Fidelis-Akinbule/ComprehesiveFraudDetectionPipeline)

A fraud detection pipeline that runs Random Forest, XGBoost, and Logistic Regression against the same transaction data, with automated feature engineering and a checkpoint system so a crashed run doesn't mean starting over from scratch. It reaches 95%+ detection accuracy, and the Streamlit dashboard exports a PDF report that a compliance reviewer can read without touching a line of code.

**Stack:** Python, Scikit-learn, Pandas, Streamlit

### Algorithmic Trading Bot (Reinforcement Learning)
[Code](https://github.com/Fidelis-Akinbule/ict-mmm_bot)

A PPO agent trading Inner Circle Trader (ICT) market structure concepts (order blocks, fair value gaps, break of structure and change of character) with automated risk management and dynamic position sizing. Signal latency runs under 100ms. It's aiming for a Sharpe ratio above 1.5, max drawdown under 10%, and a win rate above 55%, benchmarks it's still being tuned against rather than settled results.

**Stack:** Python, Stable-Baselines3 (PPO), MetaTrader 5, NumPy

### Water Infrastructure Analytics
[Code](https://github.com/Fidelis-Akinbule/Majidogo_project)

SQL-based operational analytics on a rural water infrastructure dataset: matching field employees to water sources more efficiently, flagging peak queue-time patterns, and ranking broken infrastructure by repair priority through cost-benefit analysis.

**Stack:** MySQL, SQL

### SMS Spam Classifier
[Code](https://github.com/Fidelis-Akinbule/Simple_SMS_Spam_Detection_Model)

A small TF-IDF and Naive Bayes classifier with a Streamlit front end. Naive Bayes on bag-of-words is about as simple as text classification gets, so the value here is in the clean, real-time interface built around it.

**Stack:** Python, Scikit-learn, TF-IDF, Naive Bayes, Streamlit

---

## GitHub activity

<div align="center">

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=Fidelis-Akinbule&show_icons=true&theme=radical&hide_border=true&count_private=true)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=Fidelis-Akinbule&layout=compact&theme=radical&hide_border=true&langs_count=6)

![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=Fidelis-Akinbule&theme=radical&hide_border=true)

</div>

---

## Open to

Regional BI & analytics and risk analyst roles at Nigerian telecom operators, fintechs, and microfinance banks. Also open to data strategy or ML consulting work.

[Email](mailto:Fakinbule@gmail.com) · [LinkedIn](https://www.linkedin.com/in/fidelis-akinbule/) · [GitHub](https://github.com/Fidelis-Akinbule)

I usually reply within a day or two.

---

<div align="center">

If any of these projects are useful to you, a star helps other people find them.

![Profile Views](https://komarev.com/ghpvc/?username=Fidelis-Akinbule&color=blueviolet&style=flat-square)

</div>
