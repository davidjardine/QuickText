# ROADMAP

The plans for this project may change but you can check out the  current roadmap below.  

## Phase One

The goal of Phase One is to create a set of CSS files that developers would be able to easily copy / clone and utilize in a variety of common and simple scenarios. The goal of QuickText isn't to support developers working on giant dynamic sites, but to be an alternative to starting from blank files for small one-off sites. 

For example, if a web developer needs to create a site for a client that wants a publisher / author aesthetic, there would be a CSS file to download and (so long as they're using an HTML file that is setup according to QuickText parameters) the styles would automatically apply to their site.

### To-Do

The majority of tasks in Phase One are creating templates. The HTML templates are mainly to show users what the stylesheets look like in different use cases, but can also be cloned alongside the CSS files as a starting point for a new page. The CSS templates are the actual implementations of the themes.

- [x] Establish QuickText DOM Guidelines
- [x] Document guidelines for usage (see README.md and TAGS.md)
- [x] HTML Sample Page (uses nearly every HTML tag to show how the styles are applied from one theme to the next)
- [ ] HTML Landing Page Template
- [ ] HTML Blog Post / Article Template
- [ ] HTML Gallery Page Template
- [ ] HTML Products/Services Page Template
- [x] Basic CSS Configuration file (variables)
- [x] "Vanilla" Theme stylesheet
- [ ] "Corporate" Theme stylesheet
- [ ] "Author" or "Publisher" Theme stylesheet
- [ ] "Sci-Fi" Theme stylesheet



## Phase Two

The goal of Phase Two is to have a full library of CSS files that not only provide ready-made templates for most common website styles and layouts, but also includes a set of "add-on" styles that can be incorporated into any QuickText template for advanced use cases (i.e. complex animations).  

### To-Do

- [ ] THEMES.md file to explain usage and styles for each theme
- [ ] Complete theme library
- [ ] 
- [ ] Add advanced variables (complex gradients, transform functions, animations)

## Phase Three

The goal of Phase Three is to extend the QuickText functionality to a publicly accessible website where anyone from beginner to advanced can input the parameters of the site they want to build and the back end PHP scripts will generate the templates and files they need. 

Additionally it would be nice if it can be setup to also be self-hostable so that it can be used without internet connection.

### To-Do

- [ ] Setup web server for public access
- [ ] Implement basic PHP script functionality (choose which templates you want and it downloads them for you)
- [ ] Implement advanced PHP scripts to allow for customizing templates with the available add-ons and advanced variables