Running bun link in a package within a workspace (monorepo-a/packages/app-a)
```bash
# in monorepo-a/packages/app-a
bun link
```
```json
// in app-b package.json
{
  ...
  "dependencies": {
    "@monorepo-a/app-a": "link:@monorepo-a/app-a"
  }
}

// bun install
// (also bun link @monorepo-a/app-a works too)
```

This does not link correctly. 
`app-b/node_modules/@monorepo-a/app-a` is linked to the workspace (monorepo-a) instead of the package.