This is currently a shell that provides a vagrant provided docker host for
trying different Elixir configs out on. The tutorial followed to get 
started was from:
http://blog.zenika.com/2014/10/07/setting-up-a-development-environment-using-docker-and-vagrant/

THe goal is to obtain a consistent docker host OS between Windows dev
machines and production Linux hosts. Here's a diagram from the article:

http://blog.zenika.com/wp-content/uploads/2015/07/diagr3.png

To provision an run the docker image, run:
    
    One time to get the vert-x examples
    $ vagrant docker-run vertxdev-src -- git clone https://github.com/vert-x/vertx-examples.git

    Each time to start the env
    $ vagrant up
    $ curl localhost:8080
    
    To teardown the env
    $ vagrant destroy vertxdev-src
    
    Note: this errors out because of a shared directory issue, need to
    figure out why. Using some combination of the following hepls:
    $ vagrant global-status
    $ vagrant destroy [id]
    $ vagrant global-status --prune
    