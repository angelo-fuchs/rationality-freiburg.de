# rationality-freiburg.de

Static website made with [Hugo](https://gohugo.io/).

Visit [www.rationality-freiburg.de](https://www.rationality-freiburg.de)


# Contributing

## Easy way

The simplest way of contributing (e.g. if you found a mistake in one of the
posts) is to simply edit the .md (MarkDown) documents you can find under the
`website/content/en/` directory. Then simply send a pull request.

To create a new post you can copy an existing document or folder (basically
only needed if the post contains images) and adapt as needed.

To create or update German translations you can use
[DeepL](https://www.deepl.com/translator) and modify/create corresponding files
under `website/content/de/` .


## Using hugo

This website is created using the static site generator
[Hugo](https://gohugo.io/). If you want to contribute frequently or want to
preview your post you can [install
Hugo](https://gohugo.io/getting-started/installing/) and then:

```bash
cd website
hugo new posts/some-examples.md
# edit content/posts/en/some-example.md
# optionally edit content/posts/de/some-example.md for the German translation
hugo server -D
```

Open http://localhost:1313 in a browser and check your post.

[Learn more about Hugo](https://gohugo.io/getting-started/quick-start/).


# Adding Events

```bash
cd website
NAME=2023-01-06-cognitive-biases
hugo new events/${NAME}/index.md
vim content/en/events/${NAME}/index.md
cp ~/Desktop/cover.png content/en/events/${NAME}/cover.png
cp -r content/en/events/${NAME}/ content/de/events/
vim content/{en,de}/events/${NAME}/index.md
git add content/{en,de}/events/${NAME}/
git commit -m "Add event ${NAME}"
```

To edit an existing event (e.g. because initially there was no theme).

```bash
cd website
git mv content/en/events/2023-02-17-meetup/ content/en/events/2023-02-17-exercising/
git mv content/de/events/2023-02-17-meetup/ content/de/events/2023-02-17-exercising/
vim content/{en,de}/events/2023-02-17-exercising/index.md
```

Add an `aliases` section in each case:

```yaml
aliases:
  - /events/2023-02-17-meetup/
```

```yaml
aliases:
  - /de/termine/2023-02-17-meetup/
```

Edit the title, description, slug and content in each case.
