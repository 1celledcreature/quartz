Thing like:

- Profile picture not changing after uploading new one to O365.
- Details not syncing across to Teams.
- Showing duplicate accounts for one user (only 1 account seen in teams admin center)

These and possible other errors can be solved by clearing the cache in MS Teams.

Firstly, **close MS Teams completely**. (Quit)

Type **%appdata%\Microsoft\Teams** into the search bar next to 'start' button on desktop to open the folder directory.

Go to the cache folder:
![[Pasted image 20250110160010.png]]

and any containing folders until you get to a folder that contains files that look like this:
![[Pasted image 20250110160045.png]]

Delete all the files and re-open teams.
