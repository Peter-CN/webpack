# TODO

- Increased minimal node.js version from 6 to 8
- removed buildin directory and replaced buildins with runtime modules
- Removed deprecated features
  - BannerPlugin now only support an options object
- removed CachePlugin
- Chunk.entryModule is deprecated
- Chunk.hasEntryModule is deprecated
- Chunk.addModule is deprecated
- Chunk.removeModule is deprecated
- Chunk.getNumberOfModules is deprecated
- Chunk.modulesIterable is deprecated
- Chunk.compareTo is deprecated
- Chunk.containsModule is deprecated
- Chunk.getModules is deprecated
- Chunk.remove is deprecated
- Chunk.moveModule is deprecated
- Chunk.integrate is deprecated
- Chunk.canBeIntegrated is deprecated
- Chunk.isEmpty is deprecated
- Chunk.modulesSize is deprecated
- Chunk.size is deprecated
- Chunk.integratedSize is deprecated
- Chunk.getChunkModuleMaps is deprecated
- Chunk.hasModuleInGraph is deprecated
- Chunk.updateHash signature changed
- Chunk.getChildIdsByOrders signature changed (TODO: consider moving to ChunkGraph)
- Chunk.getChildIdsByOrdersMap signature changed (TODO: consider moving to ChunkGraph)
- Chunk.getChunkModuleMaps removed
- Chunk.setModules removed
- deprecated Chunk methods removed
- ChunkGraph added
- ChunkGroup.setParents removed
- ChunkGroup.containsModule removed
- ChunkGroup.remove no longer disconnected the group from block
- ChunkGroup.compareTo signature changed
- ChunkGroup.getChildrenByOrders signature changed
- ChunkGroup index and index renamed to pre/post order index
  - old getter is deprecated
- ChunkTemplate.hooks.modules sigature changed
- ChunkTemplate.hooks.render sigature changed
- ChunkTemplate.updateHashForChunk sigature changed
- Compilation.hooks.normalModuleLoader is deprecated
  - MIGRATION: Use `NormalModule.getCompilationHooks(compilation).loader` instead
- Compilation.hooks.optimizeChunkOrder removed
- Compilation.hooks.optimizeModuleOrder removed
- Compilation.hooks.advancedOptimizeModuleOrder removed
- Compilation.hooks.optimizeDependenciesBasic removed
- Compilation.hooks.optimizeDependenciesAdvanced removed
- Compilation.hooks.optimizeModulesBasic removed
- Compilation.hooks.optimizeModulesAdvanced removed
- Compilation.hooks.optimizeChunksBasic removed
- Compilation.hooks.optimizeChunksAdvanced removed
- Compilation.hooks.optimizeChunkModulesBasic removed
- Compilation.hooks.optimizeChunkModulesAdvanced removed
- Compilation.hooks.optimizeExtractedChunksBasic removed
- Compilation.hooks.optimizeExtractedChunks removed
- Compilation.hooks.optimizeExtractedChunksAdvanced removed
- Compilation.hooks.afterOptimizeExtractedChunks removed
- Compilation.entries removed
  - MIGRATION: Use `Compilation.entryDependencies` instead
- Compilation.\_preparedEntrypoints removed
- dependencyTemplates is now a `DependencyTemplates` class instead of a raw `Map`
- Compilation.fileTimestamps and contextTimestamps removed
  - MIGRATION: Use `Compilation.fileSystemInfo` instead
- Compilation.waitForBuildingFinished removed
  - MIGRATION: Use the new queues
- Compilation.addModuleDependencies removed
- Compilation.prefetch removed
- Compilation.hooks.beforeHash is now called after the hashes of modules are created
  - MIGRATION: Use `Compiliation.hooks.beforeModuleHash` instead
- Compilation.applyModuleIds removed
- Compilation.applyChunkIds removed
- Compiler.root added which points to the root compiler
  - it can be used to cache data in WeakMaps instead of statically scoped
- Source.emitted is no longer set by the Compiler
  - MIGRATION: Check `Compilation.emittedAssets` instead
