# git-tools
Utility scripts for git

## git-clean-squashed-branches

Many repositories use squashed merges for a cleaner history,
but this makes it hard to know what local branches have been
merged and are thus eligible for deletion.  This script solves
that problem.

Just run this from within your repository and it will give a
list of branches eligible to delete and ask for confirmation
before deleting them.  This ultimately calls `git branch -d`,
not -D, so it's guaranteed not to delete branches that haven't
even been pushed yet.

This works by calling the `gh` github cli tool and inspecting
which commits were merged there, so you must have `gh` installed
and authenticated to run:

  https://github.com/cli/cli

Also uses the `jq` json filter.
