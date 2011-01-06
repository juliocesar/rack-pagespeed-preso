# rack-pagespeed vs modpagespeed (2)

rack-pagespeed:

    use Rack::PageSpeed, :public => Sinatra::Application.public do
      store :memcached
      combine_javascripts
      combine_css
      inline_javascripts :max_size => 1500
      inline_css :max_size => 1000
    end
    
modpagespeed:

Apache config with horrible directives. A.K.A. stab yourself in the eye.