- Compiler/Compilation.compilerPath added: It's a unique name of the compiler in the compiler tree. (Unique to the root compiler scope)
- Compiler.name: When generating a compiler name with absolute paths make sure to separate them which `|` or `!` from other parts of the name.
  - Using space a separator is now deprecated. (Paths could contain spaces)
  - Hint: `|` is replaced with space in Stats string output.
- Module.needRebuild deprecated
  - MIGRATION: use `Module.needBuild` instead
- Dependency.getReference signature changed
- Dependency.getExports signature changed
- Dependency.getWarnings signature changed
- Dependency.getErrors signature changed
- Dependency.updateHash signature changed
- Dependency.module removed
- There is now a base class for DependencyTemplate
- SingleEntryDependency removed
- MultiEntryDependency removed
- EntryDependency added
- Chunks can now have multiple entry modules
- EntryModuleNotFoundError removed
- SingleEntryPlugin removed
- EntryPlugin added
- ExtendedAPIPlugin removed
  - MIGRATION: No longer need, `__webpack_hash__` and `__webpack_chunkname__` can always be used and runtime code is injected as needed
- Generator.getTypes added
- Generator.getSize added
- Generator.generate signature changed
- HotModuleReplacementPlugin.getParserHooks added
- Parser was moved to JavascriptParser
- ParserHelpers was moved to JavascriptParserHelpers
- MainTemplate.hooks.moduleObj removed
- MainTemplate.hooks.currentHash removed
- MainTemplate.hooks.addModule removed
- MainTemplate.hooks.requireEnsure removed
- MainTemplate.hooks.globalHashPaths removed
- MainTemplate.hooks.globalHash removed
- MainTemplate.hooks.hotBootstrap removed
- MainTemplate.hooks some signatures changed
- Module.hash deprecated
- Module.renderedHash deprecated
- Module.reasons removed
- Module.id deprecated
- Module.index deprecated
- Module.index2 deprecated
- Module.depth deprecated
- Module.issuer deprecated
- Module.profile removed
- Module.prefetched removed
- Module.built removed
- Module.used removed
- Module.usedExports deprecated
- Module.optimizationBailout deprecated
- Module.exportsArgument removed
- Module.optional deprecated
- Module.disconnect removed
- Module.unseal removed
- Module.setChunks removed
- Module.addChunk deprecated
- Module.removeChunk deprecated
- Module.isInChunk deprecated
- Module.isEntryModule deprecated
- Module.getChunks deprecated
- Module.getNumberOfChunks deprecated
- Module.chunksIterable deprecated
- Module.hasEqualsChunks removed
- Module.useSourceMap moved to NormalModule
- Module.addReason removed
- Module.removeReason removed
- Module.rewriteChunkInReasons removed
- Module.isUsed removed
  - MIGRATION: Use `isModuleUsed`, `isExportUsed` and `getUsedName` instead
- Module.updateHash signature changed
- Module.sortItems removed
- Module.unbuild removed
  - MIGRATION: Use `invalidateBuild` instead
- Module.getSourceTypes added
- Module.getRuntimeRequirements added
- Module.size signature changed
- ModuleFilenameHelpers.createFilename signature changed
- ModuleProfile class added with more data
- ModuleReason removed
- ModuleTemplate.hooks signatures changed
- ModuleTemplate.render signature changed
- Compiler.dependencies removed
  - MIGRATION: Use `MultiCompiler.setDependencies` instead
- MultiModule removed
- MultiModuleFactory removed
- `exec` removed from loader context
  - MIGRATION: This can be implemented in the loader itself
- ProgressPlugin `entries` option now defaults to on
- ProgressPlugin no longer uses tapable context for `reportProgress`
  - MIGRATION: Use `ProgressPlugin.getReporter(compiler)` instead
- ProvidePlugin is no re-enabled for `.mjs` files
- RuntimeTemplate methods now take `runtimeRequirements` arguments
- Stats json `errors` and `warnings` now no longer contain strings but objects with information splitted into properties.
  - MIGRATION: Access the information on the properties. i. e. `message`
