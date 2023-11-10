Repro steps:

1. npx create-react-app i18n-issue --template typescript
2. cd i18n-issue 
3. npm install i18next react-i18next
4. add ./src/i18n.tsx
5. add ./src/translation.json
6. import `import "./i18n";` in `index.tsx`
7. useTranslation in app.tsx
8. npm start


Will hit this error:

```
ERROR in src/App.tsx:7:15
TS2589: Type instantiation is excessively deep and possibly infinite.
     5 |
     6 | function App() {
  >  7 |   const {t} = useTranslation();
       |               ^^^^^^^^^^^^^^^^
     8 |   return (
     9 |     <div className="App">
    10 |       <header className="App-header">

One of your dependencies, babel-preset-react-app, is importing the
"@babel/plugin-proposal-private-property-in-object" package without
declaring it in its dependencies. This is currently working because
"@babel/plugin-proposal-private-property-in-object" is already in your
node_modules folder for unrelated reasons, but it may break at any time.

babel-preset-react-app is part of the create-react-app project, which
is not maintianed anymore. It is thus unlikely that this bug will
ever be fixed. Add "@babel/plugin-proposal-private-property-in-object" to
your devDependencies to work around this error. This will make this message
go away.
```

package version:
* "react-i18next": "^13.3.2",
* "i18next": "^23.7.1",

if downgrade to this version, issue is gone:
* "react-i18next": "^11.18.3",
* "i18next": "^21.8.16",