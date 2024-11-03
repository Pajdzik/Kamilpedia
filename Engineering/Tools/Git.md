- git represents commits as snapshots (it stores the “tree” of the current version of every file)

# Commands
## add
- When running `git add`, Git hashes the content, and puts blob in `.git/objects`

## blame
- `-L` enables one to provide lines to annotate
- `-C -C -C` ignores moved or copied lines

## commit
- When committing, Git creates a new tree object with representation of the state of the repository at the time

## log
- `git log @ ^main --oneline --graph` – instructs git to show only the commits that exist on `feat_branch` but not on `main`

## merge
- `them` – is the other branch you merged in
## merge-base
- `git merge-base main mybranch`
- gives us the “base” commit where our branch branched off

## rebase
- `them` - the branch that you were on when you ran `git rebase`

## worktree
- [How I Use Git Worktrees](https://matklad.github.io/2024/07/25/git-worktrees.html)
### Links
- https://www.freecodecamp.org/news/git-rebase-handbook/
- [I kind of like rebasing](https://rednafi.com/misc/on_rebasing/)

# Concepts

## Branches
### Links
- [git branches: intuition & reality](https://jvns.ca/blog/2023/11/23/branches-intuition-reality/)
## Config
### Links
- [Changing Email Addresses Globally](https://www.git-scm.com/book/en/v2/Git-Tools-Rewriting-History#_changing_email_addresses_globally) – useful when one forgets to set it up in the git config before starting to work
## HEAD
- Three meanings
	- `.git/HEAD` file
		- name of the current branch
		- commit hash
			- detached HEAD state
	- commit (`git show HEAD`)
		- a.k.a. revision parameters
	- other
			- output in `git status
				- `HEAD detached at 90c81c72` when there is a commit ID in the file
			- output in `git log`
			- output merge conflicts
### Links
- [How HEAD works in git](obsidian://open?vault=Kamilpedia&file=Articles%2FProgramming%2FHow%20HEAD%20works%20in%20git)s
## Packfiles
- deduplication technique
- really created to reduce network usage
- stored in `.git/objects/pack/`
	- packfile
	- index to locate entries inside of the packfile
- objects in a packfile can either be _deltified_ or _non-deltified_
	- deltified - stores only a special diff instead of storing the whole object
		- ones with the extra SHA at the end
### Links
- [Unpacking Git packfiles](https://codewords.recurse.com/issues/three/unpacking-git-packfiles)
# Tools
- [git branchless](https://github.com/arxanas/git-branchless)
- 
# Links
- [Do we think of git commits as diffs, snapshots, and/or histories?](https://jvns.ca/blog/2024/01/05/do-we-think-of-git-commits-as-diffs--snapshots--or-histories/)
- [Notes on git's error messages](https://jvns.ca/blog/2024/04/10/notes-on-git-error-messages/)
### Talks
- [So You Think You Know Git Part 2 - DevWorld 2024](https://www.youtube.com/watch?v=Md44rcw13k4)
