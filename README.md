# astro-hcaptcha

A simple Astro component for **interactive** hCaptchas, for use in `<form>` et al without a frontend framework. It supports all [query parameters and container attributes](https://docs.hcaptcha.com/configuration) exposed by hCaptcha.

> [!TIP]
> If you want to use _explicit_ rendering or non-interactive captchas (the latter require the former), this is probably not the right package for you. Consider using [a different integration](https://docs.hcaptcha.com/integrations#javascript) and (optionally) a frontend framework instead.

```astro
---
import HCaptcha from "astro-hcaptcha";
---

<form action="/api/signin" method="post">
    <input type="email" name="email" placeholder="Email" />
    <input type="password" name="password" placeholder="Password" />
    <HCaptcha sitekey={env.HCAPTCHA_SITEKEY} theme="dark" />
    <button type="submit">Sign in</button>
</form>
```

```ts
sitekey: string;

render?: "explicit" | "onload";
hl?: string;
recaptchacompat?: "on" | "off";

theme?: "light" | "dark";
size?: "normal" | "compact";
tabindex?: number;
callback?: {
    success?: string;
    expired?: string;
    challengeExpired?: string;
    open?: string;
    close?: string;
    error?: string;
};
orientation?: "portrait" | "landscape";
```
