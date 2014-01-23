Examples and API documentation for Mapbox.js live in the `docs` subdirectory.
It's generated as a static site using [jekyll](http://jekyllrb.com/).

## Examples

* The structure of an example is `_posts/examplename/0100-01-01-examplename.html`.
* All files necessary for examples must be in their own directory.
* Examples use hosted mapbox.js, with the latest deployed version.
* Use the [AirBnb style guide styles](https://github.com/airbnb/javascript), but with 4 spaces not 2.
* Example code should pass [jshint](http://jshint.com/)
* Where possible, examples should be cross-browser and touch-compatible.
* Use long, descriptive names for variables.
* Add comments for pitfalls where users might run into problems, and for parts of the code that
  users will need to modify to get things working.

### Creating a new Example

To create a new example, first get jekyll running

```sh
git clone git@github.com:mapbox/mapbox.js.git
cd mapbox.js/docs
jekyll serve -w -p 4000
```

Edit the site. Existing examples [are located here](https://github.com/mapbox/mapbox.js/tree/master/docs/_posts/examples/v1.0.0) -
copy one to a new file with the same naming convention to start a new example. Test your new example
by going to http://localhost:4000/mapbox.js/ and finding and using it.

When you're done,

```sh
git add _posts/...newexample
git commit -m "Added a new example, showing off XYZ"
git push origin master
```

## API Documentation

The API documentation is a Jekyll site in the `docs` subdirectory. It is fed by
`API.md`. To rebuild the docs and serve the Jekyll site:

```sh
./docs/build.sh v1.6.0
cd docs && jekyll serve
```

### Style Conventions

* Heading - h3 for functions, h2 for object creation, h1 for topics
* Short description. For functions, this should start with a verb, like
  'Set the center of the map.'
* Arguments, if any
* Return value
* Example, in 4-indent

## Updating the site to the latest deployed version of mapbox.js:

* The version tag is updated in the `_config.yml` file under `version:`.
* Rebuild the docs: `./docs/build.sh VERSION`
* Each example should be tested against the version change.
