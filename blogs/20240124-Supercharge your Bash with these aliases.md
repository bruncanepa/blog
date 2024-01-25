# Supercharge your Bash with these aliases

As a Software Engineer I'm all in to become more efficient. 

In the past years I've curated a collection of bash aliases that help me achieve that.

Here are some of my Git favorites:

```bash
# pushes current non-tracked branch
alias gpsu="git push -u origin $(git branch --show-current)"      

# removes last commit, and all changes from it are staged
alias grsoft="git reset --soft HEAD^" 

# checkouts with all passed args
alias gch="git checkout $@"

# merges with origin/master with all passed params
alias gmom="git merge origin/master $@"
```

I've uploaded my entire `~/.bash-profile` on [Github](https://gist.github.com/bruncanepa/082b4975243589c66dc4f66820cc0d01) .



---

## Read it also on:

- [Twitter](https://twitter.com/bruncanepa/status/1750320391313146263)
- [LinkedIn](https://www.linkedin.com/posts/bruno-canepa_softwareengineer-git-activity-7156258575827316736-_HJd)

---

tags:

- productivity
- git

---
