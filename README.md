# DTANM Pack Template

A pack is a directory containing all the information needed to run a
[DTANM](https://github.com/UMDLARS/dtanm) competition.

To run a pack, the root directory of the pack should be placed (or symlinked)
into the root directory of the DTANM repo (in a directory named `pack`) before
you start the competition. (More directions on this are available in [the DTANM
repository](https://github.com/UMDLARS/dtanm).)


### Creating a new pack
To create a new pack, modify this repository with the new pack programs and
data. We recommend going to this repository's GitHub page and clicking the
green "Use this template" button at the top, which will create a new repository
with all the files from this repo included. Then you can add and remove files
as appropriate. Remember to keep your repositories private---we don't want the
files for `gold` to be public!

### Pack directory structure
Inside the `pack/` folder should be the following directory structure:
- `attacks/`
	- This directory should contain attacks to be preloaded (in the
	  [documented tarball form](https://github.com/UMDLARS/dtanm/wiki/Attacks),
	  which is how files are provided when submitted to DTANM and downloaded.
	- When DTANM is started for the first time, the attacks will be registered.
	- Attacks will not belong to any user, and cannot be duplicated by other
	  users. These attacks can pass or can fail with the default provided code.
	- If a mapping file attacks.tsv exists, then attack names will be provided
	  from those files. Otherwise, the filename will provide the name of the
	  attack (for example, `Divide by zero.tar.gz` will result in an attack
	  named `Divide by zero`.
- `docs/`
	- `index.[html|md|txt]` - This is your base help file. See the existing
	  `index.md` for an example, or `instructions.md` for specific instructions
	  on how to create documentation files.
- `env/`
	- This directory should contain any files that you would like to be copied into the same folder as the players' program when being scored.
	- Note: These files are also copied into the current working directory of the gold as well.
	- Examples include: test input files for the program if needed (for programs that take file input)
- `gold/` -- This directory should contain the source tree of the gold program (a "perfect" version of the program.) 
	- gold must include a `Makefile` for installation that builds a program called `gold`
	- Recommended: gold programs should include a test script with a test case for all known bugs in the "broken" version
- `src/` -- This directory should contain whatever code you would like all players to receive.
        - This should include a `.gitignore` file containing all files you expect to be built; if the user commits
	  these, it will cause problems when they are pushed.
- `config.py` -- This file contains configuration values that will be passed
          to the framework.
- `Dockerfile.build` -- This file will be used to build the submitted programs.
          Check out the sample for more instructions.

### Questions?
Talk to us in #dtanm-dev on https://umdlars.slack.com/ or look at an existing
pack, such as [`echo`](https://github.com/UMDLARS/dtanm_pack_echo).
