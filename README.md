Given this write call:

```
await web5.dwn.records.write({
    data: JSON.stringify({ name: 'test' }),
    message: {
    schema: 'http://garfield.com/profile.schema.json',
    protocol: 'http://garfield.com/profile.schema.json',
    protocolPath: 'profile',
    },
    store: true,
});
```

The full call stack is seen in `log.txt`

An aggregated log is seen in `aggregated_log.md`