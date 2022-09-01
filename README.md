# Laravel OpenSearch Engine
## Installation

`composer require elitexp/opensearch`

```
<?php

namespace App\Providers;

// ...

use Elitexp\OpenSearch\OpenSearchEngine;
use Laravel\Scout\EngineManager;

class AppServiceProvider extends ServiceProvider
{
    public function boot()
    {
        // ...

        resolve(EngineManager::class)->extend(config('scout.driver'), function () {
            return new OpenSearchEngine;
        });

    }
}
```