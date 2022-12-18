# Ryan’s Part Number Project

## Description
Part number system to track part numbers requested. 
Essentially, maintain a simple CSV file in a version-tracking system (git/GitHub). 
Use GitHub Desktop to simplify access to git/GitHub (other tools, including command line work, too).
(Excel would work, but is a little more complex and harder to see file changes.)

## Requirements
* Self-service so designers can request multiple part numbers
* Part numbers are not duplicated
* Store a few basic pieces of information about each part number (who, what, when, etc.)
* Be able to review and edit numbers added
* Manually make/track/mirror part numbers made in core system
* Cheap and simple solution

## Components
* GitHub repository instance (free)
* GitHub account for designers (free)—can be single account or one for each
* Python interpreter—each designer (free)
* Python script (“free”?)
* GitHub Desktop (optional; free)—each designer
* CSV, representing the “database”—should open up easily in Excel, text editor, or similar (free)

## Process
### Designer:
1. Pull changes from git (GitHub Desktop)
2. Run script (from git-project dir): `python part-numbers.py —request $count $designer-name $part-seed`
    1. Script reads CSV file into program
    2. Script finds next $count items to make into part numbers
    3. Script adds numbers to CSV, rewriting the CSV to disk
    4. Script returns list of numbers (or reports errors)
3. Review changes in GitHub Desktop, pull changes from upstream
    1. if conflicts, designer will have to correct directly 
    2. could always throw away local changes and re-run
4. commit, and push back to git (GitHub Desktop)

### Admin:
1. Review CSV in Excel, text editor, or similar (keeping CSV format)
2. Manually manage mirror to core system ?

### Developer:
1. Write python script
2. Maintain part number creation script?
3. Maintain features?
