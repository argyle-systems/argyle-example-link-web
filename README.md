# Argyle Link Integration

[Argyle Link](https://argyle.io/docs/argyle-link/overview) is a front-end UI element that allows your users to grant your application access to their workforce accounts. This example demonstrates the different ways of integrating Argyle Link into your website.

<br>

## Link Options :crystal_ball:

Switching between different options menu resets the `userToken` for the plugin. If you connect multiple partners staying in one of menu items, the `userToken` is saved and reused for the plugin ensuring all accounts are connected for the same user and the same state is retained.

### 1. Full data partner menu

When the `dataPartners` parameter is not set, Argyle Link lists all available data partners.

```js
Argyle.create({
  pluginKey: "your_plugin_key",
  dataPartners: [],
  //userToken: "user_token",
});
```

<br>

<details open><summary>:globe_with_meridians: Whole data partner menu demo </summary>
<br>
  <p align="center">
    <img src="./demo-gifs/whole-menu.gif" alt="Whole data partner menu gif">
  </p>
</details>

### 2. One data partner

If the `dataPartners` list is initialized with a single data partner id –– Argyle Link immediately shows that partner's login screen instead of the list.

```js
Argyle.create({
  pluginKey: "your_plugin_key",
  dataPartners: ["uber"],
  //userToken: "user_token",
});
```

<br>

<details open><summary>:wolf: One data partner demo</summary>
<br>
  <p align="center">
    <img src="./demo-gifs/one-partner.gif" alt="One data partner gif">
  </p>
</details>

### 3. Two data partners

When two or more data partners are provided, Argyle Link displays only the data partners you specified.

```js
Argyle.create({
  pluginKey: "your_plugin_key",
  dataPartners: ["uber", "lyft"],
  //userToken: "user_token",
});
```

<br>

<details open><summary>:cherries: Two data partners demo</summary>
<br>
  <p align="center">
    <img src="./demo-gifs/two-partners.gif" alt="Two data partners gif">
  </p>
</details>

### 4. Your own menu

Sometimes you might want to implement your own data partners list instead of showing the one from Argyle Link.

In this case you can run two different instances of Link and open them from your own UI. Here's an example:

```js
const initArgyle = (providedDataPartners) => {
  return Argyle.create({
    pluginKey: "your_plugin_key",
    dataPartners: providedDataPartners,
    //userToken: "user_token",
  });
};
```

<br>

<details open><summary>:pizza: Your own menu demo</summary>
<br>
  <p align="center">
    <img src="./demo-gifs/own-menu.gif" alt="Your own menu gif">
  </p>
</details>
