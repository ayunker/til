# Git Log an Individual Function

Today I learned you can print the git log for an individual function with the
`-L` flag - `-L :<funcname>:<file>`.

So if I have a function named `friendlyFunction` in `app/fileName.ts`, I can
see it's history with:

```git
% git log -L :friendlyFunction:app/fileName.ts
commit 740ab0c1eeb63e0a6bef06f89397e76407325f58 (HEAD -> main)
Author: Tony Yunker
Date:   Mon Nov 6 17:22:52 2023 -0600

    last commit

diff --git a/app/fileName.ts b/app/fileName.ts
--- a/app/fileName.ts
+++ b/app/fileName.ts
@@ -1,4 +1,4 @@
 export const friendlyFunction = () => {
-  console.log("hi there 👋");
+  console.log("bye now 👋");
   return 2 + 2;
 };

commit 314e725e56871e17c64b811de8e8cdb65badb08e
Author: Tony Yunker
Date:   Mon Nov 6 17:22:31 2023 -0600

    second commit

diff --git a/app/fileName.ts b/app/fileName.ts
--- a/app/fileName.ts
+++ b/app/fileName.ts
@@ -1,4 +1,4 @@
 export const friendlyFunction = () => {
   console.log("hi there 👋");
-  return 1 + 1;
+  return 2 + 2;
 };

commit 61998a2a9dfb64b0ee3aa5c23f783cca517ab15b
Author: Tony Yunker
Date:   Mon Nov 6 17:22:08 2023 -0600

    first commit

diff --git a/app/fileName.ts b/app/fileName.ts
--- /dev/null
+++ b/app/fileName.ts
@@ -0,0 +1,4 @@
+export const friendlyFunction = () => {
+  console.log("hi there 👋");
+  return 1 + 1;
+};

```

[Docs](https://git-scm.com/docs/git-log#Documentation/git-log.txt--Lltfuncnamegtltfilegt)

via https://til.hashrocket.com/posts/pv6sizk7my-git-log-an-individual-function
