# monitor

Is a mono repository. By itself, it is not an application. It is meant for capturing & persisting things that will be used in other applications; _commit-based_

## As a "mono repository"

Branches have unique purposes:

* `cache` - captures commits from a `monitor` that runs once an hour.
* `source` - persists code used in the `monitor`.
* `main` - bolier-plate for future, _to be created_ branches.

## Not Stand-Alone (_not an application_)

These branches are not applications. Their sole purposes are to capture & persist things for other applications, "commit-based". Merging does not happen; "Git Flow" is not used. Pull requests are not enforced.

\*Even though pull requests are not enforced, collaborators can branch off the target branch & open pull requests if they are are more comfortable with that workflow or if they are unsure about a commit that they are developing.

## Commit-Based

Because pull requests are optional, there are things to consider when developing your commit:

- Develop a single (_solitary_) commit. \*Think of your (_single_) commit as if it were the pull request.
    - Avoid small incremental commits
    - It is fine (_& common_), to force push, `npm push origin worker --force`, over the top of your last commit in order to make it right.
      - *Be careful* with force pushing. Probably no one else is editing and committing to the same branch you are at the same time, but make sure because you don't want to accidentally blow away their commit (_that you may not yet have locally_).
- Do these, in this order: (_to maximize auto correction_)
    - `npm run pretty`
    - `npm run lint`
- Make the commit message helpful:
    - Prefix the message w/ the name of the branch; example: `[source] youtube; update script to filter out upcoming live streams`.
    - When looking at these commits, next week or next month, does the message indicate the reason for the change?
    - Not wordy, just helpful
