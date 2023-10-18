# Installation
> `npm install --save @types/hooker`

# Summary
This package contains type definitions for JavaScript Hooker (https://github.com/cowboy/javascript-hooker).

# Details
Files were exported from https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/hooker.
## [index.d.ts](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/hooker/index.d.ts)
````ts
// Type definitions for JavaScript Hooker v0.2.3
// Project: https://github.com/cowboy/javascript-hooker
// Definitions by: Michael Zabka <https://github.com/misak113>
// Definitions: https://github.com/DefinitelyTyped/DefinitelyTyped


declare type HookerPostHookFunction = (result: any, ...args: any[]) => IHookerPostHookResult|void;
declare type HookerPreHookFunction = (...args: any[]) => IHookerPreHookResult|void;

declare module "hooker" {
    function hook(object: any, props: string|string[], options: IHookerOptions): void;
    function hook(object: any, props: string|string[], prehookFunction: HookerPreHookFunction): void;
    function unhook(object: any, props?: string|string[]): string[];
    function orig(object: any, props: string|string[]): Function;
    function override(value: any): HookerOverride;
    function preempt(value: any): HookerPreempt;
    function filter(context: any, args: any[]): HookerFilter;
}

declare class HookerOverride implements IHookerPostHookResult, IHookerPreHookResult {
    value: any;
}

declare class HookerPreempt implements IHookerPreHookResult {
    value: any;
}

declare class HookerFilter implements IHookerPreHookResult {
    context: any;
    args: any[];
}

interface IHookerPostHookResult {}

interface IHookerPreHookResult {}

interface IHookerOptions {
    pre?: HookerPreHookFunction | undefined;
    post?: HookerPostHookFunction | undefined;
    once?: boolean | undefined;
    passName?: boolean | undefined;
}

````

### Additional Details
 * Last updated: Thu, 08 Jul 2021 14:22:53 GMT
 * Dependencies: none
 * Global values: `HookerFilter`, `HookerOverride`, `HookerPreempt`

# Credits
These definitions were written by [Michael Zabka](https://github.com/misak113).
