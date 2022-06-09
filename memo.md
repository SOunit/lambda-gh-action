# url

- How to deploy a lambda function using github actions?
  https://www.youtube.com/watch?v=UQiRhKgQ5X0

# steps

- create lambda function
- add trigger
  - http API
  - security - open
- crete `index.ts`
- create `tsconfig.json`
- install typescript dependencies
  ```
  npm i -D @types/lodash @types/node @types/aws-lambda @vercel/ncc
  ```
- copy paste tsconfig.json
  https://github.com/vercel/ncc
- create `index.ts handler`
  - name come from `Runtime settings / handler` in code tab in lambda page
