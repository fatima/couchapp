# Installing

## Ruby

To run CouchApp's Ruby uploader script, you'll need Ruby 1.8.6 or better, hopefully your package management system supports Ruby and (like Debian) also a Ruby Development package, which you'll need to build the native JSON gem etc.

You'll also [need to install RubyGems.]() I've never had an easy time doing this part of a dev-env bootstrap, so let me wish you luck. There's a nacent Python implementation, so if the Ruby depedencies aren't your style, watch [Jan's CouchApp repo](http://github.com/janl/couchapp), where he's at work on the Python scripts.

Once you've got RubyGems, (please excuse the `sudo`, it's to install the `couchapp` script in your path) run:

    git clone git@github.com:jchris/couchapp.git && cd couchapp
    gem build couchapp.gemspec
    sudo gem install couchapp-*.gem

You might have to satisfy some dependencies, especially [CouchRest](http://github.com/jchris/couchrest). (I am actively working on getting my gems house in order.)

Once this is done, run `couchapp generate relax` and generally pick up with the README.

## Python

See [Jan's CouchApp repo](http://github.com/janl/couchapp) for the latest Python action. Currently we're working to get a common set of specs. We have the Ruby specs but they are a bit clumsy with all the shelling out. I'm thinking of doing a set of JSON specs that either language can execute with a lightweight runner. We'll just do shared integration tests, at the command-line level, so each language can set about porting it's peers unit tests if there are implementation questions.