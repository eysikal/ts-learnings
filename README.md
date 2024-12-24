# TypeScript Learnings

## A collection of stuff I’ve learned about TypeScript along the way which I don’t want to forget.

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

 
 


