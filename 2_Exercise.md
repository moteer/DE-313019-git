**Main Task** 
1. Run the status command. Notice how it tells you what branch you are in. 
2. Use the branch command to create a new branch. 
3. Use the checkout command to switch to it. 
4. Make a couple of commits in the branch – perhaps adding a new file and/or editing existing 
ones. 
5. Use the log command to see the latest commits. The two you just made should be at the 
top of the list. 
6. Use the checkout command to switch back to the master branch. Run log again. Notice 
your commits don’t show up now. Check the files also – they should have their original 
contents. 
7. Use the checkout command to switch back to your branch. Use gitk to take a look at the 
commit graph; notice it’s linear. (In the unlikely case you do not have gitk, using git log 
--oneline --graph --decorate=short --all will give you a similar commit graph, 
but rendered in ASCII.) 
8. Now checkout the master branch again. Use the merge command to merge your branch 
into it. Look for information about it having been a fast-forward merge. Look at git log, 
and see that there is no merge commit. Take a look in gitk and see how the DAG is linear. 
9. Switch back to your branch. Make a couple more commits. 
10.  Switch back to master. Make a commit there, which should edit a different file from the 
ones you touched in your branch – to be sure there is no conflict. 
11.  Now merge your branch again. (Aside: you don’t need to do anything to inform Git that you 
only want to merge things added since your previous merge. Due to the way Git works, that 
kind of issue simply does not come up, unlike in early versions of Subversion.) 
12.  Look at git log. Notice that there is a merge commit. Also look in gitk. Notice the DAG 
now shows how things forked, and then were joined up again by a merge commit. 
13. Try all the above in Intellij.
**Bonus Tasks** 
1. Once again, checkout your branch. Make a couple of commits. 
2. Return to your master branch. Make a commit there that changes the exact same line, or 
lines, as commits in your branch did. 
3. Now try to merge your branch. You should get a conflict. 
4. Open the file(s) that is in conflict. Search for the conflict marker. Edit the file to remove the 
conflict markers and resolve the conflict. 
5. Now try to commit. Notice that Git will not allow you to do this when you still have 
potentially unresolved conflicts. Look at the output of status too. 
6. Use the add command to add the files that you have resolved conflicts in to the staging 
area. Then use commit to commit the merge commit. 
7. Take a look at git log and gitk, and make sure things are as you expected. 
8. If time allows, you may wish to... 
 Delete everything but your .git directory, then do a checkout command, to prove 
to yourself that this really will restore all of you current working copy. 
 Create a situation where one branch has changed a file, but the other branch has 
deleted it. What happens when you try to merge? How will you resolve it? 
 Look at the help page for merge, and find out how you specify a custom message for 
the merge commit if it is automatically generated. 
 Look at the help page for merge, and find out how to prevent Git from automatically 
committing the merge commit it generates, but instead give you chance to inspect it 
and merge it yourself. 
