# BinDB

BinDB it's a library for Grey Hack Game that allow you to create a password-protected binary database inaccessible to third parties and without need parsers or something like that.

## How to use it

At the top of everything to your code import bindb.src with the "import_code" method.

    import_code("/absolute/path/of/bindb.src")

After that, create a connection with your db with the following example method:

    myDb = BinDB.connect("dbname", "dbpassword", ["table1", "table2"], "/home/tuonux")

## Availables methods

### BinDB.connect(dbname, dbpassword, tablesArray, dbDirectory)

Instantiate the connection with your binary database

Example Usage:

    mrRobotDb = BinDB.connect("mrRobot", "mypassword", ["users", "mails", "banks"], "/home/<user>")

### BinDB.insert(table, data)

Push the new data in your table

Example Usage:

    mrRobotDb.insert("users", {"name": "Elliot", "surname": "Alderson"})
    mrRobotDb.insert("users", {"name": "Tyrell", "surname": "Wellick"})
    mrRobotDb.insert("users", {"name": "Angela", "surname": "Moss"})
    mrRobotDb.insert("users", {"name": "Joanna", "surname": "Olofsson"})
    mrRobotDb.insert("users", {"name": "Gideon", "surname": "Goddard"})

### BinDB.fetch(table)

Fetch all the rows of your table

Example Usage:

    for user in mrRobotDb.fetch("users")
         print(user.name)
    end for

### BinDB.fetchOne(table, id)

Fetch a row by the index

Example Usage:

    userElliot = mrRobotDb.fetchOne("users", 1)

### BinDB.fetchBy(table, key, value)

Fetch a row by a combination of key -> value

Example Usage:

    userElliot = mrRobotDb.fetchBy("users", "name", "Elliot")

### BinDB.update(table, id, data)

Update a row by the index

Example Usage:

    mrRobotDb.update("users", 1, {"name": "Mr.", "surname": "Robot"})

### BinDB.delete(table, id)

Delete a row by the index

Example Usage:

    mrRobotDb.delete("users", 5)

### BinDB.read()

Read binary buffer ( used in rare case )

Example Usage:

    mrRobotDb.read()

### BinDB.write()

Update binary database buffer

Example Usage:

    mrRobotDb.insert("users", {"name": "Elliot", "surname": "Alderson"})
    mrRobotDb.write()

### BinDB.wipe()

Clear and delete the database

Example Usage:

    mrRobotDb.wipe()

### BinDB.printTable(table, labels)

Utility function that print your table with formatted columns

Example Usage:

    mrRobotDb.printTable("users", {"name": "Name", "surname": "Surname"})

### Methods chain

For your convenience, if you want you can chain the methods

## License

    MIT License

    Copyright (c) 2023 tuonux

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.