- Stats.jsonToString removed
- Stats.filterWarnings removed
- Stats.getChildOptions removed
- Stats helper methods removed
- Stats.toJson signature changed (second argument removed)
- Stats.presetToOptions removed
  - MIGRATION: Use `compilation.createStatsOptions` instead
- ExternalModule.external removed
- HarmonyInitDependency removed
- Dependency.getInitFragments deprecated
  - MIGRATION: Use `apply` `initFragements` instead

# Changes to the Configuration

## Changes to the structure

- `cache: Object` removed: Setting to a memory-cache object is no longer possible
- `cache.type` added: It's no possible to choose between `"memory"` and `"filesystem"`
- New configuration options for `cache.type = "filesystem"` added:
  - `cache.cacheDirectory`
  - `cache.name`
  - `cache.version`
  - `cache.store`
  - `cache.loglevel`
  - `cache.hashAlgorithm`
- `resolve.cache` added: Allows to disable/enable the safe resolve cache
- `resolve.concord` removed
- Automatic polyfills for native node.js modules were removed - `node.Buffer` removed - `node.console` removed - `node.process` removed - `node.*` (node.js native module) removed - MIGRATION: `resolve.alias` and `ProvidePlugin`. Errors will give hints.
- `optimization.chunkIds: "deterministic"` added
- `optimization.moduleIds: "deterministic"` added
- `optimization.moduleIds: "hashed"` deprecated
- `optimization.moduleIds: "total-size"` removed
- Deprecated flags for module and chunk ids were removed - `optimization.hashedModuleIds` removed - `optimization.namedChunks` removed - `optimization.namedModules` removed - `optimization.occurrenceOrder` removed - MIGRATION: Use `chunkIds` and `moduleIds`
- `optimization.splitChunks` sizes can now be objects with a size per source type
  - `minSize` - `maxSize` - `maxAsyncSize` - `maxInitialSize`
- `optimization.splitChunks` `maxAsyncSize` and `maxInitialSize` added next to `maxSize`: allows to specify different max sizes for initial and async chunks
- `optimization.splitChunks` `name: true` removed: Automatic names are no longer supported
  - MIGRATION: Use the default. `chunkIds: "named"` will give your files useful names for debugging
- `optimization.splitChunks.cacheGroups[].idHint` added: Gives a hint how the named chunk id should be chosen
- `optimization.splitChunks` `automaticNamePrefix` removed
  - MIGRATION: Use `idHint` instead
- `output.devtoolLineToLine` removed
  - MIGRATION: No replacement
- `output.hotUpdateChunkFilename: Function` is now forbidden: It never worked anyway.
- `output.hotUpdateMainFilename: Function` is now forbidden: It never worked anyway.
- `stats.chunkRootModules` added: Show root modules for chunks
- `stats.orphanModules` added: Show modules which are not emitted
- `stats.runtime` added: Show runtime modules
- `BannerPlugin.banner` signature changed - `data.basename` removed - `data.query` removed - MIGRATION: extract from `filename`
- `SourceMapDevToolPlugin` `lineToLine` removed
  - MIGRATION: No replacement
- `[hash]` as hash for the full compilation is now deprecated
  - MIGRATION: Use `[fullhash]` instead or better use another hash option
- `[modulehash]` is deprecated
  - MIGRATION: Use `[hash]` instead
- `[moduleid]` is deprecated
  - MIGRATION: Use `[id]` instead

## Changes to the defaults

- `module.unsafeCache` is now only enabled for `node_modules` by default
- `optimization.moduleIds` defaults to `deterministic` in production mode instead of `size`
- `optimization.chunkIds` defaults to `deterministic` in production mode instead of `total-size`
- `optimization.nodeEnv` defaults to `false` in `none` mode
- `resolve(Loader).cache` defaults to `true` when a `cache` is used
- `resolve(Loader).cacheWithContext` defaults to `false`

# Major Changes

## Removed deprecated things

MIGRATION: Make sure that your webpack 4 build don't print deprecation warnings.

## Automatic node.js polyfills removed

In the early days webpack aimed to allow to run most node.js modules in the browser, but the module landscape changed and many modules uses are now written for frontend purposes. webpack <= 4 ships with polyfills for many of the node.js core modules. They are automatically applied once a module uses i. e. the `crypto` module.

