### Git Commands

Command | Description
--------|------------
git config --global http.sslVerify false | To avoid SSL certificate problem: Unable to get local issuer certificate
git commit -a --allow-empty-message -m '' | To do an empty commit message
git config --global http.sslVerify false | To set the SSL verify false
git remote prune origin | To delete the branch locally which is not available in remote
git -b checkout < new_branch_name > | To create a new branch and checkout the same
git update-index --assume-unchanged < file > | To ignore a changed file
git update-index --no-assume-unchanged < file > | To revert that ignorance by the previous command
Squashing for Upstream |git fetch upstream <br/>git checkout \<your branch\><br/>git rebase -i upstream/master<br/><br/><I>choose squash for commits which needs to be squashed</I><br/><br/>git push origin \<your branch\> -f