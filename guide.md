
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

# Iron Workers Logging 

@TODO more content just a snippet below 
  

~~~
    try
    {
        $service = App::make('RenderTree\RenderTreeService');
        Log::debug('payload callback_url: ' . $payload['callback_url']);
        Log::debug('payload job_id: ' . $payload['job_id']);
        $service->processJob($payload['job_id'], $payload['callback_url']);
        echo "Success See Logs Below: \n";
        echo File::get($logs);
    }
    catch(\Exception $e)
    {
        Log::info("Error See Logs Below:");
        $message = sprintf("Error message %s on line %d in file %s",
            $e->getMessage(),
            $e->getLine(),
            $e->getFile()
        );
        Log::info($message);

        $error_message = File::get($logs);

        echo $error_message;
    }
~~~
