Repro steps:

1. npx create-react-app i18n-issue --template typescript
2. cd i18n-issue 
3. npm install i18next react-i18next
4. add ./src/i18n.tsx
5. add ./src/translation.json
6. import `import "./i18n";` in `index.tsx`