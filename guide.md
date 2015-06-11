
# Receiving a POST from a Push Queue

Your route or controller can get the post this way

~~~
$request = Request::instance();
$incoming_payload = json_decode($request->getContent());
~~~


# .env Best Practices (more coming soon)

@TODO Required

@TODO Naming = environment

# Seeding (more coming soon)

@TODO keep it minimal, using the new factory feature
