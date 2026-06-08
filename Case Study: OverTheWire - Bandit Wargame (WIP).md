# Scenario & Objective: 
The simulation is a wargame in which I must access several layers of a system to uncover passwords intentionally buried within a hosted machine via SSH.
[Wargame Link: OverTheWire - Bandit](https://overthewire.org/wargames/bandit/)

# Evidence Acquired:

Multiple passwords were discovered to access the next level; Though I'd like to prove my understanding of evidence integrity, listing the passwords or the files' MD5/SHA_256 hashes publicly is against the policy of OverTheWire, as the challenge must remain challenging for future participants.
From levels 1-6, most files that held the password were text documents.

# Tools Used: 

Terminal commands to access the hosted machine via SSH.

# Investigation & Analysis:

Level0 entry : User login information for SSH access was provided to begin the wargame.

level1 entry: Username provided, but password was not. This will be the case for the remainder of the levels.
- Used ls to list out directory contents
- Used file readme to see the file type of the contents
- Used cat [file name] to print out the text of the file's contents
- The password appears!

level2 entry:
- Names that just use "-" are tricky due to the terminal mistaking the name for a command, so it doesn't readily open the file.
- Instead, you must list the name with the directory, as in "./-" rather than "-"
- Used cat [file name] once more, "cat ./-"
- The password appears!

level3 entry:
- There are spaces within the file name alongside double dashes (--spaces in this filename--), which transforms the name into an obstacle.
- To read this file, we'll combine a couple methods to make the filename usable.
- Used cat [file name] with ./ and quotation marks around the file; That way, the system will treat the file name as one file rather than multiple commands, as well as remaining within the main directory.
- cat ./"--spaces in this filename--"
- The password appears!

level4 entry:
- The file is hidden!
- First I see a directory in blue [inhere], but once we move to this directory and try ls, nothing appears.
- Used find to list file names of the directory, which reveals two files.
- One of them is the file! [The name is not listed here to preserve the challenge]
- Used cat [file name] with ./ and quotation marks once more.
- cat ./"[file-name-here]"
- The password appears!

level5 entry:
- Needed to move into the proper directory [The name is not listed here to preserve the challenge] once more, but only one of the files is human-readable; The rest are encrypted.
- There must be an easier way to find the human-readable one, especially if there are more than a handful of encrypted files buried within a system.
- For this level, however, I just went down the line and did cat ./[file name] until the legible one appeared.

level6 entry:
- This go-around is quite different.
- The password for this level is stored in a file somewhere under the proper directory that has all of the following properties:
    human-readable
    1033 bytes in size
    not executable
- First I'll need to cd inhere; Then examine file sizes using file [file name] --extension or -text, I think; A more efficient method was discovered, but I left my thought process below alongside the solution I found.
- There's far too many files to go through them one at a time, so I need to figure out what command helps sift them out by size and file type.
- There are 19 directories in total. Using "file *" tries to open all the files within them. Will "cat" work here or nah? I'm looking for a small file, after all.
- Looking up how to find a file with a specific file size (1033 bytes), using the find command was right, but I needed to fine tune it to look for regular type files with one specific file size.
- Use "find [directory] -type f -size 1033c"
- The file that matches this size appears! Use cat ./[file name] to read it.
- The password appears!

level7 entry: WIP!

Use screenshots (redacting any sensitive info if applicable).
Show how you found the artifacts. Don't just say "I found the deleted file." Say: "Using Autopsy, I parsed the $MFT (Master File Table) and identified a deleted PDF in the user's Downloads directory."

# Executive Summary / Findings:
A 1-paragraph summary written for non-technical readers explaining exactly what happened.

WIP!
