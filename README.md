# Making a New Pack

A pack is a directory containing all the needed information to run a certain competition.

To run a pack, the root directory of the pack should be placed (or symlinked) into the root directory of the dtanm repo (in a directory named `pack`) before you run `./setup.sh`.

To create a new pack, modify this repository with the new pack programs and data.

To change this repo into your new pack repo, remove the `.git` directory in this repository, create a new private repo in github (don't want the program to leak!), and follow the instructions to push your new repository up.

Inside the `pack/` folder should be the following directory structure:

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
- `info/` -- metadata for the pack (We should change this to be a single file named `config.json`.)
	- `bin_name` - This should contain the name of the binary/script which is submitted.
	- `pack_name` - This should contain the name of the pack. Can be anything. Currently I don't think it is used for anything.
	- `src_name` - This should be the name of the source file. (NOTE: this should be removed in the next version.)
- `src/` -- This directory should contain whatever code you would like all players to receive.

## Questions?

Talk to us in #dtanm-dev on https://umdlars.slack.com/ or look at an existing pack, such as: https://github.umn.edu/UMDLARS/cctf_calc
