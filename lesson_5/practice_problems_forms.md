# Practice Problems: Forms

1. Create a contact form that collects the user's first name, last name, email address, and phone number. Be sure to require all inputs and to use appropriate input types and labels. Prevent Chrome and iOS Safari from doing any auto-actions (e.g., autocomplete and autocorrect) on the email input.

For this problem, don't use a definition list to organize your form. We'll do that in the next question.

Answer: 

```html
<form action="#" method="post">
  <label for="first_name">First Name</label>
  <input type="text" name="first_name" id="first_name" required>
  
  <label for="last_name">Last Name</label>
  <input type="text" name="last_name" id="last_name" required>

  <label for="email">Email</label>
  <input type="email" name="email" id="email" autocomplete="off" autocorrect="off" autocapitalize="none" required> 

  <label for="phone">Phone</label>
  <input type="tel" name="phone" id="phone" required>

  <input type="submit" value="Send">
</form>
```

#

2. Convert the HTML from the previous problem to use a single description list to pair each label and input control.

Answer: 
```html
<form action="#" method="post">
  <fieldset>
    <dl>
      <dt><label for="first-name">First Name</label></dt>
      <dd>
        <input type="text" name="first-name" id="first-name" required>
      </dd>

      <dt><label for="last-name">Last Name</label></dt>
      <dd><input type="text" name="last-name" id="last-name" required></dd>

      <dt><label for="email">Email Address</label></dt>
      <dd>
        <input type="email" name="email" id="email" required
               autocomplete="off" autocorrect="off" autocapitalize="none">
      </dd>

      <dt><label for="phone">Phone Number</label></dt>
      <dd><input type="tel" name="phone" id="phone" required></dd>
    </dl>

    <input type="submit" value="Send">
  </fieldset>
</form>
```

#

3. Add a select box to your solution from the previous problem that lets the user select a phone type given the options "home," "business," and "mobile." Make sure you pre-select the "home" option.

Answer: 

```html
<dt><label for="phone-type">Phone Type</label></dt>
<dd>
  <select name="phone-type" id="phone-type">
    <option value="home" selected>Home</option>
    <option value="business">Business</option>
    <option value="mobile">Mobile</option>
  </select>
</dd>
```

#

4. Add a message box to your solution from the previous problem that lets the user enter an optional multi-line message. The message box should allow around six lines of text of up to about 80-characters each.

Answer:

```html
<dt><label for="message">Message</label></dt>
<dd><textarea id="message" name="message" rows="6" cols="80"></textarea></dd>
```

# 

