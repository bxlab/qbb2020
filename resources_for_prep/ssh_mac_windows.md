# Instructions to access MARCC from your laptop

## For macOS and Windows 10

macOS and Windows 10 both have a built in program called `ssh` that allows the user to connect securely to a remote server (e.g. MARCC)

To open an ssh connection to MARCC in macOS or Windows 10:

1. Open your terminal/command prompt.<br /><br />On macOS, open the terminal app. If terminal is not on your toolbar, you can search **terminal** in **Finder** or open spotlight search using the shortcut `cmd`+`Space` and then searching **terminal**.<br /><br />If you are on Windows 10, open the command prompt app. Click on the **magnifying glass** icon at the bottom of the screen to open a search, and search **command prompt**. Alternatively, use the shortcut `windows key`+`R` to open the **run** window, type **cmd** and then click **OK**.

2. Once your terminal/command prompt app is open, type the command `ssh <JHEDID>@jhu.edu@login.marcc.jhu.edu`.<br /><br />Your JHEDID is the bit before *@jh.edu* or *jhu.edu* in your JHU email. For example, if my JHU email was johndoe@jh.edu, I would log in with the command `ssh johndoe@jhu.edu@login.marcc.jhu.edu`.

Congratulations! You're now on MARCC.