You may have noticed this before

    store :memcached
    
Bundled assets can be stored in disk or memcached (Heroku friendly). Hash-like syntax to specify details:

    store :disk => Sinatra::Application.public
    # assets are served uber fast if you do this
    
Storage engines can be added. Must obey key-value Hash rules. And yes, a regular Hash also works:

    store({}) # BAM!