---
layout: page
#title: Site Lab
permalink: /site-lab/
---

<div>
POSTS Index
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
	  {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
</div>
<div>
<h2>Members</h2>
{% for member in site.data.members %}
<a href="https://github.com/{{ member.github }}">
{{ member.name }}
</a>
{% endfor %}
</div>
<div>
	<h2>Books</h2>
	{% for book in site.books %}
		<h3>{{ book.title }}</h3>
		<p>{{ book.description }}</p>
		<p>{{ book.url }}</p>
		<p><a href="{{ book.amzLink }}"> Buy Now</a></p>
	{% endfor %}
</div>
<div>
	<h2>Static Files</h2>
	{% for file in site.static_files %}
		<p>{{ file.path }}</p>
	{% endfor %}
</div>
<div>
	<h2>Collection</h2>
	{% for c in site.collections %}
		<p>Docs in collection "{{ c.label }}"</p>

		{% for d in c.docs %}
			<p>{{ d.path }}</p>
		{% endfor %}

		<p> Files in collection "{{ c.label }}"</p>
		{% for f in c.files %}
		    <p>{{ f.name }}</p>
		{% endfor %}
	{% endfor %}
</div>
<div>
	<h2>Java Codes</h2>
{% highlight java linenos %}
public class PicapiApp implements CommandLineRunner {
    private static final Logger LOG = LoggerFactory.getLogger(PicapiApp.class);

    private static AppLauncher launcher = new AppLauncher();

    static AppLauncher getLauncher() {
        return PicapiApp.launcher;
    }

    static void setLauncher(AppLauncher launcher) {
        PicapiApp.launcher = launcher;
    }

    public static void main(String[] args) {
        launcher.run(args);
    }

    @Override
    public void run(String... params) throws Exception {
        LOG.info("Cmd line params: ");

        for(String param : params) {
            LOG.info("\t" + param);
        }
    }
}
{% endhighlight %}
</div>

