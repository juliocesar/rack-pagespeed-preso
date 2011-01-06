Pre-historic image caching technique, but a good example:

    class AddTimestampToImages < Rack::PageSpeed::Filter
      def execute! document
        document.css('img').each { |img| img['src'] += "?#{file_for(img).mtime.to_i}"}
      end
    end

Then

    use Rack::PageSpeed, :public => Sinatra::Application.public do
      add_timestamp_to_images
    end

rack-pagespeed automagically finds your class as long as you declared it somewhere before invoking.