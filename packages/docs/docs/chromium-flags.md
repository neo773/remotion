---
image: /generated/articles-docs-chromium-flags.png
id: chromium-flags
title: Chromium flags
crumb: "Tweaks"
---

import {AngleChangelog} from '../components/AngleChangelog';

We allow you to set the following flags in Chromium and Google Chrome since Remotion 2.6.5:

## `--disable-web-security`

This will most notably disable CORS among other security features.

:::note
Remotion will automatically append the `--user-data-dir` flag.
:::

### Via Node.JS APIs

In [`getCompositions()`](/docs/renderer/get-compositions#disablewebsecurity), [`renderStill()`](/docs/renderer/render-still#disablewebsecurity), [`renderMedia()`](/docs/renderer/render-media#disablewebsecurity), [`renderFrames()`](/docs/renderer/render-frames#disablewebsecurity), [`getCompositionsOnLambda()`](/docs/lambda/getcompositionsonlambda#disablewebsecurity), [`renderStillOnLambda()`](/docs/lambda/renderstillonlambda#disablewebsecurity) and [`renderMediaOnLambda()`](/docs/lambda/rendermediaonlambda#disablewebsecurity), you can pass [`chromiumOptions.disableWebSecurity`](/docs/renderer/render-still#disablewebsecurity).

### Via CLI flag

Pass [`--disable-web-security`](/docs/cli/render#--disable-web-security) in one of the following commands: [`remotion render`](/docs/cli/render), [`remotion compositions`](/docs/cli/compositions), [`remotion still`](/docs/cli/still), [`remotion lambda render`](/docs/lambda/cli/render), [`remotion lambda still`](/docs/lambda/cli/still), [`remotion lambda compositions`](/docs/lambda/cli/compositions).

### Via config file

Use [setChromiumDisableWebSecurity()](/docs/config#setchromiumdisablewebsecurity).

```tsx twoslash
import { Config } from "@remotion/cli/config";

// ---cut---

Config.setChromiumDisableWebSecurity(true);
```

:::note
Prior to `v3.3.39`, the option was called `Config.Puppeteer.setChromiumDisableWebSecurity()`.
:::

## `--ignore-certificate-errors`

Results in invalid SSL certificates, such as self-signed ones, being ignored.

### Via Node.JS APIs

In [`getCompositions()`](/docs/renderer/get-compositions#ignorecertificateerrors), [`renderStill()`](/docs/renderer/render-still#ignorecertificateerrors), [`renderMedia()`](/docs/renderer/render-media#ignorecertificateerrors), [`renderFrames()`](/docs/renderer/render-frames#ignorecertificateerrors), [`getCompositionsOnLambda()`](/docs/lambda/getcompositionsonlambda#disablewebsecurity), [`renderStillOnLambda()`](/docs/lambda/renderstillonlambda#ignorecertificateerrors) and [`renderMediaOnLambda()`](/docs/lambda/rendermediaonlambda#ignorecertificateerrors), you can pass [`chromiumOptions.ignoreCertificateErrors`](/docs/renderer/render-still#ignorecertificateerrors).

### Via CLI flag

Pass [`--ignore-certificate-errors`](/docs/cli/render#--ignore-certificate-errors) in one of the following commands: [`remotion render`](/docs/cli/render), [`remotion compositions`](/docs/cli/compositions), [`remotion still`](/docs/cli/still), [`remotion lambda render`](/docs/lambda/cli/render), [`remotion lambda still`](/docs/lambda/cli/still), [`remotion lambda compositions`](/docs/lambda/cli/compositions).

### Via config file

Use [setChromiumIgnoreCertificateErrors()](/docs/config#setchromiumignorecertificateerrors).

```tsx twoslash
import { Config } from "@remotion/cli/config";

// ---cut---

Config.setChromiumIgnoreCertificateErrors(true);
```

:::note
Prior to `v3.3.39`, the option was called `Config.Puppeteer.setChromiumIgnoreCertificateErrors()`.
:::

## `--disable-headless`

Setting this flag will open an actual Chrome during render where you can see the render happen.

### Via Node.JS APIs

In [`getCompositions()`](/docs/renderer/get-compositions#headless), [`renderStill()`](/docs/renderer/render-still#headless), [`renderMedia()`](/docs/renderer/render-media#headless) and [`renderFrames()`](/docs/renderer/render-frames#headless), you can pass [`chromiumOptions.headless`](/docs/renderer/render-still#headless). You cannot set this option in Lambda.

### Via CLI flag

Pass [`--disable-headless`](/docs/cli/render#--disable-headless) in one of the following commands: [`remotion compositions`](/docs/cli/compositions), [`remotion render`](/docs/cli/render), [`remotion still`](/docs/cli/still).

### Via config file

Use [setChromiumHeadlessMode()](/docs/config#setchromiumheadlessmode).

```tsx twoslash
import { Config } from "@remotion/cli/config";

// ---cut---

Config.setChromiumHeadlessMode(false);
```

:::note
Prior to `v3.3.39`, the option was called `Config.Puppeteer.setChromiumHeadlessMode()`.
:::

## `--gl`

<Options id="gl" />

### Via Node.JS APIs

In [`getCompositions()`](/docs/renderer/get-compositions#gl), [`renderStill()`](/docs/renderer/render-still#gl), [`renderMedia()`](/docs/renderer/render-media#gl), [`renderFrames()`](/docs/renderer/render-frames#gl), [`getCompositionsOnLambda()`](/docs/lambda/getcompositionsonlambda#gl), [`renderStillOnLambda()`](/docs/lambda/renderstillonlambda#gl) and [`renderMediaOnLambda()`](/docs/lambda/rendermediaonlambda#gl), you can pass [`chromiumOptions.gl`](/docs/renderer/render-still#gl).

### Via CLI flag

Pass [`--gl=swiftshader`](/docs/cli) in one of the following commands: [`remotion render`](/docs/cli/render), [`remotion compositions`](/docs/cli/compositions), [`remotion still`](/docs/cli/still), [`remotion lambda render`](/docs/lambda/cli/render), [`remotion lambda still`](/docs/lambda/cli/still), [`remotion lambda compositions`](/docs/lambda/cli/compositions).

### Via config file

```tsx twoslash
import { Config } from "@remotion/cli/config";

// ---cut---

Config.setChromiumOpenGlRenderer("swiftshader");
```

:::note
Prior to `v3.3.39`, the option was called `Config.Puppeteer.setChromiumOpenGlRenderer()`.
:::

## `--user-agent`<AvailableFrom v="3.3.83"/>

### Via Node.JS APIs

In [`getCompositions()`](/docs/renderer/get-compositions#useragent), [`renderStill()`](/docs/renderer/render-still#useragent), [`renderMedia()`](/docs/renderer/render-media#useragent), [`renderFrames()`](/docs/renderer/render-frames#useragent), [`getCompositionsOnLambda()`](/docs/lambda/getcompositionsonlambda#useragent), [`renderStillOnLambda()`](/docs/lambda/renderstillonlambda#useragent) and [`renderMediaOnLambda()`](/docs/lambda/rendermediaonlambda#chromiumoptions), you can pass [`chromiumOptions.userAgent`](/docs/renderer/render-still#useragent).

### Via CLI flag

Pass [`--user-agent`](/docs/cli) in one of the following commands: [`remotion render`](/docs/cli/render), [`remotion compositions`](/docs/cli/compositions), [`remotion still`](/docs/cli/still), [`remotion lambda render`](/docs/lambda/cli/render), [`remotion lambda still`](/docs/lambda/cli/still), [`remotion lambda compositions`](/docs/lambda/cli/compositions).

## Need more flags?

Open a [GitHub issue](https://github.com/remotion-dev/remotion/issues/new?assignees=&labels=&template=feature_request.md&title=) to request it.