5. Add some placeholder text to the phone number input that shows the format you expect to see. (For instance, ###-###-####.)

Answer: 

```html
<dt><label for="phone">Phone Number</label></dt>
<dd>
  <input type="tel" name="phone" id="phone" placeholder="###-###-####"
         required>
</dd>
```

#

6. Add some placeholder text to the message box, e.g., `Type your message here.`

Answer: 

```html
<dt><label for="message">Message</label></dt>
<dd>
  <textarea id="message" name="message" rows="6" cols="80" placeholder="Type your message here."></textarea>
</dd>
```

**Full code for previous problems**
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Practice Problems: Forms</title>
    <meta charset="utf-8">
  </head>
  <body>
    <form action="#" method="post">
      <fieldset>
        <dl>
          <dt><label for="first_name">First Name</label></dt>
          <dd><input type="text" name="first_name" id="first_name" required></dd>
          
          <dt><label for="last_name">Last Name</label></dt>
          <dd><input type="text" name="last_name" id="last_name" required></dd>

          <dt><label for="email">Email</label></dt>
          <dd><input type="email" name="email" id="email" autocomplete="off" autocorrect="off" autocapitalize="none" required></dd> 

          <dt><label for="phone">Phone</label></dt>
          <dd>
            <input type="tel" name="phone" id="phone" placeholder="(###) ###-####" required>
          </dd>
          
          <dd>
            <select name="phone_type" id="phone_type">
              <option value="home" selected>Home</option>
              <option value="cell">Cell</option>
              <option value="work">Work</option>
            </select>
          </dd>

          <dt><label for="message">Message</label></dt>
          <dd>
            <textarea id="message" name="message" rows="6" cols="80" placeholder="Type your message here."></textarea>
          </dd>
          
          <dd><input type="submit" value="Send"></dd>
        </dl>
      </fieldset>
    </form>
  </body>
</html>
```

#

7. Create a search form with three items:

- a field for the search term,

- a group of three controls to select precisely one from the list "TV," "Movies," and "Music,"

- a Search button (use the button tag, not the obsolete `<input type="button">` tag).

The form doesn't have to do anything when submitted. Don't use a description list for this problem.


Answer:
```html
<form action="#" method="get">
  <fieldset>
    <label>
      Search for
      <input type="search" name="query" id="query">
    </label>

    <label>
      <input type="radio" name="filter" value="tv" required>
      TV
    </label>

    <label>
      <input type="radio" name="filter" value="movies" required>
      Movies
    </label>

    <label>
      <input type="radio" name="filter" value="music" required>
      Music
    </label>

    <button name="search">Search</button>
  </fieldset>
</form>
```

#

8. Create a review form with a single control that lets the user select from the movies "Looper," "Frozen," and "Tommy Boy,"

then add a numeric rating field that the user can set to any integer from 1-5. 

Next, add a toggle control to add the movie to your favorites list. 

Enable the toggle control by default. 

Lastly, add a submit button.


Answer:
```html
<form action="#" method="post">
  <fieldset>
    <label for="title">
      Movie
      <select name="title" id="title">
        <option disabled selected>Choose Movie</option>
        <option>Looper</option>
        <option>Frozen</option>
        <option>Tommy Boy</option>
      </select>
    </label>

    <label for="rating">
      Rating
      <input type="number" name="rating" id="rating" min="1" max="5" placeholder="(1-5)">
    </label>

    <label>
      <input type="checkbox" name="favorite" checked>
      Add to my favorites
    </label>

    <input type="submit" value="Rate movie">
  </fieldset>
</form>
```

#

9. Add the movie "Alien" to the end of the drop-down list and make it the initial selection when displaying the form.

Answer: 

```html
<select name="title" id="title">
  <option value="Looper">Looper</option>
  <option value="Frozen">Frozen</option>
  <option value="Tommy Boy">Tommy Boy</option>
  <option value="Alien" selected>Alien</option>
</select>
```

#

10. Update your solution to show all four possible choices at once.

Answer:

```html
<select name="title" id="title" size="4">
  <option value="Looper">Looper</option>
  <option value="Frozen">Frozen</option>
  <option value="Tommy Boy">Tommy Boy</option>
  <option value="Alien" selected>Alien</option>
</select>
```

#

11. Create a form that filters news articles by a single category and any number of selected tag words. 

Use radio buttons for the news category and checkboxes for the tags. 

Make sure you use the get method to allow the user to save and share the filtered URL.

- Categories: 
  - Core, Plugins and Libraries, Conventions, Reviews, Opinion, People
  - Tags: HTML, CSS, Javascript, Ruby, Rails, Python, Django

For this problem, use the container-style label tag (without the for attribute). 

Use an unordered list instead of a description list for both the categories and tags.


Answer:

```html
<form action="#" method="get">
  <fieldset>
    <h1>Category</h1>
    <ul>
      <li>
        <label>
          <input type="radio" name="category" value="core" required>
          Core
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="category" value="plugins" required>
          Plugins and Libraries
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="category" value="conventions" required>
          Conventions
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="category" value="reviews" required>
          Reviews
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="category" value="opinion" required>
          Opinion
        </label>
      </li>
      <li>
        <label>
          <input type="radio" name="category" value="people" required>
          People
        </label>
      </li>
    </ul>

    <h1>Tags</h1>
    <ul>
      <li>
        <label>
          <input type="checkbox" name="html">
          HTML
        </label>
      </li>
      <li>
        <label>
          <input type="checkbox" name="css">
          CSS
        </label>
      </li>
      <li>
        <label>
          <input type="checkbox" name="javascript">
          Javascript
        </label>
      </li>
      <li>
        <label>
          <input type="checkbox" name="ruby">
          Ruby
        </label>
      </li>
      <li>
        <label>
          <input type="checkbox" name="rails">
          Rails
        </label>
      </li>
      <li>
        <label>
          <input type="checkbox" name="python">
          Python
        </label>
      </li>
      <li>
        <label>
          <input type="checkbox" name="django">
          Django
        </label>
      </li>
    </ul>

    <input type="submit" value="Filter">
  </fieldset>
</form>
```

#

12. 

Convert the radios and checkboxes in the filter form to select lists. 

Let the user select any number of tags, and ensure the selection box is large enough that she can see several choices at once. 

Use description lists to organize the form elements.

```html
<form action="#" method="get">
  <fieldset>
    <dl>
      <dt><label for="category">Category</label></dt>
      <dd>
        <select name="category" size="5" id="category">
          <option value="core">Core</option>
          <option value="plugins">Plugins and Libraries</option>
          <option value="conventions">Conventions</option>
          <option value="reviews">Reviews</option>
          <option value="opinion">Opinion</option>
          <option value="people">People</option>
        </select>
      </dd>

      <dt><label for="tags">Tags</label></dt>
      <dd>
        <select name="tags" id="tags" size="5" multiple>
          <option value="html">HTML</option>
          <option value="css">CSS</option>
          <option value="javascript">Javascript</option>
          <option value="ruby">Ruby</option>
          <option value="rails">Rails</option>
          <option value="python">Python</option>
          <option value="django">Django</option>
        </select>
      </dd>
    </dl>

    <input type="submit" value="Filter">
  </fieldset>
</form>
```

#

13. Provide the user with a way to reset the filter form.

Answer: 
```html
<input type="reset">
```

#
#
