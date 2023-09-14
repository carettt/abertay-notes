[2022-12-10], 23:08
Type: #topic

## React Native

Framework to develop mobile applications without needing to use separate OS-native languages

---

### Expo CLI

- Framework that sits on-top of React Native
	- Hides complexity

VSCode Extensions:
- React Native Tools
- React-Native/React/Redux snippets

>[!WARNING]
>run `wsl --set-version Ubuntu 2` to fix nodejs and npm

#### Installation
```shell
sudo apt-get install curl git # expo requirements
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash # nvm
# at this point restart terminal
nvm install --lts
npx create-expo-app [app-name]
```

---