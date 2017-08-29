---
title: Watch Out for the Auto Line Ending Conversions
---

Yesterday, I noticed that in some of the files in my local repository, the line breaks were changed from UNIX style (LF) to Windows style (CRLF). The problem occurred after I made some changes on the remote repository (GitHub), and later on pulled them to my local repository using GitHub for Windows.

Further more, if I change those line breaks back and try to commit, those changes will be noticed, but the commit won't go though. A "nothing to commit" error can be found in the generated GitHubLog.txt.

After some research, it turns out that the problem was caused by a feature (or trap?) of Git. The default setting of Git for Windows (and hence GitHub for Windows) will convert LF to CRLF when checking out text files. When committing, CRLF will be converted back to LF.

![](/images/Git%20Setup.png)

To fix the problem, you need to either open up git shell and input command `git config --global core.autocrlf true` or directly head to `C:\Users\yourname` and modify `.gitconfig`.

![](/images/gitconfig.png)

---

Further Reading:  
[A detailed blog over this issue](https://github.com/cssmagic/blog/issues/22)  
[Git documentation](https://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration#__code_core_autocrlf_code)  
[GitHub documentation](https://help.github.com/articles/dealing-with-line-endings/)
