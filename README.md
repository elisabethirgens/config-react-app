# 🧪

This project is me taking [Create React App](https://github.com/facebook/create-react-app) for a spin and ejecting to learn more about configuring the build

- `npm start` to run the app

---

## What I learnt 🎓

CRA makes a decision on my behalf to use Yarn (because I have Yarn installed, otherwise it would use npm?) and will generate a `yarn.lock`. But I can set a flag to choose npm as a package manager:

- `npx create-react-app config-react-testing --use-npm`

The script also attempts initialize git and commit. That fails because of my [gitconfig setup](https://github.com/elisabethirgens/dotfiles/commit/21269f41051615d273c7738f544bcc4acf50d938) which suits me fine, I find it kinda rude that the script tries to automatically make a commit in my name. 🤨