While this makes using modules written for node.js easy, it adds these huge polyfills to the bundle. In many cases these polyfills are even unneeded.

webpack 5 stopped to automatically polyfill these core modules and tried to focus on frontend-compatible modules.

MIGRATION:

- Try to use frontend-compatible modules when possible.
- It's possible to manually add the polyfill for a node.js core module. The error message gives a hint how to do that.
- Package authors: Use the `browser` field in `package.json` to make a package frontend-compatible. Provide alternative implementations/dependencies for the browser.

## Deterministic chunk and module ids

New algorithms were added for long term caching. These are enabled by default in production mode.

`chunkIds: "deterministic", moduleIds: "deterministic"`

The algorithms assing short (3 char) numberic ids to modules and chunks in a deterministic way. This is a trade-off between bundle size and long term caching.

MIGRATION: Best use the default values for `chunkIds` and `moduleIds`. You can also opt-in to the old defaults `chunkIds: "size", moduleIds: "size"`, this will create smaller bundles, but invalidate them more often for caching.

## Named chunk ids

A new named chunk id algorithm enabled by default in development mode gives chunk (and filename) useful names. Chunk id is determined by chunk content.

So you no longer need to use `import(/* webpackChunkName: "name" */ "module")` for debugging.

It's possible to use `chunkIds: "named"` in production, but make sure to not accidentically expose sensitive information about module names.

## Compiler idle and close

Compilers now need to be closed after using. Compilers now enter and leave idle state and have hooks for this. Plugins may use this to do unimportant work. i. e. the Persistent cache slowy stores the cache to disk. On compiler close remaining work should be finished as fast as possible. A callback signals closing done.

Plugins should expect that some users may forget to close the Compiler, so all work should eventually be finishing in idle too. Process should be prevented from exiting when work is done.

The `webpack()` fasade automatically calls close when passing a callback.

MIGRATION: When using the node.js API make sure to call `Compiler.close` when done.

# Major internal Changes

The following changes are only relavant when writing plugins:

## Runtime Modules

A large part of runtime code was moved into so called "runtime modules". These special modules add runtime code. They can be added in any chunk, but are currently always added to the runtime chunk. "Runtime requirements" control which runtime modules are added to the bundle. This ensures that only runtime code that is used is added to the bundle. In future runtime modules could also added to on-demand-loaded chunk to load runtime code when needed.

The core runtime is now very small and only includes the `__webpack_require__` function, module factories and module instance cache. In future an alternative code runtime can be used to avoid wrapping the bundle in a IIFE and allow ESM style exports. This will allow ESM as target.

As some responsibilities from Main and ChunkTemplate were removed, also are some hooks.

## Serialization

A serialization mechanism was added to allow serialization of complex objects in webpack. It has a opt-in semantic, so classes that should be serialized need to be explicitly flagged (and serialization implemented). This has been done for most Modules, all Dependencies and some Errors.

## Extensible Caching

A `Cache` class with a plugin interface has been added. This class can be used to write and read to the cache. Depending on configuration different plugins add the functionality to the cache. The `MemoryCachePlugin` adds in-memory caching. The `FileCachePlugin` adds persistent caching.

The `FileCachePlugin` uses the serialization mechanism to persist and restore cached items to disk.

## Hook object frozen

Classes with `hooks` have their `hooks` object frozen, so adding custom hooks is no longer possible this way. The recommended way to add custom hooks is via WeakMap and a static `getXXXHooks(XXX)` (i. e. `getCompilationHook(compilation)`) method. Internal classes use the same mechanism for custom hooks.

## Tapable base class removed

The compat layer for webpack 3 plugins was removed. It has been deprecated for webpack 4.

## Staged hooks

For some steps in the sealing process there has been multiple hooks for different stages. i. e. `optimizeDependenciesBasic` `optimizeDependencies` and `optimizeDependenciesAdvanced`. These has been removed in favor of a single hook which should be used with a `stage` option. See `OptimizationStages` for possible stage values.

## Order and ids

