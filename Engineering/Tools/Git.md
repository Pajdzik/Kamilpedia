- git represents commits as snapshots (it stores the “tree” of the current version of every file)

# Commands
## add
- When running `git add`, Git hashes the content, and puts blob in `.git/objects`

## commit
- When committing, Git creates a new tree object with representation of the state of the repository at the time

## merge-base
- `git merge-base main mybranch`
- gives us the “base” commit where our branch branched off

## rebase

### Links
- https://www.freecodecamp.org/news/git-rebase-handbook/


# Concepts

## Branches
### Links
- [git branches: intuition & reality](https://jvns.ca/blog/2023/11/23/branches-intuition-reality/)
## HEAD
### Links
- [How HEAD works in git](https://jvns.ca/blog/2024/03/08/how-head-works-in-git/)

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
- [# Do we think of git commits as diffs, snapshots, and/or histories?](https://jvns.ca/blog/2024/01/05/do-we-think-of-git-commits-as-diffs--snapshots--or-histories/)
- 