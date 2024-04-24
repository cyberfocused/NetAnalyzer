# NetAnalyzer

import requests

def create_github_repo(repo_name, token):
    url = 'https://api.github.com/cyberfocused/NetAnalyzer'
    headers = {
        'Authorization': f'token {token}',
        'Accept': 'application/vnd.github.v3+json'
    }
    payload = {
        'name': NetAnalyzer,
        'auto_init': True  # Initializes the repository with a README
    }
    
    response = requests.post(url, headers=headers, json=payload)
    
    if response.status_code == 201:
        print(f"Repository '{NetAnalyzer}' created successfully.")
        return True
    else:
        print(f"Failed to create repository. Status code: {response.status_code}")
        print(response.json())
        return False

def main():
    repo_name = input("NetAnalyzer: ")
    token = input("Enter your GitHub personal access token: ")

    if create_github_repo(repo_name, token):
        print(f"Your repository '{NetAnalyzer}' has been initialized on GitHub.")

if __name__ == "__main__":
    main()

