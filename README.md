## Write

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

The full call stack is seen in `write_log.txt`
An aggregated log is seen in `write_aggregated_log.md`

## Query + Read + json()

```
 const queryResult = await web5.dwn.records.query({
          message: {
            filter: {
              protocol: 'http://garfield.com/profile.schema.json',
              protocolPath: 'profile',
            },
          },
        });

        const recordId = queryResult.records?.at(0)?.id;

        const readResult = await web5.dwn.records.read({
          message: {
            filter: {
              recordId,
            },
          },
        });

        const profile = await readResult.record.data.json();
```

The full call stack is seen in `read_log.txt`
An aggregated log is seen in `read_aggregated_log.md`