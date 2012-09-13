================
    CONTENTS
================

    This folder contains:
        1. All  necessary files for the "Preschool Poker" program
        2. The program itself (PreschoolPoker.py)
        3. A folder "results" of all test results using the program with varying parameters

====================
    INSTRUCTIONS
====================
    For instructions on how to use the PreschoolPoker program with arguments, do:
        `python PreschoolPoker.py -h`

    Otherwise, you may simply run PreschoolPoker.py interactively by doing:
        `python PreschoolPoker.py`

    You may also pipe the results of an automated game to an output file.
    To do this successfully you must make sure you supply at least the 
    [game_type] and [ai_opponent] parameters.

====================================
    NAVIGATING THE RESULTS FOLDER
====================================
    
    Results files are named as follows:
        `[game_type]_[ai_opponent]_[number_of_trials]_[learning_rate].txt`
    
    For example a game of draw1 poker vs randy with 10 trials and a learning rate of 0.2 would be:
        `draw1_randy_10_0.2.txt`

    Each results file records the entire sequence of moves for every game played with the resulting
    state probability table listed last. It is recommended that if you only want the probability
    table, you use the following command:
        `tail [file]`
        
    To compare multiple results you may also do:
        `tail -f [file 1] [file 2] ... [file n] 

===================
    CONCLUSIONS
===================

    My conclusions based on the results in the results folder are as follows:
        1. Higher learning rates mean that conclusions will be reached faster.
           This is especially good for determing the best and worst possible states, however,
           every state in between may be grossly inaccurate.
        
        2. The number of iterations plays a part in evening out individual state probabilities.
           The more games played, the more likely you are to be accurate. When combined with a
           high learning rate however, conclusions are reached early on and therefore the benefit
           of a high number of iterations is quickly lost.
           
        3. It is also worth mentioning, that the skill of the player also contributes greatly to
           the effectiveness of any learning strategy. A stupid player will require more iterations
           and/or a lower learning rate to reach a general optimal solution, although it may not 
           matter for a solution specific to the player.
           
        4. Based on the previous observations, it is obvious that a balance needs to be struck between
           number of iterations and learning rate for the best results. Personally, I prefer a low
           learning rate with a high number of iterations as this seems most likely to apply to the
           general case (no matter the opponent's intelligence).
           
           However, for a quick look at best/worst scenarios, it is clear the a high learning rate is the
           most efficient; given an adequate number of iterations.

============
    NOTE    
============
    For the probability table for a game of stud poker, see file:
        'results/stud_deep_100_0.3.txt'
           
           
             
            ====================================================
            |   This program was created by Damola Mabogunje   |
            ====================================================

