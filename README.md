# Problem with installing DataDog tracing library

To reproduce, clone this repository. Then do

```
yarn install
yarn build
```

This produces the following error on my machines (macOS M2 and Linux x86, both with Node.js version 14):

```
yarn run v1.22.19
warning package.json: No license field
$ webpack
asset bundle.js 2.57 MiB [emitted] (name: main)
runtime modules 1.04 KiB 5 modules
cacheable modules 2.05 MiB 476 modules
+ 27 modules

WARNING in ./node_modules/express/lib/view.js 81:13-25
Critical dependency: the request of a dependency is an expression
 @ ./node_modules/express/lib/application.js 22:11-28
 @ ./node_modules/express/lib/express.js 18:12-36
 @ ./node_modules/express/index.js 11:0-41
 @ ./index.ts 2:0-35 3:10-17

1 warning has detailed information that is not shown.
Use 'stats.errorDetails: true' resp. '--stats-error-details' to show it.

ERROR in ./node_modules/dd-trace/packages/datadog-plugin-graphql/src/tools/transforms.js 9:18-53
Module not found: Error: Can't resolve 'graphql/language/visitor' in '/Users/sven/development/ct/datadog/node_modules/dd-trace/packages/datadog-plugin-graphql/src/tools'
 @ ./node_modules/dd-trace/packages/datadog-plugin-graphql/src/tools/signature.js 6:21-44
 @ ./node_modules/dd-trace/packages/datadog-plugin-graphql/src/tools/index.js 6:18-40
 @ ./node_modules/dd-trace/packages/datadog-plugin-graphql/src/index.js 219:25-43
 @ ./node_modules/dd-trace/packages/dd-trace/src/plugins/index.js 26:28-74
 @ ./node_modules/dd-trace/packages/dd-trace/src/plugin_manager.js 5:16-36
 @ ./node_modules/dd-trace/packages/dd-trace/src/proxy.js 10:22-49
 @ ./node_modules/dd-trace/packages/dd-trace/src/index.js 10:4-22
 @ ./node_modules/dd-trace/packages/dd-trace/index.js 4:22-38
 @ ./node_modules/dd-trace/index.js 3:0-47
 @ ./node_modules/dd-trace/init.js 3:15-27
 @ ./index.ts 1:0-23

ERROR in ./node_modules/dd-trace/packages/datadog-plugin-graphql/src/tools/transforms.js 10:18-53
Module not found: Error: Can't resolve 'graphql/language/printer' in '/Users/sven/development/ct/datadog/node_modules/dd-trace/packages/datadog-plugin-graphql/src/tools'
 @ ./node_modules/dd-trace/packages/datadog-plugin-graphql/src/tools/signature.js 6:21-44
 @ ./node_modules/dd-trace/packages/datadog-plugin-graphql/src/tools/index.js 6:18-40
 @ ./node_modules/dd-trace/packages/datadog-plugin-graphql/src/index.js 219:25-43
 @ ./node_modules/dd-trace/packages/dd-trace/src/plugins/index.js 26:28-74
 @ ./node_modules/dd-trace/packages/dd-trace/src/plugin_manager.js 5:16-36
 @ ./node_modules/dd-trace/packages/dd-trace/src/proxy.js 10:22-49
 @ ./node_modules/dd-trace/packages/dd-trace/src/index.js 10:4-22
 @ ./node_modules/dd-trace/packages/dd-trace/index.js 4:22-38
 @ ./node_modules/dd-trace/index.js 3:0-47
 @ ./node_modules/dd-trace/init.js 3:15-27
 @ ./index.ts 1:0-23

ERROR in ./node_modules/dd-trace/packages/datadog-plugin-graphql/src/tools/transforms.js 11:20-48
Module not found: Error: Can't resolve 'graphql/utilities' in '/Users/sven/development/ct/datadog/node_modules/dd-trace/packages/datadog-plugin-graphql/src/tools'
 @ ./node_modules/dd-trace/packages/datadog-plugin-graphql/src/tools/signature.js 6:21-44
 @ ./node_modules/dd-trace/packages/datadog-plugin-graphql/src/tools/index.js 6:18-40
 @ ./node_modules/dd-trace/packages/datadog-plugin-graphql/src/index.js 219:25-43
 @ ./node_modules/dd-trace/packages/dd-trace/src/plugins/index.js 26:28-74
 @ ./node_modules/dd-trace/packages/dd-trace/src/plugin_manager.js 5:16-36
 @ ./node_modules/dd-trace/packages/dd-trace/src/proxy.js 10:22-49
 @ ./node_modules/dd-trace/packages/dd-trace/src/index.js 10:4-22
 @ ./node_modules/dd-trace/packages/dd-trace/index.js 4:22-38
 @ ./node_modules/dd-trace/index.js 3:0-47
 @ ./node_modules/dd-trace/init.js 3:15-27
 @ ./index.ts 1:0-23

3 errors have detailed information that is not shown.
Use 'stats.errorDetails: true' resp. '--stats-error-details' to show it.

webpack 5.74.0 compiled with 3 errors and 1 warning in 1167 ms
error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.
```
