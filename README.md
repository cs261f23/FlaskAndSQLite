# Flask and SQLite Quickstart

This is a very simple Flask application that uses a SQLite database. After
getting this running you probably want to look at other resources.
Some links:

* All Flask documentation: https://flask.palletsprojects.com/en/2.3.x/
* Flask quickstart: https://flask.palletsprojects.com/en/2.3.x/quickstart/
* Flask tutorial: https://flask.palletsprojects.com/en/2.3.x/tutorial/
* Python sqlite3 documentation: https://docs.python.org/3/library/sqlite3.html

## Running This Example

It is good practice to use a virtual environment for a Python project. All the
libraries you use are installed into the virtual environment to avoid
cluttering your system Python installation.

This guide assumes you are working from a Unix-style command line, such as
macOS Terminal, a WSL terminal (probably Ubuntu), or Git Bash. If Python isn't
working in Git Bash, you may need to do some extra stuff. If you use Windows
CMD or Powershell the commands might need to be altered.

It also assumes you cloned this repository into
`Desktop/CS261/FlaskAndSQLite`. Modify commands as needed for your own naming
scheme.

Navigate to the repository directory with `cd`:

```
cd Desktop/CS261/FlaskAndSQLite
```

Create a virtual environment (only needs to be done once). This creates a
virtual environment in the directory `venv`. Change the last argument to change
that name if you wish:

```
python3 -m venv venv
```

Activate the virtual environment. This needs to be done every time you open a
new terminal window. You should see the name of the environment in parentheses
to the left of your prompt if you successfully activated. This will be
different in CMD and Powershell (look up tutorials for virtual environments in
Windows).

```
source venv/bin/activate
```

Install Flask:

```
pip install flask
```

Initialize the database. The "init-db" command is a custom command that is
defined within `flask_intro.py`, you can make more commands if you wish:

```
flask --app flask_intro init-db
```

Run the Flask app:

```
flask --app flask_intro run --debug
```

Open the URL (probably `http://127.0.0.1:5000`) in your browser to see the
site. Right click anywhere on the page and select "View page source" (or
whatever your browser calls it) to look at the HTML that was generated from the
template.

If you want to manually manipulate the database during development you can use
the `sqlite3` command line utility (included in macOS and WSL Ubuntu, not sure
about other Windows environments). Press `ctrl-d` to exit when you are done:

```
$ sqlite3 db.sqlite
SQLite version 3.42.0 2023-05-16 12:36:15
Enter ".help" for usage hints.
sqlite> INSERT INTO item(name, quantity) VALUES('Lamp', 5);
sqlite> 
```

Now that an additional item has been inserted into the database, refresh the
page to see the changes. Running the "init-db" command above will reset the
database again.

Look through all the files in this project to get a better sense of what is
going on, and be sure to check out the official Flask tutorial as well.

If you use VS Code or an IDE such as Pycharm you can use the terminal there,
and you should be able to configure it to know about your virtual environment
and activate it automatically.
