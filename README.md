# Basic TypeScript project

## Commands

After cloning this repo, install dependencies with

`npm i`

---

To start development process, run

`npm run dev`

This command runs nodemon, which watches files and executes 3 following commands:

* `cross-clear` - clear console on any platform
* `npm run lint` - run ESLint. Note that this command ignores errors and runs code anyway
* `npm start` - runs index.ts with *environmental variables* from `.env` file.

**Note!** Before running development process make sure to fill `.env` according to `.env.sample`

---

To create a build of this project, run

`npm run build`

This command executes 3 following commands:

* `npm run lint:strict` - run ESLint and throw error on linting errors
* `npm test` - run tests with jest
* `tsc --project ./` - build project

The output directory is set to `dist`.

**Note!** `npm run build` does not contain *environmental variables* from `.env` file.

## More about this setup

### Testing

The chosen testing framework is jest. There is one example test described in
`test/basic.test.ts`

### Linting

This project is set up with ESLint and [airbnb](https://github.com/airbnb/javascript) config
which I amaze so much 😍.

### Git hooks

This project is set up with [Husky](https://github.com/typicode/husky) to run git hooks. I
prefer having a single pre-commit hook which runs `npm run lint:strict && npm test` to make
sure that the code style is correct and all tests pass.
