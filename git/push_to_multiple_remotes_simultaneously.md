# Push to Multiple Remotes Simultaneously

I've started mirroring some of my git repos to multiple remotes, making use of
git's decentralized nature. I quickly realized this can become tedious. If I
have my `origin` remote set to urlA, and `backup` remote set to urlB, then I
have to push to each remote each time.

```
$ git push origin main
$ git push backup main
```

I don't know about you, but I **will** forget to push to backup at *least* 50%
of the time. 

Turns out you can use `git remote set-url` to add multiple repo urls to a
remote (for push only, not fetch). So you can add urlA and urlB to `origin`, so
any push to origin will push to both remotes.

```
$ git remote set-url --add --push origin urlA
$ git remote set-url --add --push origin urlB

$ git remote -v 
origin	urlA (fetch)
origin	urlA (push)
origin	urlB (push)

```

You can't do this for fetch - think about the conflicts pulling from branches
on 2 different remotes that have diverged 😱

[git-remote Docs](https://git-scm.com/docs/git-remote)

via https://til.hashrocket.com/posts/qkfqt9q7il-push-to-multiple-remotes-simultaneously

https://yunchizhang.github.io/posts/multi_remote_repos.html
