# Changelog
All notable changes to this project will be documented in this file.

---

## [v0.1.1](https://github.com/Bejibun-Framework/bejibun-limiter/compare/v0.1.1...v0.1.1) - 2026-08-16

### 🩹 Fixes

### 📖 Changes
Initial release of `@bejibun/limiter` -- a rate limiter for the Bejibun Framework, providing a simple key-based API to throttle repeated actions (e.g. login attempts, API calls) using a cache-backed counter.

**`RateLimiterBuilder`:**
- `.setKey(key)` -- set the cache key identifying the thing being limited
- `.setLimit(limit)` -- set the max number of attempts allowed within the duration
- `.setDuration(duration)` -- set the time window in seconds
- `.attempt(callback)` -- increment the attempt counter and run `callback` if still under the limit; throws when exceeded
- `.tooManyAttempts()` -- check whether the current count has already exceeded the limit, without incrementing it
- `.clear()` -- reset the counter for a key

**`RateLimiter` facade (static API, built on `RateLimiterBuilder`):**
- `RateLimiter.attempt(key, limit, callback, duration?)`
- `RateLimiter.tooManyAttempts(key, limit, duration?)`
- `RateLimiter.clear(key)`

**Config:**
- `config/limiter.ts` defines default `limit` (60) and `duration` (60 seconds), copied into the consuming project's `config/` directory via the package's configure step
  **Error handling:**
- `RateLimiterException` -- thrown for an invalid/missing callback or when an attempt exceeds the limit (default HTTP code `429`); logs via `@bejibun/logger` before throwing

**Dependencies:**
- `@bejibun/app ^0.1.24`
- `@bejibun/cache ^0.1.24`
- `@bejibun/logger ^0.1.22`
- `@bejibun/utils ^0.1.28`

### ❤️Contributors
- Havea Crenata ([@crenata](https://github.com/crenata))

**Full Changelog**: https://github.com/Bejibun-Framework/bejibun-limiter/blob/master/CHANGELOG.md