---
description: Customise the server & dashboard navigation links on all layouts.
icon: swap-arrows
---

# Routes

## Adding Server Routes

<pre class="language-tsx" data-title="routes.ts"><code class="lang-tsx">import { SaveIcon } from '@heroicons/react/solid' // Import Icon from heroicons
import PluginManagerContainer from '@/components/server/plugins/PluginManagerContainer';

<strong>export default {
</strong>    account: [],
    server: {
        control: [],
        management: [
        {
            path: '/minecraft/plugins',
            permission: 'file.*',
            name: 'Plugin Manager',
            component: PluginManagerContainer,
            icon: SaveIcon, // Define Icon
        },
        ],
        administration: [],
    },
}
</code></pre>

**Icon Property**: You may use any icon package of your choice. Reviactyl currently uses `@heroicons/react/solid` for UI.

## Show Route per Egg / Nest.

**Properties**:&#x20;

1. nestId: (Single Nest) - Example; `nestId: [1],`
2. eggId: (Single Egg) - Example; `eggId: [1],`
3. nestIds: (Multiple Nest) - Example; `nestIds: [1,2,3],`
4. eggIds: (Multiple Egg) - Example; `eggIds: [1,2,3],`

{% code title="routes.ts" %}
```tsx
export default {
    account: [],
    server: {
        control: [],
        management: [
        {
            path: '/minecraft/plugins',
            permission: 'file.*',
            name: 'Plugin Manager',
            component: PluginManagerContainer,
            icon: SaveIcon, // Define Icon
        },
        ],
        administration: [],
    },
}
```
{% endcode %}

## Translating Route Name

In `/resources/lang/<lang>/routes.php` add a string in respective category;

{% code title="routes.php" %}
```php
<?php

return [
    'account' => [],
    'server' => [
        // ...
        'plugin-manager' => 'Plugin Manager', // Add String here
    ],
];
```
{% endcode %}

In `/resources/scripts/routers/routes.ts`&#x20;

{% code title="routes.ts" %}
```tsx
export default {
    account: [],
    server: {
        control: [],
        management: [
        {
            path: '/minecraft/plugins',
            permission: 'file.*',
            name: 'server.plugin-manager', // Replace name with the key
            component: PluginManagerContainer,
            icon: SaveIcon,
        },
        ],
        administration: [],
    },
}
```
{% endcode %}
