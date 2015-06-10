
# Receiving a POST from a Push Queue

Your route or controller can get the post this way

~~~
$request = Request::instance();
$incoming_payload = json_decode($request->getContent());
~~~
