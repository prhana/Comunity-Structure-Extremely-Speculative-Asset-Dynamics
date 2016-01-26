# Comunity-Structure-Extremely-Speculative-Asset-Dynamics
Can features based on the network structure around a particular cryptocurrency beforeit trades, predict the severity and magnitude of the subsequent bubbles?

latest PDF: https://www.sharelatex.com/github/repos/nikete/Comunity-Structure-Extremely-Speculative-Asset-Dynamics

[![PDF Status](https://www.sharelatex.com/github/repos/nikete/Comunity-Structure-Extremely-Speculative-Asset-Dynamics/builds/latest/badge.svg)](https://www.sharelatex.com/github/repos/nikete/Comunity-Structure-Extremely-Speculative-Asset-Dynamics/builds/latest/output.pdf)

## Data Description:
1. **Forum data:** The processed forum data can be found [here](https://www.dropbox.com/sh/grxbcuyo4cquyow/AABgnyGD0EtpJwrzfkgJdSuMa?dl=0). There are 5 files which indicate how the mentioned coins in the last two columns of the files were decided. For example, 'unmodified-symbol-or-name-in-subject-with-ANN----unmodified-symbol-and-name-in-subject-with-ANN-sorted-by-time' indicates that the last field contains the list of coins whose name and symbol were mentioned only in the subject; the second to last field in contrast contains the list of coins whose name or symbol were mentioned in the subject. In both cases, the post must have been tagged as announcment for the coin mentions to be counted. **Download these files and put them in a directory named 'forum-data' under the top-level repo directory.**
2. **Coins info with their earliest trade date**: https://github.com/nikete/Comunity-Structure-Extremely-Speculative-Asset-Dynamics/blob/master/data/coins-with-earliest-trade-date.csv
3. **Verified announcements**: A list of 379 coin announcments that were manually verified either through candidates or by search over the forum. https://github.com/nikete/Comunity-Structure-Extremely-Speculative-Asset-Dynamics/blob/master/data/verified_announcements.csv
4. **mapofcoins announcements**: A list of 593 coin announcement that were fetched from mapofcoins page. These are less reliable than verified announcements above, but nevertheless better than our candidates. Not all of these coins actually match the list of our coins in item 2 above. https://github.com/nikete/Comunity-Structure-Extremely-Speculative-Asset-Dynamics/blob/master/data/ann_mapofcoins.csv

## Extract Introducer Candidates:
The current candidates are in *data/introducers/* in five different directories depending on how the coin mentions are detected:

1. unmodified-symbol-and-name-in-subject
2. unmodified-symbol-and-name-in-subject-content
3. unmodified-symbol-and-name-in-subject-with-ANN
4. unmodified-symbol-or-name-in-subject
5. unmodified-symbol-or-name-in-subject-with-ANN

The verified announcements are extracted from these candidates. We manually checked these candidates and used the one that was the best as the first announcement of the coin. If the forum-data changes or new coins are added to our list, you can regenerate the new set of candidates:

1. Update the top level directory in first line of [forums/commands/extract_users.sh](https://github.com/nikete/Comunity-Structure-Extremely-Speculative-Asset-Dynamics/blob/master/forums/commands/extract_users.sh)
2. Run *./forums/commands/extract_users.sh*

The new set of candidates will be written in *data/introducers/unlimited* directory. You can compare them with current set of candidates in data/introducers. 
[data/introducers/verified_introducers.csv](https://github.com/nikete/Comunity-Structure-Extremely-Speculative-Asset-Dynamics/blob/master/data/introducers/verified_introducers.csv) contains the list of 336 announcments we verified from the candidates.


