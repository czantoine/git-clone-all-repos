# Git clone all repositories

Clone all repositories from user or organisation 

Simple script using GitHub CLI (no API keys)

Here's a simple solution using the official GitHub CLI tool, gh - no need for API keys and can handle any number of private repos 

## Login with gh for private repos, and follow prompts

With brew

``` shell 
brew install gh
```

``` shell
gh auth login
```

What account do you want to log into? GitHub.com
What is your preferred protocol for Git operations? HTTPS
Authenticate Git with your GitHub credentials? Yes
How would you like to authenticate GitHub CLI? Login with a web browser

Copy and Paste `! First copy your one-time code: XXXX-XXXX`
And Press Enter

## Clone (or update) up to 1000 repos under `./myorgname` folder

Replace 'myorgname' with your org name and increase repo limit if needed 

```
gh repo list myorgname --limit 1000 | while read -r repo _; do
  gh repo clone "$repo" "$repo"
done
```
