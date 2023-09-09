# Husky with React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Create a react app.

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


### configure ESLint 
Create a .eslintrc.json file and paste below linting configuration:

{
    "env": {
      "browser": true,
      "es2021": true
    },
    "extends": ["eslint:recommended", "plugin:react/recommended", "plugin:react-hooks/recommended"],
    "parserOptions": {
      "ecmaVersion": 12,
      "sourceType": "module",
      "ecmaFeatures": {
        "jsx": true
      }
    },
    "plugins": ["react", "react-hooks"],
    "rules": {
      //add customize rules here as per your project's needs
    }
}  


## Install Husky

* npm i --save-dev husky
* npx husky install
* npx husky add .husky/pre-commit (adds precommit hook)

This will create a pre commit hook pre-commimt under .husky folder.
This hook will run when you do git commit.

## install lint-staged

Linting makes more sense when run before committing your code. By doing so you can ensure no errors go into the repository and enforce code style. But running a lint process on a whole project is slow, and linting results can be irrelevant. Ultimately you only want to lint files that will be committed.

lint-staged will stop your git commit when there is an error on linting your files

* npm i --save-dev lint-staged

## Update package.json

{
  "scripts": {
    "lint": "eslint . --fix --max-warnings=0",
    "format": "prettier . --write",
    "prepare": "husky install",
  },
   "lint-staged": {
    "*.{js,jsx,css,md,scss,html,json}": "npm run format",
    "*.{js,jsx}": "npm run lint"
  }
}

add these lines into your package.json . It tells lint-staged what command should be run with specific files.

