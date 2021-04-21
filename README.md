# 🧪

This project is me taking [Create React App](https://github.com/facebook/create-react-app) for a spin and ejecting to learn more about configuring the build

- `npm start` to run the app

---

## What I learnt 🎓

CRA makes a decision on my behalf to use Yarn (because I have Yarn installed, otherwise it would use npm?) and will generate a `yarn.lock`. But I can set a flag to choose npm as a package manager:

- `npx create-react-app config-react-testing --use-npm`

The script also attempts initialize git and commit. That fails because of my [gitconfig setup](https://github.com/elisabethirgens/dotfiles/commit/21269f41051615d273c7738f544bcc4acf50d938) which suits me fine, I find it kinda rude that the script tries to automatically make a commit in my name. 🤨

Let's measure dependencies!

```
git ls-files package-lock.json | xargs wc -l
```

There are **38155 lines of code** in the initial package-lock.json and it's 1.46 MB 🤪

### About ejecting react-scripts

Running `npm run eject` results in:

- 14 changed files with 1,936 additions and 6 deletions
- 58 new dependencies to replace the single react-scripts in package.json
- config/webpack.config.js that is too large a diff for github to render 🙈
- Check out [the whole commit](https://github.com/elisabethirgens/config-react-app/commit/08f77c28e33f95e72ee7a6a5917598de528040a6)

No changes to the lock file. At first I expected there would be, but makes sense when I think about it. Ejecting react-scripts doesn't change which packages are used in the project and installed in my node_modules — the eject changes how they are referenced in package.json

When running eject, there is a warning and then if you insist anyway, an invitation to a survey. Nice! I get to answer questions around my experience with Create React App and questions like: “how comfortable are you with configuring Webpack, Babel, and ESLint manually on your own?” and

> How do you feel after running `eject`?<br/>
> I feel frustrated because I didn’t want to give up the defaults but I needed to change something<br/>
> I feel empowered because I am comfortable with the underlying tools<br/>

Neither of those two. I feel curious and excited 🥳 because **I want to take responsibility and ownership** of configuring a new application. Not always, but sometimes. I don't understand why CRA is trying so hard to persuade me against doing that. I'm sceptical of abstracting away too much in a magical `react-scripts` that is a one-size-fits-all config, but equally unconvinced that ejecting is a path I want to take.
