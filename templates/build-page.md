

# Building a Page

## Example Page Template

We believe the easiest way to learn how to use Kilvin CMS' templating is by example, so we are going to walk you through a very basic set of templates to help you get the gist of how they work.

Here is an example *homepage* template:

```
{% extends "_page" %}

{% set page_title = 'My Cool Site' %}

{% block main_content %}

	{% for entry in Plugins.load('Weblogs.Entries').with('fields').mostRecent(5).get() %}
		{{ include('_entry') }}
    {% endfor %}

{% endblock main_content %}
```

Incredibly simple, right? Hardly looks like anything at all! That is the power of Twig.

The first line says that this template is an [extension](https://twig.symfony.com/doc/2.x/tags/extends.html) of the `_page` template. That means that this template will first create its own content and then that content will be inserted into the `_page` template. The `_page` template can contain all of the basic output for a page like the CSS, Javascript, and a standard HTML structure. This is helpful if the general outline of each page is the same with only the main content changing based off the URL. A very simple `_page` page might look like this:

```
<html>
	<head>
		<title>{{page_title}}</title>
		<link rel="stylesheet" href="/site.css">
	</head>

	<body>
		<div class="row">
			<div class="eight columns">
				{% block main_content %}
					<p>Default Main Content</p>
				{% endblock main_content %}
			</div>
		</div>
	</body>
</html>
```

For the *homepage* template, we are setting a variable called `page_title` that will be the title of the HTML page. We are also creating a [block](https://twig.symfony.com/doc/2.x/functions/block.html) of content called `main_content` and this block of content will be inserted into the '_page' template and replace the default `main_content` block already there. This is the basic idea of template inheritance: one template inherits the data from another.

The 'main_content' block in the *homepage* template is built by calling the 'Plugins' facade and loading up the Weblogs Entries class. We then request the five most recent entries from this class and loop through the results with the [for tag](https://twig.symfony.com/doc/2.x/tags/for.html).

So. We now have five entries and are looping through each one. On each loop, we both set an 'entry' variable and include a new template called '_entry'.  This '_entry' template contains the HTML for outputting the entry as HTML. Thanks to the power of inheritance, it automatically receives the `entry` variable without us doing anything!

Here is an example '_entry' template:

```
<article class="entry">
    <header class="entry-header">
        <h2 class="entry-title">
            <a href="{{ entry.url_title }}">{{ entry.fields.title }}</a>
        </h2>

        <div class="entry-meta">
            {{ entry.entry_date | date('M j, Y') }}
            •
            by {{ entry.author.screen_name }}
        </div>
    </header>

    <div class="entry-content">
    	{{ parsedown(entry.fields.body) | raw }}
    </div>
</article>
```

The `entry` variable has data attached to it, like the `url_title`, `entry_date`, and `fields` of the entry. You can just place those variables in the HTML and output them.




