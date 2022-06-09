# url

- How to deploy a lambda function using github actions?
  https://www.youtube.com/watch?v=UQiRhKgQ5X0

# steps

## lambda function / API gateway

- create lambda function

- add trigger

  - http API
  - security - open

## src function

- crete `index.ts`

- create `tsconfig.json`

- install typescript dependencies

  ```
  npm i -D @types/lodash @types/node @types/aws-lambda @vercel/ncc typescript
  ```

- copy paste tsconfig.json
  https://github.com/vercel/ncc

- create `index.ts handler`

  - name come from `Runtime settings / handler` in code tab in lambda page

## github action

### step1 - check if this work well

- create `.github/workflow/main.yml`
- checkout code to Github Action Server
- install node
- install npm package

### step2 - deploy to lambda

- deploy to lambda
  - build /w ncc - Typescript to Javascript
    - `npx ncc build index.ts`
  - zip dist folder
    - `zip -j deploy.zip ./dist/*`
  - aws cli - deploy
    - aws lambda help
    - `aws lambda update-function-code --function-name=lambda-gh-action --zip-file=fileb://deploy.zip`

### step3 - add aws credential

- copy and paste from document
  https://github.com/aws-actions/configure-aws-credentials

# install aws cli

https://www.youtube.com/watch?v=vefyYGn9C00

# points

- one tool, you can control all AWS services
  - create service
  - edit service
