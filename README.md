Lab 3 – Video Script
Name: Mahit KC
Lab: INET 2005 – Lab 3

INTRODUCTION (Start of Video)
Narration:
"Hello, my name is Mahit KC, and this is my demonstration for INET 2005 – Lab 3.
In this lab, we are working with PHP and MySQL to perform displaying, inserting, updating, deleting, and validating data.
I’ll go step-by-step for each part of the lab."

PART A – Displaying MySQL Data in PHP
Step 1 – Show First 10 Rows of Film Table
Question:
"How can we display the first 10 films from the database in PHP?"

Answer:
"We can query the film table with LIMIT 10, then loop through the results and display them in an HTML table."

Lines to Show:

// Line 12–27
$sql = "SELECT * FROM film LIMIT 10";
$result = mysqli_query($conn, $sql);

if (mysqli_num_rows($result) > 0) {
    echo "<table border='1'>";
    echo "<tr><th>ID</th><th>Title</th><th>Description</th><th>Year</th><th>Length</th></tr>";
    while($row = mysqli_fetch_assoc($result)) {
        echo "<tr>";
        echo "<td>" . $row['film_id'] . "</td>";
        echo "<td>" . $row['title'] . "</td>";
        echo "<td>" . $row['description'] . "</td>";
        echo "<td>" . $row['release_year'] . "</td>";
        echo "<td>" . $row['length'] . "</td>";
        echo "</tr>";
    }
    echo "</table>";
} else {
    echo "No films found";
}
Narration:
"This query retrieves the first 10 films from the film table. We then display them in a table with proper headers."

Step 2 – Search Films
Question:
"How can we search films based on a description?"

Answer:
"We use a LIKE query in MySQL with % wildcards to search for matching descriptions."

Lines to Show:

// Line 20–22 in search.php
$search = mysqli_real_escape_string($conn, $_POST['search']);
$sql = "SELECT * FROM film WHERE description LIKE '%$search%' LIMIT 20";
Narration:
"When the user types a search term, the query returns up to 20 results containing that term in their description."

Step 3 – Last 10 Actors
Question:
"How can we show only the last 10 actors?"

Answer:
"We can use ORDER BY actor_id DESC LIMIT 10 to sort actors by newest first and limit results to 10."

Lines to Show:

// Line 30–45 in actors.php
$sql = "SELECT * FROM actor ORDER BY actor_id DESC LIMIT 10";
$result = mysqli_query($conn, $sql);

if (mysqli_num_rows($result) > 0) {
    echo "<table border='1'>";
    echo "<tr><th>ID</th><th>First Name</th><th>Last Name</th></tr>";
    while($row = mysqli_fetch_assoc($result)) {
        echo "<tr>";
        echo "<td>" . $row['actor_id'] . "</td>";
        echo "<td>" . $row['first_name'] . "</td>";
        echo "<td>" . $row['last_name'] . "</td>";
        echo "</tr>";
    }
    echo "</table>";
} else {
    echo "No actors found";
}
Narration:
"This displays the latest 10 actors added to the table."

PART B – Insert / Update / Delete Data
Step 1 & 2 – Insert Actor
Question:
"How can we add a new actor to the database?"

Answer:
"We make an HTML form to collect first name and last name, then use INSERT INTO SQL to store the data."

Lines to Show:

// Line 15–20 in actors.php
$first = mysqli_real_escape_string($conn, $_POST['first_name']);
$last = mysqli_real_escape_string($conn, $_POST['last_name']);
$sql = "INSERT INTO actor (first_name, last_name) VALUES ('$first', '$last')";
Narration:
"When submitted, this form sends the data to PHP which inserts it into the actor table."

Step 4 – Delete Actor
Question:
"How can we delete an actor by ID?"

Answer:
"We create a form where the user enters an actor’s ID. The PHP script then deletes the record using DELETE FROM."

Lines to Show:

// Line 10–16 in delete.php
$actor_id = mysqli_real_escape_string($conn, $_POST['actor_id']);
$sql = "DELETE FROM actor WHERE actor_id = $actor_id";
Narration:
"This deletes the specified actor and shows a message if successful."

Step 5 – Update Actor
Question:
"How can we update an actor’s name?"

Answer:
"We first display the current actor details in a form, then on submission we update using UPDATE SET."

Lines to Show:

// Line 15–18 in update.php
$sql = "UPDATE actor SET first_name = '$first_name', last_name = '$last_name' WHERE actor_id = $actor_id";
Narration:
"This updates the actor’s first and last name in the database."

PART C – JavaScript Form Validation
Form Setup
Question:
"How can we validate a form before submission?"

Answer:
"We use JavaScript to check that all fields are filled and that the terms checkbox is checked."

Lines to Show:

// Line 3–24 in script.js
inputs.forEach(input => {
    input.addEventListener("focus", () => {
        input.style.backgroundColor = "yellow";
        input.style.fontStyle = "italic";
        label.style.textDecoration = "underline";
    });

    input.addEventListener("blur", () => {
        input.style.backgroundColor = "";
        input.style.fontStyle = "";
        label.style.textDecoration = "";
    });
});

// Line 26–44
form.addEventListener("submit", function(event) {
    let valid = true;

    inputs.forEach(input => {
        if (input.value.trim() === "") {
            input.style.border = "2px solid red";
            valid = false;
        } else {
            input.style.border = "1px solid #ccc";
        }
    });

    if (!terms.checked) {
        termsError.style.display = "inline";
        valid = false;
    } else {
        termsError.style.display = "none";
    }

    if (!valid) {
        event.preventDefault();
    }
});
Narration:
"This script adds styling when typing, and checks for missing fields or unchecked terms before allowing form submission."

Closing Statement
"This completes my Lab 3 demonstration for INET 2005. Thank you."

If you want, I can now make a table version of this script with questions, answers, narration, and line numbers so it’s even easier for you to record your video without missing anything.
