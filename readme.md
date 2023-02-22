# SpiroKit Universal App Monorepo

The official SpiroKit template for Universal Apps using:

- Expo SDK 47
- NextJS 13.1
- Solito (Cross-platform navigation)
- SpiroKit (UI Kit)
- Moti (Animations)
- React Navigation 6

## Usage

1. Get your SpiroKit license [here](https://spirokit.com)
   We support Parity Purchasing Power. Check our website to see if you are eligible for a discount, if you need it.

2. Create a new project

```sh
expo init my-app --template @spirokit/universal-app-template-typescript
```

3. Download the `spirokit-core-[version].tgz` file from Gumroad and add it to the root of your project.

4. Install SpiroKit on `/packages/app`

```sh
npm i ../../spirokit-core-[version].tgz
yarn add ../../spirokit-core-[version].tgz
```

5. Run your app.

```
yarn native
yarn web
```

For more information about how to use SpiroKit, here's the [full storybook documentation](https://docs.spirokit.com).

## 🔦 About

This monorepo is a blank(ish) starter for an Expo + Next.js app.

While it's pretty barebones, it does a lot of the annoying config for you.

## 🗂 Folder layout

- `apps` entry points for each app

  - `expo`
  - `next`

- `packages` shared packages across apps
  - `app` you'll be importing most files from `app/`
    - `features` (don't use a `screens` folder. organize by feature.)
    - `provider` (all the providers that wrap the app, and some no-ops for Web.)
    - `navigation` Next.js has a `pages/` folder. React Native doesn't. This folder contains navigation-related code for RN. You may use it for any navigation code, such as custom links.

You can add other folders inside of `packages/` if you know what you're doing and have a good reason to.

## 🏁 Start the app

- Install dependencies: `yarn`

- Next.js local dev: `yarn web`
  - Runs `yarn next`
- Expo local dev: `yarn native`
  - Runs `expo start`

## 🆕 Add new dependencies

### Pure JS dependencies

If you're installing a JavaScript-only dependency that will be used across platforms, install it in `packages/app`:

```sh
cd packages/app
yarn add date-fns
cd ../..
yarn
```

### Native dependencies

If you're installing a library with any native code, you must install it in `apps/expo`:

```sh
cd apps/expo
yarn add react-native-reanimated

cd ../..
yarn
```

You can also install the native library inside of `packages/app` if you want to get autoimport for that package inside of the `app` folder. However, you need to be careful and install the _exact_ same version in both packages. If the versions mismatch at all, you'll potentially get terrible bugs.

## 🎙 Special thanks

Fernando Rojo for creating an amazing Starter Repo for Solito + Expo + NexJS:
[@FernandoTheRojo](https://twitter.com/fernandotherojo)

## 🧐 Why use Expo + Next.js?

See Fernando's talk about this topic at Next.js Conf 2021:

<a href="https://www.youtube.com/watch?v=0lnbdRweJtA"><img width="1332" alt="image" src="https://user-images.githubusercontent.com/13172299/157299915-b633e083-f271-48c6-a262-7b7eef765be5.png">
</a>
