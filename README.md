<div align="center">

<img src="https://github.com/Bejibun-Framework/bejibun/blob/master/public/images/bejibun.png?raw=true" width="150" alt="Bejibun" />

![GitHub top language](https://img.shields.io/github/languages/top/Bejibun-Framework/bejibun-limiter)
![NPM Downloads](https://img.shields.io/npm/d18m/%40bejibun%2Flimiter)
![GitHub issues](https://img.shields.io/github/issues/Bejibun-Framework/bejibun-limiter)
![GitHub](https://img.shields.io/github/license/Bejibun-Framework/bejibun-limiter)
![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/Bejibun-Framework/bejibun-limiter?display_name=tag&include_prereleases)

</div>

# Limiter for Bejibun

Limiter for Bejibun Framework.

## Usage

### Installation

Install the package.

```bash
# Using Bun
bun add @bejibun/limiter

# Using Bejibun
bun ace install @bejibun/limiter
```

### Configuration

The configuration file automatically executed if you are using `ace`.

Or

Add `limiter.ts` inside config directory on your project if doesn't exist.

```bash
config/limiter.ts
```

```ts
const config: Record<string, any> = {
    limit: 60,
    duration: 60 // seconds
};

export default config;
```

You can pass the value with environment variables.

### How to Use

How to use tha package.

```ts
import RateLimiter from "@bejibun/limiter";

await RateLimiter.attempt(`user:${user.id}`, 60 /* limit */, () => {
    //
}, 60 /* duration (optional) */);
await RateLimiter.tooManyAttempts(`user:${user.id}`, 60 /* limit */, 60 /* duration (optional) */);
await RateLimiter.clear(`user:${user.id}`);
```

## ☕ Support / Donate

If you find this project helpful and want to support it:

[![Donate](https://img.shields.io/badge/Donate-Support%20Me-orange?style=for-the-badge)](https://donate.bejibun.com)

Or you can buy this `$BJBN (Bejibun)` tokens [here](https://pump.fun/coin/CQhbNnCGKfDaKXt8uE61i5DrBYJV7NPsCDD9vQgypump).