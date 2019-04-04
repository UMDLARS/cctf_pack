# Making a New Pack

A pack is a directory containing all the needed information to run a certain competition.
To run a pack the root directory of the pack should be placed in the root directory of this dtanm repo. And should be called `pack`.

The structure:  
 - The root folder
    - `docs`
        - `tips` - This should be an executable that prints out helpful tips for the players of the competition.
        - `www` - This directory should contain all the files that you would like to serve using apache on port 80.
            - Normally this folder should contain an `index.html`
    - `env`
        - This directory should contain any files that you would like to be copied into the same folder as the players' program when being scored.
        - Note: These files are also copied into the current working directory of the gold as well.
        - Normally you would put some sample test input files into this directory.
    - `gold`
        - This directory should contain the gold program (a "perfect" version of the program.)
    - `info` - (We should change this to be a single file named `config.json`.)
        - `bin_name` - This should contain the name of the binary/script which is submitted.
        - `pack_name` - This should contain the name of the pack. Can be anything. Currently I don't think it is used for anything.
        - `src_name` - This should be the name of the source file. (NOTE: this should be removed in the next version.)
    - `src`
        - This directory should contain whatever code you would like all players to receive.
