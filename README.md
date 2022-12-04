# aoc-times

A script for checking times on a private leaderboard.

## Using

Run

```bash
$ ./aoc-times --cookie <COOKIE> --leaderboard <LEADERBOARD> --day <DAY_NUMBER> --part <PART_NUMBER> --year <YEAR>
```
or alternatively, predefine them, use a configuration, or a combination of both to define the variables.

```bash
$ COOKIE=<COOKIE> ./aoc-times -f config.txt --year 2015 # successive parameters take priority
```
Example output:

```
Completion Table for Day 1 Part 1 (2022)
#   Name                Date                    
1   Daniel              Thu   Dec  1  00:01:32  2022
2   andy-k              Thu   Dec  1  00:01:41  2022
3   ast-ral             Thu   Dec  1  00:01:50  2022
4   tritoke             Thu   Dec  1  00:01:58  2022
5   0e4ef622            Thu   Dec  1  00:02:07  2022
6   Giacomo             Thu   Dec  1  00:02:37  2022
...
```

For more information on how to use, run `./aoc-times --help`.

## How it works

This script essentially makes a `curl` request and runs a bunch of `jq` commands to grab the information that's needed.

Caching is done by storing information and last updated time in a `.aoc` directory in the same directory as the script. For more information about the need for caching, see [the automation FAQ.](https://www.reddit.com/r/adventofcode/wiki/faqs/automation/)