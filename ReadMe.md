#### Step 1. Instantiate the Node Package Manager

> Run cmd : `npm init`

It will ask you to create the package.json.

#### Step 2. Set up the eslint

> Run cmd : `npx eslint --init`

It will ask you to create .eslintrc & initiate files.

#### Step 3. Add the prettier

> Run cmd : `npm i -D prettier eslint-config-prettier eslint-plugin-prettier`

**"eslint-config-prettier", "eslint-plugin-prettier"** is for the preventing conflict

And then, add the "plugin:prettier/recommended" to the .eslintrc's extends key as an array

Also, add prettier config to the .eslintrc's rules key.

```
"rules : {
    // ...etc
    "prettier/prettier": [
        "error",
        {
            "trailingComma": "es5",
            "singleQuote": true,
            "printWidth": 100,
            "semi": true
        }
    ]

}

```

#### Step 4. Create the index.js file

Export the index.js

#### Step 5. Declare peerDependencies

As it is stated in the official ESLint docs, you should declare your dependency on ESLint in package.json using the peerDependencies field. So just copy all dev dependencies in the package.json file to peerDependencies field:

```
// package.json

...

"peerDependencies": {
    "@typescript-eslint/eslint-plugin": "^5.5.0",
    "@typescript-eslint/parser": "^5.5.0",
    "eslint": "^8.4.0",
    "eslint-config-prettier": "^8.3.0",
    "eslint-plugin-prettier": "^4.0.0",
    "eslint-plugin-react": "^7.27.1",
    "eslint-plugin-react-hooks": "^4.3.0",
    "eslint-plugin-simple-import-sort": "^7.0.0",
    "prettier": "^2.5.1"
  }

```

### Step 6. Add airbnb style

Run cmd : `yarn add -D eslint-config-airbnb `

And then, add the "airbnb" to the extends

```
module.exports = {
  ...etc,
  extends: ["plugin:react/recommended", "airbnb", "plugin:prettier/recommended"],
  ...
};

```

---

Reference :
[how to create reusable eslint](https://dev.to/ramonak/how-to-create-custom-reusable-eslint-typescript-prettier-config-for-react-apps-5605)
[Test npm locally](https://medium.com/@debshish.pal/publish-a-npm-package-locally-for-testing-9a00015eb9fd)