webpack used to order modules and chunks in the Compilation is a specific way to assign ids in a incremental matter. This is no longer the case. The order will no longer be used for id generation. Instead the full control of id generation is in the plugin.

Hooks to optimize the order of module and chunks has been removed.

## Arrays to Sets

- Compilation.modules is now a Set
- Compilation.chunks is now a Set

There is a compat-layer which prints deprecation warnings.

## Compilation.fileSystemInfo

This new class can be used to access information about the filesystem in a cache way. Currently it allows to ask for file and directory timestamps. Information about timestamps is transferred from the watcher if possible, otherwise determined by filesystem access.

In future asking for file content hashes will be added and modules can check validity with file content instead of file hashes.

## Hot Module Replacement

HMR runtime has be refactored to Runtime Modules. `HotUpdateChunkTemplate` has been merged into `ChunkTemplate`. ChunkTemplates and plugins should now also handle `HotUpdateChunk`s.

The javascript part of HMR runtime has be separated from the core HMR runtime. Other module types can now also handle HMR in a own way. In future this allows i. e. HMR for the mini-css-extract-plugin or for WASM modules.

## Work Queues

webpack used to handle module processing with functions calling functions and a `semaphore` which limits parallelism. The `Compilation.semaphore` has been removed and async queues now handle work queuing and processing. Each step has a separate queue:

- `Compilation.factorizeQueue`: calling the module factory for a group of dependencies
- `Compilation.addModuleQueue`: adding the module to the compilation (may restores module from cache)
- `Compilation.buildQueue`: building the module if neccessary (may stores module to cache)
- `Compilation.rebuildQueue`: building a module again if manually triggered
- `Compilation.processDependenciesQueue`: processing dependencies of a module

These queues have some hooks to watch and intercept job processing.

In future multiple compilers may work together and job coordination can be done by intercepting these queues.

## Module and Chunk Graph

webpack used to store the resolve module in the dependency and used to store the contained modules in the chunk. This is no longer the case. All information about how modules are connected in the module graph are now stored in a ModuleGraph class. All information about how module are connected with chunks are stored in the ChunkGraph class. Information which depend on i. e. the chunk graph is also stored in the related class.

This means the following information about modules have been moved:

- Module connections -> ModuleGraph
- Module issuer -> ModuleGraph
- Module optimization bailout -> ModuleGraph (TODO check if it should ChunkGraph instead)
- Module usedExports -> ModuleGraph
- Module pre order index -> ModuleGraph
- Module post order index -> ModuleGraph
- Module depth -> ModuleGraph
- Module profile -> ModuleGraph
- Module id -> ChunkGraph
- Module hash -> ChunkGraph
- Module runtime requirements -> ChunkGraph
- Module is in chunk -> ChunkGraph
- Module is entry in chunk -> ChunkGraph
- Module is runtime module in chunk -> ChunkGraph
- Chunk runtime requirements -> ChunkGraph

webpack used disconnect modules from the graph when restored from cache. This is no longer necessary. Module store no info about the graph and can technically used in multiple graphs. This makes caching easier.

There is a compat-layer for most of these changes which prints a deprecation warning when used.

MIGRATION: Use the new APIs on ModuleGraph and ChunkGraph

## Init fragments

DependenciesBlockVariables has been removed in favor of InitFragments. DependencyTemplates can now add InitFragments to inject code to the top of the module source. InitFragments allow deduplication.

## Module source types

Modules now have to tell which source types they support via `Module.getSourceTypes()`. Depending on that different plugins call `source()` with this types. i. e. for source type `javascript` the `JavascriptModulesPlugin` embed the source code into the bundle. Source type `webassembly` will make the `WebAssemblyModulesPlugin` emit a wasm file. Custom source types are possible, i. e. the mini-css-extract-plugin will probably use the source type `stylesheet` to embed the source code into the css file.

There is no relationship between module type and source type. i. e. module type `json` also uses source type `javascript` and module type `webassembly/experimental` uses source types `javascript` and `webassembly`.

## Extensible Stats

Stats preset, default, json and toString are now baked by a plugin system. Converted the current Stats into plugins.

---

lib/dependencies/HarmonyExportImportedSpecifierDependency.js
