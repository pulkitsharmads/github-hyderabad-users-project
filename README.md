
# GitHub Hyderabad Users Analysis  

- How the data was scraped:  
  We used the GitHub REST API with Python to collect data about users in Hyderabad who have more than 50 followers. The data includes user profiles and metadata for up to 500 public repositories per user.  

- Interesting insight:  
  Surprisingly, repositories using Perl have the highest average star count, even though it is not a common language among these developers.  

- Recommendation for developers:  
  Developers should focus on building community engagement (followers) rather than simply creating many repositories, as higher followers significantly boost influence and visibility.  



 Project Overview  

This project uses the GitHub API to explore developer activity and repository usage patterns in Hyderabad. The analysis includes:
- User information such as name, company, bio, hireability status, and follower counts.
- Repository data including languages, stars, watchers, projects, wikis, and licenses.

The goal is to analyze trends like which programming languages are popular, which companies employ active developers, and how follower counts are affected by developer actions.  



 Files Included  

- `users.csv`: Contains data of users with more than 50 followers from Hyderabad.  
  Fields:  
  - `login`: User's GitHub login  
  - `name`: Full name  
  - `company`: Cleaned company names  
  - `location`: Hyderabad  
  - `email`: Email address (if available)  
  - `hireable`: Hireability status (`true`/`false`)  
  - `bio`: User’s bio  
  - `public_repos`: Number of public repositories  
  - `followers`: Number of followers  
  - `following`: Number of users followed  
  - `created_at`: Date the user joined GitHub  

- `repositories.csv`: Contains metadata of up to 500 public repositories per user.  
  Fields:  
  - `login`: Repository owner’s GitHub login  
  - `full_name`: Full name of the repository  
  - `created_at`: Date of repository creation  
  - `stargazers_count`: Number of stars  
  - `watchers_count`: Number of watchers  
  - `language`: Programming language used  
  - `has_projects`: Whether the repository has projects enabled (`true`/`false`)  
  - `has_wiki`: Whether the repository has a wiki (`true`/`false`)  
  - `license_name`: License type (if available)  



 How to Use This Project  

# 1. Clone the Repository  
Use the following command to clone the repository locally:  
```bash
git clone https://github.com/YOUR_USERNAME/github-hyderabad-users.git
cd github-hyderabad-users
```

# 2. Install Dependencies  
Install required Python packages using:  
```bash
pip install pandas numpy requests
```

# 3. Load and Explore the Data  
Use the following code to explore the data:

```python
import pandas as pd

# Load the datasets
users = pd.read_csv('users.csv')
repos = pd.read_csv('repositories.csv')

# Example 1: Top 5 users by followers
top_users = users.sort_values(by='followers', ascending=False).head(5)
print("Top 5 Users by Followers:")
print(top_users[['login', 'followers']])

# Example 2: Most popular programming language
most_popular_language = repos['language'].mode()[0]
print(f"Most Popular Language: {most_popular_language}")
```



 Project Insights  

1. Top Users by Followers:  
   The top 5 users by followers in Hyderabad are:  
   `iam-veeramalla, in28minutes, stacksimplify, thenaveensaggam, MadhavBahl`  

2. Most Popular Programming Language:  
   JavaScript is the most popular programming language among these developers.  

3. Surprising Finding:  
   Although not widely used, Perl repositories have the highest average star count, suggesting niche popularity.  

4. Language with Highest Average Stars:  
   Perl holds the highest average star count per repository.  
