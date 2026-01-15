/// BRANCHES AVAILABLE WITH DESCRIPTSIONS \\\

dev (integration branch)
-- add encouraging message for players

fetaure1 (features)
-- add version comment documentation : add comment in Main.java
-- improve user feedback messages for guesses : text changes in GameEngine.java
-- Add play-again loop functionality : changes in Main.java
-- Add ability to quit game with negative numbers : changes in GUI.java

feature2 (features)
-- implement max attempts logic and game over condition : add var/ functions GameEngine.java
-- Add max attempts constant and gameover state : changes in GameUI.java GameEngineTest.java

feature3 (fetures)
-- done : Add test cases GameEngineTest.java
-- had to fix : Fix guessing target GameEngine.java
-- got it done : Add Hint functions GameEngine.java 
-- started hint : Enabled hints GameEngine.java

hotfix (commits ready for main)
-- fix randomInt to properly inlcude max value in range : added test cases UtilsTest.java

main (Stable branch)
-- initial Number guessing game

/// UNDERSTANDINGS and OBSERVATIONS\\\
• Differences between merge, rebase, squash, and cherry-pick
    Merge:
	Let's start off that we are currently in branch A. 
	When calling 'git merge B', we are stating that we want to combine branchB into branchA(current).
	The combination is more of a 'if I don't have parts of B in A, then add them to A'.
	Conflicts occur when both A and B have the same part (function, var, command), but they are different.
	Resolve Conflicts manually -> then git add -> git commit -m "Resolved merge conflicts between A and B"

    Rebase:
	This keeps history linear 
	"Rebase rewrites the current branch’s commits to sit on top of another branch."

	--LOGS OF INDIVIDUAL BRANCH--
	Branch Main: commitX
	Branch A: commitX --- commitA --- commitB
	Branch B: commitX --- commitC --- commitD

	While in Branch Main and 'git merge B'

	--LOGS OF INDIVIDUAL BRANCH--
	Branch Main: commitX --- commitC --- commitD
	Branch A: commitX --- commitA --- commitB
	Branch B: commitX --- commitC --- commitD

	While in Branch A and 'git rebase Main' 
	"Branch A’s history is rewritten so that its commits are replayed linearly on top of main."

	--LOGS OF INDIVIDUAL BRANCH--
	Branch Main: commitX --- commitC --- commitD
	Branch A: commitX --- commitC --- CommitD --- commitA' --- commitB'
	Branch B: commitX --- commitC --- commitD

	visual explanation : https://www.youtube.com/watch?v=0chZFIZLR_0
	resons to why to do : https://www.youtube.com/watch?v=DkWDHzmMvyg
	
    Squash:
	Best used if messy messegaes for commits to clean
	'git rebase -i HEAD~4'  <-- the value 4 is for the FOUR most recent commits
	pick - remain as is
	squash - remove/merge to the current 'pick' commit message

    Cherry-pick:
	Apply one specific commit from another branch onto the current branch.
	For urgent fixes
	
	 
• What you observed in the git history for feature1 vs feature2 vs feature3
    Feature1: I believe this history had the simplest and only the history associated to its branch.
	I lost the comparison once the feature was deleted.
    Feature2: This history is more complex because it was rebased and later involved in merges with dev.
    Feature3: Has the shorter history because of the squash.

• When you would use each strategy in real projects
    Merge : I think it is best to use when combining completed work from one branch to another. 
	This is also to keep full history of the project.
    Squash : This is best when there is only one person working on the branch and to commit history linear
	for the ease of reading.
    Cherry-pick: is to apply a specific fix.

For the moment that I am new this system, I think it is best to have the similar branch structure as this
	one to where there is the main (initialize), dev (integration), and seperate feature branches.
 