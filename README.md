## 📊 Kaggle-Notebooks Repository

🔗 **My Kaggle Profile:** https://www.kaggle.com/lukhilaksh

### 📂 Repository Structure

- **Kaggle-Notebooks**
  - README.md

  - **Bi Intro**
    - bi.csvclass Solution:
    def longestRepeating(self, s, queryCharacters, queryIndices):
        n = len(s)

       
        tree = [None] * (4 * n)

        def merge(a, b):
            if a is None:
                return b
            if b is None:
                return a

            lc1, rc1, pre1, suf1, best1, len1 = a
            lc2, rc2, pre2, suf2, best2, len2 = b

            prefix = pre1
            if pre1 == len1 and rc1 == lc2:
                prefix = len1 + pre2

            suffix = suf2
            if suf2 == len2 and rc1 == lc2:
                suffix = len2 + suf1

            best = max(best1, best2)

            if rc1 == lc2:
                best = max(best, suf1 + pre2)

            return (
                lc1,
                rc2,
                prefix,
                suffix,
                best,
                len1 + len2
            )

        def build(node, left, right):
            if left == right:
                c = s[left]
                tree[node] = (c, c, 1, 1, 1, 1)
                return

            mid = (left + right) // 2

            build(node * 2, left, mid)
            build(node * 2 + 1, mid + 1, right)

            tree[node] = merge(
                tree[node * 2],
                tree[node * 2 + 1]
            )

        def update(node, left, right, idx, char):
            if left == right:
                tree[node] = (char, char, 1, 1, 1, 1)
                return

            mid = (left + right) // 2

            if idx <= mid:
                update(node * 2, left, mid, idx, char)
            else:
                update(node * 2 + 1, mid + 1, right, idx, char)

            tree[node] = merge(
                tree[node * 2],
                tree[node * 2 + 1]
            )

        build(1, 0, n - 1)

        ans = []

        for char, idx in zip(queryCharacters, queryIndices):
            update(1, 0, n - 1, idx, char)
            ans.append(tree[1][4])

        return ans
    - Bi_Intro.ipynb
    - Bi_Intro-Coclass Solution:
    def longestRepeating(self, s, queryCharacters, queryIndices):
        n = len(s)

       
        tree = [None] * (4 * n)

        def merge(a, b):
            if a is None:
                return b
            if b is None:
                return a

            lc1, rc1, pre1, suf1, best1, len1 = a
            lc2, rc2, pre2, suf2, best2, len2 = b

            prefix = pre1
            if pre1 == len1 and rc1 == lc2:
                prefix = len1 + pre2

            suffix = suf2
            if suf2 == len2 and rc1 == lc2:
                suffix = len2 + suf1

            best = max(best1, best2)

            if rc1 == lc2:
                best = max(best, suf1 + pre2)

            return (
                lc1,
                rc2,
                prefix,
                suffix,
                best,
                len1 + len2
            )

        def build(node, left, right):
            if left == right:
                c = s[left]
                tree[node] = (c, c, 1, 1, 1, 1)
                return

            mid = (left + right) // 2

            build(node * 2, left, mid)
            build(node * 2 + 1, mid + 1, right)

            tree[node] = merge(
                tree[node * 2],
                tree[node * 2 + 1]
            )

        def update(node, left, right, idx, char):
            if left == right:
                tree[node] = (char, char, 1, 1, 1, 1)
                return

            mid = (left + right) // 2

            if idx <= mid:
                update(node * 2, left, mid, idx, char)
            else:
                update(node * 2 + 1, mid + 1, right, idx, char)

            tree[node] = merge(
                tree[node * 2],
                tree[node * 2 + 1]
            )

        build(1, 0, n - 1)

        ans = []

        for char, idx in zip(queryCharacters, queryIndices):
            update(1, 0, n - 1, idx, char)
            ans.append(tree[1][4])

        return anspy1.ipynb

  - **Bihar Polls 2025 Results**
    - bihar-polls-multilinear-100-accurecy-prediction.ipynb
    - bihar_election_results.csv

  - **Bookstore Financial**
    - bookstore-inventory-eda.ipynb
    - bookstore_inventory.csv

  - **Car Price**
    - car_price.ipynb
    - car_price_dataset_medium.csv

  - **Coffee Sales**
    - Coffe_sales.ipynb
    - Coffe_sales.csv

  - **College Exam Result**
    - college-exam-result-eda.ipynb
    - AI_Data.csv

  - **Crocodile Species**
    - crocodile_Analysis.ipynb
    - crocodile_dataset.csv

  - **Demon Slayer**
    - Demon_Slayer_Character_Analysis.ipynb
    - Demon Slayer.csv

  - **Diabetes and LifeStyle**
    - Diabetes_and_LifeStyle_Dataset.ipynb
    - Diabetes_and_LifeStyle_Dataset.csv

  - **EAFC26 Player**
    - eafc-all-player-eda.ipynb
    - EAFC26.csv

  - **Ecommerce 10000**
    - ecommerce-eda.ipynb
    - ecommerce_10000.csv

  - **Ecommerce Customer Behavior**
    - customer behavior.ipynb
    - ecommerce_customer_churn_dataset.csv

  - **Employee Salary**
    - employee salary.ipynb
    - employee_salary_dataset.csv

  - **Exam Score**
    - exam-score-86-beats.ipynb
    - Exam_Score_Prediction.csv

  - **Food Nutrition**
    - Food Nutrition.ipynb
    - Food_Nutrition_Dataset.csv

  - **Global Gender Equality**
    - global gender data.ipynbw
    - combined_global_gender_data_20251123.csv

  - **Global House Purchase**
    - Global_House_Purchase.ipynb

  - **Global Population**
    - global_population.ipynb
    - global_population_stats_2024.csv

  - **GTA V**
    - GTA Vice City.ipynb
    - GTA Vice_City.csv

  - **Instax Sales Transaction**
    - sales-transaction-99-model-beats.ipynb
    - instax_sales_transaction_data.csv

  - **Loan Eligibility Prediction**
    - Loan Eligibility Prediction.ipynb
    - Loan Eligibility Prediction.csv

  - **Medical Insurance Cost**
    - insurance.ipynb
    - insurance.csv

  - **Music Hits Youtube**
    - youtube-music-eda.ipynb
    - youtube-top-100-songs-2025.csv

  - **Phone Call**
    - User Call Behaviour.ipynb
    - categories.csv
    - walsoft_semi_categorized_phone_dataset.csv

  - **Shopping Behavior Updated**
    - Shopping Behavior Eda.ipynb
    - shopping_behavior_updated.csv

  - **Shopping Behaviour**
    - shopping-behaviors-eda.ipynb
    - shopping_behavior_updated.csv

  - **Social Media Advertising Response**
    - Social_Network_Ads.csv

  - **Steam**
    - Steam.ipynb
    - all_data.csv

  - **Student Class**
    - students_class10.ipynb
    - students_class10_basic_dataset.xlsx

  - **Student Performance**
    - student-performance-eda.ipynb
    - StudentPerformance.csv

  - **Urban Solar ROI**
    - solar-viability-prediction-95-90-accuracy.ipynb
    - solar_energy_worldwide.csv

  - **Viral Shorts**
    - Viral_shorts.ipynb
    - viral_shorts_reels_performance_dataset.csv

  - **Wine Quality**
    - wine-quality-multilinear-regression.ipynb
    - WineQT.csv

  - **World Smartphone Market**
    - Global_mobile_prices.ipynb
    - Global_Mobile_Prices_2025_Extended.csv

  - **World Top Restaurants**
    - World Top Resturants.ipynb
    - world_top_restaurants_dataset.csv
