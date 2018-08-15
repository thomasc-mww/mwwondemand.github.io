```ruby
require 'net/http'

# api_user Login API KEY (POST )
def send_request
  uri = URI('https://api.mwwondemand.com/api/login')

  # Create client
  http = Net::HTTP.new(uri.host, uri.port)

  # Create Request
  req =  Net::HTTP::Post.new(uri)
  # Add headers
  req.add_field "Content-Type", "application/vnd.api+json"
  # Add headers
  req.add_field "Authorization", "auth-key=S@mpl3!"
  # Add headers
  req.add_field "Accept", "application/vnd.api+json; version=1"

  # Fetch Request
  res = http.request(req)
  puts "Response HTTP Status Code: #{res.code}"
  puts "Response HTTP Response Body: #{res.body}"
rescue StandardError => e
  puts "HTTP Request failed (#{e.message})"
end
```
