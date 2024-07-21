#Commit 1 : Starting the project

In Squash, If you have multiple commits in your branch and that branch has not yet merged in the production, you can squash all that commits and make into one commit which looks like you have not made any mistake and solved the problem in one go.

for ex, you have commits and each commit have some changes of course.
- RC-Self-learning | Solved the Bug
- Code Refactor
- Minor Changes
- Code organized
- Used Query Params Instead of LocalStorage

all this commits, looks like you are noob.
So to be like Pro , you can show only one commit and you can choose what should be displayed. 

Let's Learn : (#Commit 2 : Introduction | Prologue ) 

Made some Changes and "commit 3" as it's ready to go from my side 😊

Made the (#Commit 3 : Done with Changes | Bug Solved  )

-------Some one Reviewed and Give some corrections | Suggestions --------

You Made some changes and then Code Refactored.

Made the (#Commit 4 : Code Refactor | Minor changes  )


-------Kamlesh Sir Reviewed | Use Query Params Instead of LocalStorage --------

You again made the changes and then used the Query Params Instead of LocalStorage.

Made the (#Commit 5 :  Used Query Params Instead of LocalStorage  )



Now if you see the Commits Number, they are like a lot. and all the commits message you have added also looks like you are not a pro developer.

So here squash comes into the picture.

It's not a command but a keyword. Used to squash the previous commits into one.
You can merged several commits into one single commit with the compelling interactive rebase command.

Step 1 : Check the commit history 
git log --oneline




Step 2 : Choose the commits to squash. | Start the Interactive Rebase:

Suppose you want to squash the last commit. run this command :
- git rebase -i HEAD ~<number of commits you want to go back>

EX git rebase -i HEAD ~4 commits back




Step 3 :  Edit the Rebase File:

The list you see might look something like this:
pick a1b2c3d Commit message #Commit 1 : Starting the project
pick e4f5g6h Commit message #Commit 2 : Introduction | Prologue
pick i7j8k9l Commit message #Commit 3 : Done with Changes | Bug Solved 
pick m0n1o2p Commit message #Commit 4 : Code Refactor | Minor changes 
pick q3r4s5t Commit message #Commit 5 :  Used Query Params Instead of LocalStorage


Each line starts with "pick", which means you’re selecting that commit to include as-is. To squash commits, you change pick to squash (or s), starting from the second commit you want to combine.

For example, if you want to combine all 5 commits into the first commit:

pick a1b2c3d Commit message #Commit 1 : Starting the project
pick e4f5g6h Commit message #Commit 2 : Introduction | Prologue
pick i7j8k9l Commit message #Commit 3 : Done with Changes | Bug Solved 
pick m0n1o2p Commit message #Commit 4 : Code Refactor | Minor changes 
pick q3r4s5t Commit message #Commit 5 :  Used Query Params Instead of LocalStorage


Now you want to squash all commits except the third one and use the message of the third commit as the final commit message, : 

git rebase -i HEAD~5


pick a1b2c3d Commit message #Commit 1 : Starting the project
squash e4f5g6h Commit message #Commit 2 : Introduction | Prologue
squash i7j8k9l Commit message #Commit 3 : Done with Changes | Bug Solved 
squash m0n1o2p Commit message #Commit 4 : Code Refactor | Minor changes 
squash q3r4s5t Commit message #Commit 5 : Used Query Params Instead of LocalStorage


pick keeps the first commit as-is.
squash combines subsequent commits into the first one.


Save and Close the Editor:
Git will combine the changes from all squash commits into the first pick commit.

Edit the Commit Message:

After squashing, Git presents a new editor to craft a commit message for the combined commit.
The new commit message window will include all previous commit messages. It might look like this:

# This is a combination of 5 commits.
# The first commit's message is:
Done with Changes | Bug Solved

# This is the 2nd commit message:
Introduction | Prologue

# This is the 3rd commit message:
Starting the project
...


Here, you can choose to keep the message of the commit you prefer (Commit #3 in this case). You edit the message to be exactly what you want:

Done with Changes | Bug Solved  

Save and Close the Editor:


#Commit 6 :  DONE WITH THE SQUASH LEARNING
-------------------------------------------------------------------------------