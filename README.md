# Husky with React App

## Create a react app for husky demo.

Create a react app using command 
### `npx create-react-app react-husky`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

## Install Linter eslint

ESLint analyzes your code for potential errors, and enforces coding standards while improving code quality.

It can also help you as a developer to identify and fix common mistakes, use best practices, and maintain consistency across your codebase.

You can integrate ESLint seamlessly into your React projects, providing real-time feedback and improving your overall code quality.

* npm install eslint eslint-plugin-react eslint-plugin-react-hooks --save-dev


### Configure ESLint 
Create a .eslintrc.json file and paste below linting configuration:


![EsLint Config](<img/elint config.png>)

## Install Husky

* npm i --save-dev husky
* npx husky install
* npx husky add .husky/pre-commit (adds precommit hook)

This will create a pre commit hook pre-commimt under .husky folder.

![Husky Folder](<img/husky folder and precommit.png>)

This hook will run when you do git commit.



## install lint-staged

Linting makes more sense when run before committing your code. By doing so you can ensure no errors go into the repository and enforce code style. But running a lint process on a whole project is slow, and linting results can be irrelevant. Ultimately you only want to lint files that will be committed.

lint-staged will stop your git commit when there is an error on linting your files

* npm i --save-dev lint-staged

## Update package.json

![Package.json](<img/package.json snip.png>)


add these lines into your package.json . It tells lint-staged what command should be run with specific files.

![Precommit Hook](<img/precommit file.png>)