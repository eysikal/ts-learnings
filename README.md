# TypeScript Learnings

## A collection of things I’ve learned about TypeScript along the way that I don’t want to forget.

### 1. You should always configure TS with the `noImplicitAny` and `strictNullChecks` options.
#### And if you can, aim to enable the "strict" option.

```
// tsconfig.json
"compilerOptions": {
  "noImplicitAny": true,
  "strictNullChecks": true,
}
```
Or, better:
```
// tsconfig.json
"compilerOptions": {
  "strict": true,
}
```

If you are newly enabling these options in an established project, you can use the following command to check which files have errors that need to be addressed:
```
tsc --noImplicitAny --noEmit
// Or
tsc --strictNullChecks --noEmit
// Or
tsc --strict --noEmit
```


### 2. A cool trick for preserving type information at runtime is to set a `kind` property:
```
interface Truck {
  kind: 'Truck';
  mpg: number;
  tireRotationInterval: number;
}

interface Plane {
  kind: 'Plane';
  flightHours: number;
  crewSize: number;
}

type Transporation = Truck | Plane;

// At runtime
describeTransportation(transport: Transportation) {
  switch (transport.kind) {
    case 'Truck':
      console.log(`${transport.kind}` gets ${mpg} MPG needs its tires rotated every ${tireRotationInterval} miles.`);
    case 'Plane':
      console.log(`${transport.kind}` has logged ${flightHours} flight hours and requires a crew size of ${crewSize} people.`);
  }
}
```
 


