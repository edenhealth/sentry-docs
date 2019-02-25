In PHP a function can be used to modify the event or return a completely new one. If you return `null`, the event will be discarded.

```php
\Sentry\init([
  'dsn' => '___PUBLIC_DSN___',
  'before_send' => function (\Sentry\Event $event): ?Event {
    return $event;
  },
]);
```