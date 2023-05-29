Request is designed to be the simplest way possible to make http calls. It supports HTTPS and follows redirects by default.

const request = require('request');
request('http://www.google.com', function (error, response, body) {
  console.error('error:', error); // Print the error if one occurred
  console.log('statusCode:', response && response.statusCode); // Print the response status code if a response was received
  console.log('body:', body); // Print the HTML for the Google homepage.
});

Streaming
You can stream any response to a file stream.

request('http://google.com/doodle.png').pipe(fs.createWriteStream('doodle.png'))
You can also stream a file to a PUT or POST request. This method will also check the file extension against a mapping of file extensions to content-types (in this case application/json) and use the proper content-type in the PUT request (if the headers don’t already provide one).

fs.createReadStream('file.json').pipe(request.put('http://mysite.com/obj.json'))
Request can also pipe to itself. When doing so, content-type and content-length are preserved in the PUT headers.

request.get('http://google.com/img.png').pipe(request.put('http://mysite.com/img.png'))
Request emits a "response" event when a response is received. The response argument will be an instance of http.IncomingMessage.