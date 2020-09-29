```ruby
require 'net/http'

# Create Webhook (POST )
def send_request
  uri = URI('https://api.mwwondemand.com/api/webhooks')

  # Create client
  http = Net::HTTP.new(uri.host, uri.port)
  body = "{
  \"data\": {
    \"type\": \"webhooks\",
    \"attributes\": {
      \"url\": \"http://test\"
    }
  }
}"

  # Create Request
  req =  Net::HTTP::Post.new(uri)
  # Add headers
  req.add_field "Content-Type", "application/vnd.api+json"
  # Add headers
  req.add_field "Authorization", "<BEARER_TOKEN>"
  # Add headers
  req.add_field "Accept", "application/vnd.api+json;version=1"
  # Set body
  req.body = body

  # Fetch Request
  res = http.request(req)
  puts "Response HTTP Status Code: #{res.code}"
  puts "Response HTTP Response Body: #{res.body}"
rescue StandardError => e
  puts "HTTP Request failed (#{e.message})"
end
```
