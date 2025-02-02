# Snapshot report for `test/prefer-export-from.mjs`

The actual snapshot is saved in `prefer-export-from.mjs.snap`.

Generated by [AVA](https://avajs.dev).

## Invalid #1
      1 | import defaultExport from 'foo';
      2 | export default defaultExport;

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {default} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import defaultExport from 'foo';␊
    > 2 | export default defaultExport;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
    `

## Invalid #2
      1 | import defaultExport from 'foo';
      2 | export {defaultExport as default};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {default} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import defaultExport from 'foo';␊
    > 2 | export {defaultExport as default};␊
        |         ^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
    `

## Invalid #3
      1 | import defaultExport from 'foo';
      2 | export {defaultExport as named};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {default as named} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import defaultExport from 'foo';␊
    > 2 | export {defaultExport as named};␊
        |         ^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`named\`.␊
    `

## Invalid #4
      1 | import defaultExport from 'foo';
      2 | export const variable = defaultExport;

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {default as variable} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import defaultExport from 'foo';␊
    > 2 | export const variable = defaultExport;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`variable\`.␊
    `

## Invalid #5
      1 | import {default as defaultExport} from 'foo';
      2 | export default defaultExport;

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {default} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import {default as defaultExport} from 'foo';␊
    > 2 | export default defaultExport;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
    `

## Invalid #6
      1 | import {default as defaultExport} from 'foo';
      2 | export {defaultExport as default};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {default} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import {default as defaultExport} from 'foo';␊
    > 2 | export {defaultExport as default};␊
        |         ^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
    `

## Invalid #7
      1 | import {default as defaultExport} from 'foo';
      2 | export {defaultExport as named};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {default as named} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import {default as defaultExport} from 'foo';␊
    > 2 | export {defaultExport as named};␊
        |         ^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`named\`.␊
    `

## Invalid #8
      1 | import defaultExport from 'foo';
      2 | export const variable = defaultExport;

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {default as variable} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import defaultExport from 'foo';␊
    > 2 | export const variable = defaultExport;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`variable\`.␊
    `

## Invalid #9
      1 | import defaultExport from 'foo';
      2 | defaultExport.bar = 1;
      3 | export {defaultExport as named};
      4 | export {defaultExport as default};
      5 | export const variable = defaultExport;

> Output

    `␊
      1 | import defaultExport from 'foo';␊
      2 | defaultExport.bar = 1;␊
      3 |␊
      4 |␊
      5 |␊
      6 | export {default as named, default, default as variable} from 'foo';␊
    `

> Error 1/3

    `␊
      1 | import defaultExport from 'foo';␊
      2 | defaultExport.bar = 1;␊
    > 3 | export {defaultExport as named};␊
        |         ^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`named\`.␊
      4 | export {defaultExport as default};␊
      5 | export const variable = defaultExport;␊
    `

> Error 2/3

    `␊
      1 | import defaultExport from 'foo';␊
      2 | defaultExport.bar = 1;␊
      3 | export {defaultExport as named};␊
    > 4 | export {defaultExport as default};␊
        |         ^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
      5 | export const variable = defaultExport;␊
    `

> Error 3/3

    `␊
      1 | import defaultExport from 'foo';␊
      2 | defaultExport.bar = 1;␊
      3 | export {defaultExport as named};␊
      4 | export {defaultExport as default};␊
    > 5 | export const variable = defaultExport;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`variable\`.␊
    `

## Invalid #10
      1 | import {named} from 'foo';
      2 | export default named;

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {named as default} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import {named} from 'foo';␊
    > 2 | export default named;␊
        | ^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
    `

## Invalid #11
      1 | import {named} from 'foo';
      2 | export {named as default};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {named as default} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import {named} from 'foo';␊
    > 2 | export {named as default};␊
        |         ^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
    `

## Invalid #12
      1 | import {named} from 'foo';
      2 | export {named as named};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {named} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import {named} from 'foo';␊
    > 2 | export {named as named};␊
        |         ^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`named\`.␊
    `

## Invalid #13
      1 | import {named} from 'foo';
      2 | export {named as renamed};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {named as renamed} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import {named} from 'foo';␊
    > 2 | export {named as renamed};␊
        |         ^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`renamed\`.␊
    `

## Invalid #14
      1 | import {named} from 'foo';
      2 | export const variable = named;

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {named as variable} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import {named} from 'foo';␊
    > 2 | export const variable = named;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`variable\`.␊
    `

## Invalid #15
      1 | import {named} from 'foo';
      2 | named.bar = 1;
      3 | export {named as named};
      4 | export {named as default};
      5 | export const variable = named;

> Output

    `␊
      1 | import {named} from 'foo';␊
      2 | named.bar = 1;␊
      3 |␊
      4 |␊
      5 |␊
      6 | export {named, named as default, named as variable} from 'foo';␊
    `

> Error 1/3

    `␊
      1 | import {named} from 'foo';␊
      2 | named.bar = 1;␊
    > 3 | export {named as named};␊
        |         ^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`named\`.␊
      4 | export {named as default};␊
      5 | export const variable = named;␊
    `

> Error 2/3

    `␊
      1 | import {named} from 'foo';␊
      2 | named.bar = 1;␊
      3 | export {named as named};␊
    > 4 | export {named as default};␊
        |         ^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
      5 | export const variable = named;␊
    `

> Error 3/3

    `␊
      1 | import {named} from 'foo';␊
      2 | named.bar = 1;␊
      3 | export {named as named};␊
      4 | export {named as default};␊
    > 5 | export const variable = named;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`variable\`.␊
    `

## Invalid #16
      1 | import * as namespace from 'foo';
      2 | export {namespace as namespace};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export * as namespace from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import * as namespace from 'foo';␊
    > 2 | export {namespace as namespace};␊
        |         ^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`namespace\`.␊
    `

## Invalid #17
      1 | import * as namespace from 'foo';
      2 | export {namespace as renamed};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export * as renamed from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import * as namespace from 'foo';␊
    > 2 | export {namespace as renamed};␊
        |         ^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`renamed\`.␊
    `

## Invalid #18
      1 | import * as namespace from 'foo';
      2 | export const variable = namespace;

> Output

    `␊
      1 |␊
      2 |␊
      3 | export * as variable from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import * as namespace from 'foo';␊
    > 2 | export const variable = namespace;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`variable\`.␊
    `

## Invalid #19
      1 | import * as namespace from 'foo';
      2 | namespace.bar = 1;
      3 | export {namespace as named};
      4 | export {namespace as default};
      5 | export const variable = namespace;

> Output

    `␊
      1 | import * as namespace from 'foo';␊
      2 | namespace.bar = 1;␊
      3 |␊
      4 | export {namespace as default};␊
      5 |␊
      6 | export * as named from 'foo';␊
      7 | export * as variable from 'foo';␊
    `

> Error 1/2

    `␊
      1 | import * as namespace from 'foo';␊
      2 | namespace.bar = 1;␊
    > 3 | export {namespace as named};␊
        |         ^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`named\`.␊
      4 | export {namespace as default};␊
      5 | export const variable = namespace;␊
    `

> Error 2/2

    `␊
      1 | import * as namespace from 'foo';␊
      2 | namespace.bar = 1;␊
      3 | export {namespace as named};␊
      4 | export {namespace as default};␊
    > 5 | export const variable = namespace;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`variable\`.␊
    `

## Invalid #20
      1 | import {named1, named2} from 'foo';
      2 | export {named1};

> Output

    `␊
      1 | import { named2} from 'foo';␊
      2 |␊
      3 | export {named1} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import {named1, named2} from 'foo';␊
    > 2 | export {named1};␊
        |         ^^^^^^ Use \`export…from\` to re-export \`named1\`.␊
    `

## Invalid #21
      1 | import defaultExport, {named} from 'foo';
      2 | export {defaultExport};

> Output

    `␊
      1 | import  {named} from 'foo';␊
      2 |␊
      3 | export {default as defaultExport} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import defaultExport, {named} from 'foo';␊
    > 2 | export {defaultExport};␊
        |         ^^^^^^^^^^^^^ Use \`export…from\` to re-export \`defaultExport\`.␊
    `

## Invalid #22
      1 | import defaultExport, {named} from 'foo';
      2 | export {named};

> Output

    `␊
      1 | import defaultExport from 'foo';␊
      2 |␊
      3 | export {named} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import defaultExport, {named} from 'foo';␊
    > 2 | export {named};␊
        |         ^^^^^ Use \`export…from\` to re-export \`named\`.␊
    `

## Invalid #23
      1 | import defaultExport, * as namespace from 'foo';
      2 | export {defaultExport};

> Output

    `␊
      1 | import  * as namespace from 'foo';␊
      2 |␊
      3 | export {default as defaultExport} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import defaultExport, * as namespace from 'foo';␊
    > 2 | export {defaultExport};␊
        |         ^^^^^^^^^^^^^ Use \`export…from\` to re-export \`defaultExport\`.␊
    `

## Invalid #24
      1 | import * as foo from 'foo';
      2 | export {foo};
      3 | export * as bar from 'foo';

> Output

    `␊
      1 |␊
      2 |␊
      3 | export * as bar from 'foo';␊
      4 | export * as foo from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import * as foo from 'foo';␊
    > 2 | export {foo};␊
        |         ^^^ Use \`export…from\` to re-export \`foo\`.␊
      3 | export * as bar from 'foo';␊
    `

## Invalid #25
      1 | import * as foo from 'foo';
      2 | export {foo};
      3 | export {bar} from 'foo';

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {bar} from 'foo';␊
      4 | export * as foo from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import * as foo from 'foo';␊
    > 2 | export {foo};␊
        |         ^^^ Use \`export…from\` to re-export \`foo\`.␊
      3 | export {bar} from 'foo';␊
    `

## Invalid #26
      1 | import * as foo from 'foo';
      2 | export {foo};
      3 | export {} from 'foo';

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {} from 'foo';␊
      4 | export * as foo from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import * as foo from 'foo';␊
    > 2 | export {foo};␊
        |         ^^^ Use \`export…from\` to re-export \`foo\`.␊
      3 | export {} from 'foo';␊
    `

## Invalid #27
      1 | import * as foo from 'foo';
      2 | export {foo};
      3 | export * from 'foo';

> Output

    `␊
      1 |␊
      2 |␊
      3 | export * from 'foo';␊
      4 | export * as foo from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import * as foo from 'foo';␊
    > 2 | export {foo};␊
        |         ^^^ Use \`export…from\` to re-export \`foo\`.␊
      3 | export * from 'foo';␊
    `

## Invalid #28
      1 | import foo from 'foo';
      2 | export {foo};
      3 | export * as bar from 'foo';

> Output

    `␊
      1 |␊
      2 |␊
      3 | export * as bar from 'foo';␊
      4 | export {default as foo} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import foo from 'foo';␊
    > 2 | export {foo};␊
        |         ^^^ Use \`export…from\` to re-export \`foo\`.␊
      3 | export * as bar from 'foo';␊
    `

## Invalid #29
      1 | import foo from 'foo';
      2 | export {foo};
      3 | export {bar} from 'foo';

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {bar, default as foo} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import foo from 'foo';␊
    > 2 | export {foo};␊
        |         ^^^ Use \`export…from\` to re-export \`foo\`.␊
      3 | export {bar} from 'foo';␊
    `

## Invalid #30
      1 | import foo from 'foo';
      2 | export {foo};
      3 | export {bar,} from 'foo';

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {bar, default as foo,} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import foo from 'foo';␊
    > 2 | export {foo};␊
        |         ^^^ Use \`export…from\` to re-export \`foo\`.␊
      3 | export {bar,} from 'foo';␊
    `

## Invalid #31
      1 | import foo from 'foo';
      2 | export {foo};
      3 | export {} from 'foo';

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {default as foo} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import foo from 'foo';␊
    > 2 | export {foo};␊
        |         ^^^ Use \`export…from\` to re-export \`foo\`.␊
      3 | export {} from 'foo';␊
    `

## Invalid #32
      1 | import foo from 'foo';
      2 | export {foo};
      3 | export * from 'foo';

> Output

    `␊
      1 |␊
      2 |␊
      3 | export * from 'foo';␊
      4 | export {default as foo} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import foo from 'foo';␊
    > 2 | export {foo};␊
        |         ^^^ Use \`export…from\` to re-export \`foo\`.␊
      3 | export * from 'foo';␊
    `

## Invalid #33
      1 | import {named1, named2} from 'foo';
      2 | export {named1, named2};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {named1, named2} from 'foo';␊
    `

> Error 1/2

    `␊
      1 | import {named1, named2} from 'foo';␊
    > 2 | export {named1, named2};␊
        |         ^^^^^^ Use \`export…from\` to re-export \`named1\`.␊
    `

> Error 2/2

    `␊
      1 | import {named1, named2} from 'foo';␊
    > 2 | export {named1, named2};␊
        |                 ^^^^^^ Use \`export…from\` to re-export \`named2\`.␊
    `

## Invalid #34
      1 | import {named} from 'foo';
      2 | export {named as default, named};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {named as default, named} from 'foo';␊
    `

> Error 1/2

    `␊
      1 | import {named} from 'foo';␊
    > 2 | export {named as default, named};␊
        |         ^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
    `

> Error 2/2

    `␊
      1 | import {named} from 'foo';␊
    > 2 | export {named as default, named};␊
        |                           ^^^^^ Use \`export…from\` to re-export \`named\`.␊
    `

## Invalid #35
      1 | import {named, named as renamed} from 'foo';
      2 | export {named, renamed};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {named, named as renamed} from 'foo';␊
    `

> Error 1/2

    `␊
      1 | import {named, named as renamed} from 'foo';␊
    > 2 | export {named, renamed};␊
        |         ^^^^^ Use \`export…from\` to re-export \`named\`.␊
    `

> Error 2/2

    `␊
      1 | import {named, named as renamed} from 'foo';␊
    > 2 | export {named, renamed};␊
        |                ^^^^^^^ Use \`export…from\` to re-export \`renamed\`.␊
    `

## Invalid #36
      1 | import defaultExport, {named1, named2} from 'foo';
      2 | export {named1 as default};
      3 | export {named2};
      4 | export {defaultExport};

> Output

    `␊
      1 |␊
      2 |␊
      3 |␊
      4 |␊
      5 | export {default as defaultExport, named1 as default, named2} from 'foo';␊
    `

> Error 1/3

    `␊
      1 | import defaultExport, {named1, named2} from 'foo';␊
    > 2 | export {named1 as default};␊
        |         ^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
      3 | export {named2};␊
      4 | export {defaultExport};␊
    `

> Error 2/3

    `␊
      1 | import defaultExport, {named1, named2} from 'foo';␊
      2 | export {named1 as default};␊
    > 3 | export {named2};␊
        |         ^^^^^^ Use \`export…from\` to re-export \`named2\`.␊
      4 | export {defaultExport};␊
    `

> Error 3/3

    `␊
      1 | import defaultExport, {named1, named2} from 'foo';␊
      2 | export {named1 as default};␊
      3 | export {named2};␊
    > 4 | export {defaultExport};␊
        |         ^^^^^^^^^^^^^ Use \`export…from\` to re-export \`defaultExport\`.␊
    `

## Invalid #37
      1 | import * as foo from 'foo';
      2 | import * as bar from 'foo';
      3 | export {foo, bar};

> Output

    `␊
      1 |␊
      2 |␊
      3 |␊
      4 | export * as foo from 'foo';␊
      5 | export * as bar from 'foo';␊
    `

> Error 1/2

    `␊
      1 | import * as foo from 'foo';␊
      2 | import * as bar from 'foo';␊
    > 3 | export {foo, bar};␊
        |         ^^^ Use \`export…from\` to re-export \`foo\`.␊
    `

> Error 2/2

    `␊
      1 | import * as foo from 'foo';␊
      2 | import * as bar from 'foo';␊
    > 3 | export {foo, bar};␊
        |              ^^^ Use \`export…from\` to re-export \`bar\`.␊
    `

## Invalid #38
      1 | import * as foo from 'foo';
      2 | export {foo, foo as bar};

> Output

    `␊
      1 |␊
      2 |␊
      3 | export * as foo from 'foo';␊
      4 | export * as bar from 'foo';␊
    `

> Error 1/2

    `␊
      1 | import * as foo from 'foo';␊
    > 2 | export {foo, foo as bar};␊
        |         ^^^ Use \`export…from\` to re-export \`foo\`.␊
    `

> Error 2/2

    `␊
      1 | import * as foo from 'foo';␊
    > 2 | export {foo, foo as bar};␊
        |              ^^^^^^^^^^ Use \`export…from\` to re-export \`bar\`.␊
    `

## Invalid #39
      1 | import defaultExport from 'foo';
      2 | export * from 'foo';
      3 | export default defaultExport;

> Output

    `␊
      1 |␊
      2 | export * from 'foo';␊
      3 |␊
      4 | export {default} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import defaultExport from 'foo';␊
      2 | export * from 'foo';␊
    > 3 | export default defaultExport;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
    `

## Invalid #40
      1 | import defaultExport from 'foo';
      2 | export {named} from 'foo';
      3 | export * from 'foo';
      4 | export default defaultExport;

> Output

    `␊
      1 |␊
      2 | export {named, default} from 'foo';␊
      3 | export * from 'foo';␊
      4 |␊
    `

> Error 1/1

    `␊
      1 | import defaultExport from 'foo';␊
      2 | export {named} from 'foo';␊
      3 | export * from 'foo';␊
    > 4 | export default defaultExport;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
    `

## Invalid #41
      1 | import defaultExport from './foo.js';
      2 | export {named} from './foo.js';
      3 | export default defaultExport;

> Output

    `␊
      1 |␊
      2 | export {named, default} from './foo.js';␊
      3 |␊
    `

> Error 1/1

    `␊
      1 | import defaultExport from './foo.js';␊
      2 | export {named} from './foo.js';␊
    > 3 | export default defaultExport;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
    `

## Invalid #42
      1 | import defaultExport from './foo.js';
      2 | export {named} from './foo.js?query';
      3 | export default defaultExport;

> Output

    `␊
      1 |␊
      2 | export {named} from './foo.js?query';␊
      3 |␊
      4 | export {default} from './foo.js';␊
    `

> Error 1/1

    `␊
      1 | import defaultExport from './foo.js';␊
      2 | export {named} from './foo.js?query';␊
    > 3 | export default defaultExport;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
    `

## Invalid #43
      1 | import * as namespace from 'foo';
      2 | export default namespace;
      3 | export {namespace};

> Output

    `␊
      1 | import * as namespace from 'foo';␊
      2 | export default namespace;␊
      3 |␊
      4 | export * as namespace from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import * as namespace from 'foo';␊
      2 | export default namespace;␊
    > 3 | export {namespace};␊
        |         ^^^^^^^^^ Use \`export…from\` to re-export \`namespace\`.␊
    `

## Invalid #44
      1 | import * as namespace from 'foo';
      2 | export {namespace};
      3 | export default namespace;

> Output

    `␊
      1 | import * as namespace from 'foo';␊
      2 |␊
      3 | export default namespace;␊
      4 | export * as namespace from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import * as namespace from 'foo';␊
    > 2 | export {namespace};␊
        |         ^^^^^^^^^ Use \`export…from\` to re-export \`namespace\`.␊
      3 | export default namespace;␊
    `

## Invalid #1
      1 | import defaultExport from 'foo';
      2 | export {defaultExport as default};
      3 | export {defaultExport as named};

> Options

    `␊
    [␊
      {␊
        "ignoreUsedVariables": true␊
      }␊
    ]␊
    `

> Output

    `␊
      1 |␊
      2 |␊
      3 |␊
      4 | export {default, default as named} from 'foo';␊
    `

> Error 1/2

    `␊
      1 | import defaultExport from 'foo';␊
    > 2 | export {defaultExport as default};␊
        |         ^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
      3 | export {defaultExport as named};␊
    `

> Error 2/2

    `␊
      1 | import defaultExport from 'foo';␊
      2 | export {defaultExport as default};␊
    > 3 | export {defaultExport as named};␊
        |         ^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`named\`.␊
    `

## Invalid #2
      1 | import {named} from 'foo';
      2 | export {named as default};
      3 | export {named as named};

> Options

    `␊
    [␊
      {␊
        "ignoreUsedVariables": true␊
      }␊
    ]␊
    `

> Output

    `␊
      1 |␊
      2 |␊
      3 |␊
      4 | export {named as default, named} from 'foo';␊
    `

> Error 1/2

    `␊
      1 | import {named} from 'foo';␊
    > 2 | export {named as default};␊
        |         ^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
      3 | export {named as named};␊
    `

> Error 2/2

    `␊
      1 | import {named} from 'foo';␊
      2 | export {named as default};␊
    > 3 | export {named as named};␊
        |         ^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`named\`.␊
    `

## Invalid #3
      1 | import {named} from 'foo';
      2 | export default named;
      3 | export {named as named};

> Options

    `␊
    [␊
      {␊
        "ignoreUsedVariables": true␊
      }␊
    ]␊
    `

> Output

    `␊
      1 |␊
      2 |␊
      3 |␊
      4 | export {named as default, named} from 'foo';␊
    `

> Error 1/2

    `␊
      1 | import {named} from 'foo';␊
    > 2 | export default named;␊
        | ^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
      3 | export {named as named};␊
    `

> Error 2/2

    `␊
      1 | import {named} from 'foo';␊
      2 | export default named;␊
    > 3 | export {named as named};␊
        |         ^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`named\`.␊
    `

## Invalid #4
      1 | import defaultExport, {named} from 'foo';
      2 | export default defaultExport;
      3 | export {named};

> Options

    `␊
    [␊
      {␊
        "ignoreUsedVariables": true␊
      }␊
    ]␊
    `

> Output

    `␊
      1 |␊
      2 |␊
      3 |␊
      4 | export {default, named} from 'foo';␊
    `

> Error 1/2

    `␊
      1 | import defaultExport, {named} from 'foo';␊
    > 2 | export default defaultExport;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
      3 | export {named};␊
    `

> Error 2/2

    `␊
      1 | import defaultExport, {named} from 'foo';␊
      2 | export default defaultExport;␊
    > 3 | export {named};␊
        |         ^^^^^ Use \`export…from\` to re-export \`named\`.␊
    `

## Invalid #5
      1 | import defaultExport, {named} from 'foo';
      2 | export {defaultExport as default, named};

> Options

    `␊
    [␊
      {␊
        "ignoreUsedVariables": true␊
      }␊
    ]␊
    `

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {default, named} from 'foo';␊
    `

> Error 1/2

    `␊
      1 | import defaultExport, {named} from 'foo';␊
    > 2 | export {defaultExport as default, named};␊
        |         ^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`default\`.␊
    `

> Error 2/2

    `␊
      1 | import defaultExport, {named} from 'foo';␊
    > 2 | export {defaultExport as default, named};␊
        |                                   ^^^^^ Use \`export…from\` to re-export \`named\`.␊
    `

## Invalid #6
      1 | import defaultExport from 'foo';
      2 | export const variable = defaultExport;

> Options

    `␊
    [␊
      {␊
        "ignoreUsedVariables": true␊
      }␊
    ]␊
    `

> Output

    `␊
      1 |␊
      2 |␊
      3 | export {default as variable} from 'foo';␊
    `

> Error 1/1

    `␊
      1 | import defaultExport from 'foo';␊
    > 2 | export const variable = defaultExport;␊
        | ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Use \`export…from\` to re-export \`variable\`.␊
    `

## Invalid #7
      1 | import {notUsedNotExported, exported} from 'foo';
      2 | export {exported};

> Options

    `␊
    [␊
      {␊
        "ignoreUsedVariables": true␊
      }␊
    ]␊
    `

> Error 1/1

    `␊
      1 | import {notUsedNotExported, exported} from 'foo';␊
    > 2 | export {exported};␊
        |         ^^^^^^^^ Use \`export…from\` to re-export \`exported\`.␊
    ␊
    --------------------------------------------------------------------------------␊
    Suggestion 1/1: Switch to \`export…from\`.␊
      1 | import {notUsedNotExported, } from 'foo';␊
      2 |␊
      3 | export {exported} from 'foo';␊
    `
