
# DesktopLauncher
A solution for building unique windows desktop app distribution systems similar to clickonce.

Note code & instructions can also be found just off the main page at kettlemorainesoftware.com

Conceptually there is an app repository for user apps. There is a console app that is run through a desktop shortcut for running each app in the repository. The console app first checks the repository to see if any new app files are there, and if so copies them down to the user's profile. The console app then runs the app in the user's profile. If the repository is not available for any reason, the app is simply run.

To initially run a user app, the user gets an e-mail with a link to the repository. Clicking this link will cause the shortcut to be placed on the desktop. This shortcut is then used to subsequently run that app.

To configure the solution for a single customer, a developer needs to edit three constants in one file in the solution. Then the solution needs to be rebuilt.

To configure for a second customer (& subsequent customers), conditional compliation can be used.

The repository can be thought of as being CONNCECTED or DISCONNECTED, which is set using one of the constants mentioned above. If CONNECTED (think accessible using a simple copy command), when a developer makes a change to a user app, the user app's files are placed directly into the repository.

If DISCONNECTED, user app files are bundled and e-mailed to a remote admin, who must drag that bundle onto a desktop shortcut which unbundles them into their repository.

DISCONNECTED can be of two types: Group or Solo, where Group implies more than one end user and Solo just one end user (the local admin).

It is important to note that this solution is easy to use for both the developer and end user. For the developer configure the three constants and rebuild the solution. Then run the initial build app (in this solution) to create the initial repository. If CONNECTED the repository is saved to its final production place. If DISCONNECTED the repository is bundled and an e-mail built (just missing TO) for a local admin who must run the final repository placement app (in this solution, or it could be on multiple web sites). User apps are placed into the repository by the developer or local admin (again depending on connection type).

Initial end user access to their app comes from via an e-mail link, from the developer, local admin or possibly the help desk. That e-mail is created by another app in this solution.

Subsequent end user access to their app is from a desktop shortcut placed on the desktop when the e-mail link is clicked.

One of the features of this solution is that when a user app is changed, the user is usually not aware. A change causes the repository to be updated with new file(s), the console app copies new files to the local profile and then runs whatever it finds in the local profile.

There is a simple way to obsolete existing user apps when needed.

Finally all three distribution types have been used in production environments. So this system has had real world tests.
