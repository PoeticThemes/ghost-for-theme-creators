# Ghost for Theme Creators
Develop, test, and deliver high-quality themes for Ghost with **Ghost for Theme Creators**, a Docker image that helps you develop and test your Ghost themes with **over 20 unit tests** in the form of posts and pages.

[![Ghost for Theme Creators](https://i.imgur.com/PXAtEmz.png)](https://github.com/PoeticThemes/ghost-for-theme-creators/stargazers)

[![Ghost for Theme Creators](https://i.imgur.com/on39dIl.png)](https://github.com/PoeticThemes/ghost-for-theme-creators/stargazers)

# List of tests
These tests are designed to help you find bugs in your themes, and to ensure they are robust enough to handle a variety of edge cases.

- HTML cards
- Featured post
- Featured post (no image)
- Special characters
- YouTube cards
- Vimeo cards
- Image cards
- Long content
- Nested and mixed lists
- Many tags
- No title, no content, no image
- Untitled post
- No content
- Long title
- Error page
- Post (no image)
- Page
- Page (no image)
- Gallery cards
- Embedded items
- Bookmarks

# Adding it to your theme
1. Create a ***docker-compose.yml*** file in your theme's project directory:
```
# This docker-compose.yml file is intended for easy development of this theme.
version: '3'
services:
  ghost-for-theme-creators:
    image: poeticthemes/ghost-for-theme-creators
    ports:
      - 80:2368
    volumes:
      # Mount source code into casper directory to set it as the current theme:
      - ./:/var/lib/ghost/content/themes/casper/
    restart: always
    environment:
      - url=http://localhost
      - NODE_ENV=development
```
2. Make sure **Docker Desktop** is running and in your theme's project directory run `docker-compose pull && docker-compose up -d`
3. Open `http://localhost` on your web browser and start developing.

For a real example check the ***docker-compose.yml*** file in the [Boo for Ghost](https://github.com/PoeticThemes/boo) theme.

# How to request more tests
Simply [open a new issue here](https://github.com/PoeticThemes/ghost-for-theme-creators/issues/new) and exmplain the test you want to implement with as much details as possible.
