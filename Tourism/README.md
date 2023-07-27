# Week 4 Assessment

### Setup
* In Package Manager Console
* `drop-database` and then
* `update-database`

Run the following script in pgAdmin in the Tourism Database:
<section class="answer">
<h3>SQL Script</h3>

<pre>
INSERT INTO states (name, abbreviation, time_zone)
VALUES 
	('Iowa', 'IA', 'Central'),
	('Texas', 'TX', 'Central'),
	('Colorado', 'CO', 'Mountain'),
	('Virginia', 'VA', 'Eastern'),
	('Oregon', 'OR', 'Eastern'),
	('North Carolina', 'NC', 'Eastern'),
	('British Columbia', 'BC', 'Pacific');

INSERT INTO cities (name, state_id)
VALUES 
	('Ames', 1),
	('Des Moines', 1),
	('Houston', 2),
	('Dallas', 2),
	('Austin', 2),
	('Denver', 3),
	('Boulder', 3),
	('Aurora', 3),
	('Richmond', 4),
	('Roanoke', 4),
	('Alexandria', 4),
	('Portland', 5),
	('Salem', 5),
	('Raleigh', 6),
	('Kill Devil Hills', 6),
	('Charlotte', 6),
	('Vancouver', 7),
	('Victoria', 7);
</pre>

</section>

## Exercise

Your goal for this assessment is to have an application that allows a user to do the following:
1. Edit an existing State using a pre-populated form. //
1. Filter states by time zone using a link on the State Index page. //
1. Delete a state using a button on the State Index page. //

Create a separate branch for each exercise. Merge each branch into `main` after completing each exercise.

### Editing a State (5 points) //

Update the application so that a user can edit an existing State using a pre-populated form.
* e.g. The time zone for `Oregon` should be changed to `Pacific`.
* Do not break any currently passing tests.

Note: Be sure to merge this branch into `main`!

### Filter States by Time Zone (5 points)

Update the application so that a user can filter States by time zone using links on the State Index page.
* Include the following links: `Eastern`, `Central`, `Mountain`, `Pacific`, `Clear Filter`.
	* The application should only display States in the selected time zone.
	* The `Clear Filter` link should display all States.
* e.g. Filtering on `Central` should display the states of `Iowa` and `Texas`.
* Do not break any currently passing tests.

Note: Be sure to merge this branch into `main`!

### Delete a State (5 points)

Update the application so that the user can delete a State using a button on the State Index page.
* The deleted state should no longer appear on the State Index page.
* Deleting a state should also delete all cities in that state.
* e.g. `British Columbia` is not a U.S. state. It should be deleted.
* Do not break any currently passing tests.

Note: Be sure to merge this branch into `main`!

## Questions (5 points)

Edit this file with your answers.

1. What is the difference between `POST` and `PUT`?
	* POST is the method that will CREATE a resource, whereas PUT would UPDATE an entire resource.
    	* POST is the method that we will be using, as PUT is not supported by most applications. POST can also be used to update, and delete resources.

2. What is the purpose of `ViewData`?
	* ViewData is something like a dictionary, as in we can assign a value to ViewData[] in our controller, and use it in our View.
    	* I think of it as another way to pass information to the view without only relying on return in the action

3. If the State model of our Tourism application also has a field for `Region` (e.g. `Midwest`, `South`, etc.), what might the url be if want to filter for States in both the South region and Eastern time zone?
	* /states?region=midwest&timezone=central
	* the ? represents the start of a query, and the & shows that we are filtering again.

4. What is the purpose of the `.Remove()` method in the controller code? What do we need to pass in as a parameter when calling `.Remove()`?
	* .Remove acts as our DESTROY or DELETE method, so when .Remove() is being called, we are passing in a resource that needs to be deleted, for instance in our MoviesMVC, we would: _context.Movies.Remove(movie).

5. If you wanted to improve the UI of the State Index page, what would be the filepath of the CSS file you need to create? (Hint: to find the full path of a project file, right-click the file in Solution Explorer and select `Copy Full Path`. You can then paste the path elsewhere.)
	* \Launch_8485-bs\Tourism\Views\States\StyleSheet.cshtml.css

## Rubric

This assessment has a total of 20 points.  A score of 15 or higher is a pass.

As a reminder, this assessment is for students and instructors to determine if there are any areas that need additional reinforcement!
