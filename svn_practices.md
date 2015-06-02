Svn practices来自Apache OpenOffice Wiki
跳转至： 导航、搜索
This page is under review. This line will be removed after it is done. 

This page gathered svn practices frequently used by contributors and committers. If you have any advice to this page, please feel free to update it or discuss your idea in ooo-dev mail list. 

SVN Client 1.7 is recommanded to use for AOO development. It's strongly recommended use alternative name for svn's subcommand, like co-checkout, ci-commit, up-update, di-diff, and so on. 

目录 [隐藏] 
1 Read-only access
2 Write access
3 Working with a branch
4 Reference
Read-only accessGrab the whole source code from main trunk 
svn co https://svn.apache.org/repos/asf/openoffice/trunk aooGrab a branch 
svn co https://svn.apache.org/repos/asf/openoffice/branches/AOO410 aoo410Grab a specific directory from a branch 
svn co https://svn.apache.org/repos/asf/openoffice/branches/AOO410/main/sw swThis gets the source code for Writer module (named "sw") from the AOO410 branch 

Get the latest changes into your working copy 
Change into the working directory such as aoo or sw for the above case and run 

svn update
This command will merge the public changes with the local changes if there are any. 

Update to a specific revision 
svn update -r xxxx
Check changes history 
svn log
svn log filename
Also show information about the paths that were changed in each displayed revision. 

svn log -v
Show for specific revision. 

svn log -r m
Organize logical changes by changelist 
Use cl instead of changelist for convenience. 

svn changelist tocload-feature filename1 filename2 ...
Check changes and create a patch from local changes 
When creating patch, combine all your changes into a patch. 

The path in patch should at least start in "main" or top directory. 

svn diff filename1 filename2 > n.patch
Create patch from a specific revision: 
svn diff -c m > n.patch
For changes consisting of many revisions n..m use 
svn diff -r m:n > n.patch
instead. 

Discard local changes and revert to unmodified state 
svn revert
Write accessApply patch when review other's code change 
Make sure current directory is consistent with path in patch, like "main". 

svn patch n.patch
Reverse patch: 

svn patch --reverse-diff n.patch
Check changes before committing them 
svn status
and / or 

svn diff
svn diff --changelist tocload-feature
Commit your changes 
Don't forget to specify the list of files/dirs that are changed to avoid accidentally committing unwanted changes. 

svn commit -m "comment" [filenames]
svn commit -m "comment" --changelist tocload-feature
Committing a patch 
Prepare a commit-comment file (e.g. mychangelog.txt) by using the relevant parts of this template: 

  Patch by:
  Suggested by:
  Found by:
  Review by:
  Tested by:
and then commit it by running either 

svn commit -F mychangelog.txt [filenames]
svn commit -F mychangelog.txt --changelist tocload-feature
Update Bugzilla 
Update bugzilla with revision information for cross reference when you are done with the commit and know the revision numbers. 

Working with a branchThere at least two situations that you need to work with a branch. 

If the changes you are about to make are complicated or you want to share them with others during development. 
There are interesting upstream branches created by others. For example, after AOO 3.4 is released, a branch for the AOO 3.4.x micro releases was created. 
Instead of doing 'svn commit' both on trunk and the release branch use 'svn merge' if your fix needs to be submitted to both code lines. 

There are also other cases in which you don't want to commit in development mainline directly. 

How to create a branch 
 svn copy https://svn.apache.org/repos/asf/openoffice/trunk  \
           https://svn.apache.org/repos/asf/openoffice/branches/tocloading \
      -m "Creating a private branch for toc loading of word document."Keep a branch in sync 
Subversion is aware of the history of your branch and knows when it split away from the mainline. To perform a sync merge, first make sure your working copy of the branch is “clean”—that it has no local modifications reported by 'svn status'. Then simply run: 

$ pwd
/home/user/tocloading 
$ svn merge ^/ooo/trunk
Reintegrate a branch 
When your new feature is done. It needs to be merged back to mainline. Before do that, sync the brache with mainline and commit your changes. Then 

$ svn merge --reintegrate ^/ooo/branches/tocloading
and commit again 

Remove a branch 
Once a branch is integrated back it has become useless and can be removed. 

$ svn delete ^/ooo/branches/tocloading -m "Remove branch of toc loading"
ReferenceSVN Basics http://openoffice.apache.org/svn-basics.html 

A guide for new committers: http://www.apache.org/dev/new-committers-guide.html 

Merge Instruction from FreeBSD: http://wiki.freebsd.org/SubversionPrimer/Merging 

SVN book: http://svnbook.red-bean.com/en/1.7/svn-book.html 

SVN Best Practices http://svn.apache.org/repos/asf/subversion/trunk/doc/user/svn-best-practices.html 

取自“https://wiki.openoffice.org/w/index.php?title=Svn_practices&oldid=234574”
1个分类：Documentation查看
页面讨论查看源代码历史个人工具
登录导航首页最近更改Download AOODocumentationUser ForumExtensionsTemplatesWiki Help打印/导出创建图书
下载为PDF
打印版本
搜索
     工具箱链入页面相关更改特殊页面永久链接页面信息  本页面最后修改于2014年3月24日 (星期一) 13:37。Content is available under ALv2 unless otherwise noted.隐私权政策关于Apache OpenOffice Wiki免责声明
