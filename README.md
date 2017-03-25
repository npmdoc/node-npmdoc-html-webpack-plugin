# api documentation for  [html-webpack-plugin (v2.28.0)](https://github.com/ampedandwired/html-webpack-plugin)  [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-html-webpack-plugin.svg)](https://travis-ci.org/npmdoc/node-npmdoc-html-webpack-plugin)
#### Simplifies creation of HTML files to serve your webpack bundles

[![NPM](https://nodei.co/npm/html-webpack-plugin.png?downloads=true)](https://www.npmjs.com/package/html-webpack-plugin)

[![apidoc](https://npmdoc.github.io/node-npmdoc-html-webpack-plugin/build/screen-capture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-html_webpack_plugin_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-html-webpack-plugin/build..beta..travis-ci.org/apidoc.html)

![package-listing](https://npmdoc.github.io/node-npmdoc-html-webpack-plugin/build/screen-capture.npmPackageListing.svg)



# package.json

```json

{
    "author": {
        "name": "Charles Blaxland",
        "email": "charles.blaxland@gmail.com",
        "url": "https://github.com/ampedandwired"
    },
    "bugs": {
        "url": "https://github.com/ampedandwired/html-webpack-plugin/issues"
    },
    "dependencies": {
        "bluebird": "^3.4.7",
        "html-minifier": "^3.2.3",
        "loader-utils": "^0.2.16",
        "lodash": "^4.17.3",
        "pretty-error": "^2.0.2",
        "toposort": "^1.0.0"
    },
    "description": "Simplifies creation of HTML files to serve your webpack bundles",
    "devDependencies": {
        "appcache-webpack-plugin": "^1.3.0",
        "css-loader": "^0.26.1",
        "dir-compare": "1.3.0",
        "es6-promise": "^4.0.5",
        "extract-text-webpack-plugin": "^1.0.1",
        "file-loader": "^0.9.0",
        "html-loader": "^0.4.4",
        "jade": "^1.11.0",
        "jade-loader": "^0.8.0",
        "jasmine": "^2.5.2",
        "rimraf": "^2.5.4",
        "semistandard": "8.0.0",
        "style-loader": "^0.13.1",
        "underscore-template-loader": "^0.7.3",
        "url-loader": "^0.5.7",
        "webpack": "^1.14.0",
        "webpack-recompilation-simulator": "^1.3.0"
    },
    "directories": {},
    "dist": {
        "shasum": "2e7863b57e5fd48fe263303e2ffc934c3064d009",
        "tarball": "https://registry.npmjs.org/html-webpack-plugin/-/html-webpack-plugin-2.28.0.tgz"
    },
    "files": [
        "index.js",
        "default_index.ejs",
        "lib/"
    ],
    "gitHead": "9bdb6189ea630a634a84aabc81a9bbe8c47bf92b",
    "homepage": "https://github.com/ampedandwired/html-webpack-plugin",
    "keywords": [
        "webpack",
        "plugin",
        "html",
        "html-webpack-plugin"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "ampedandwired",
            "email": "charles.blaxland@gmail.com"
        },
        {
            "name": "jantimon",
            "email": "j.nicklas@me.com"
        }
    ],
    "name": "html-webpack-plugin",
    "optionalDependencies": {},
    "peerDependencies": {
        "webpack": "1 || ^2 || ^2.1.0-beta || ^2.2.0-rc"
    },
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/ampedandwired/html-webpack-plugin.git"
    },
    "scripts": {
        "build-examples": "node examples/build-examples.js",
        "prepublish": "npm run test",
        "pretest": "semistandard",
        "test": "jasmine"
    },
    "semistandard": {
        "ignore": [
            "examples/*/dist/**/*.*"
        ]
    },
    "version": "2.28.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module html-webpack-plugin](#apidoc.module.html-webpack-plugin)
1.  object <span class="apidocSignatureSpan">html-webpack-plugin.</span>chunksorter
1.  object <span class="apidocSignatureSpan">html-webpack-plugin.</span>compiler

#### [module html-webpack-plugin.chunksorter](#apidoc.module.html-webpack-plugin.chunksorter)
1.  [function <span class="apidocSignatureSpan">html-webpack-plugin.chunksorter.</span>auto (chunks)](#apidoc.element.html-webpack-plugin.chunksorter.auto)
1.  [function <span class="apidocSignatureSpan">html-webpack-plugin.chunksorter.</span>dependency (chunks)](#apidoc.element.html-webpack-plugin.chunksorter.dependency)
1.  [function <span class="apidocSignatureSpan">html-webpack-plugin.chunksorter.</span>id (chunks)](#apidoc.element.html-webpack-plugin.chunksorter.id)
1.  [function <span class="apidocSignatureSpan">html-webpack-plugin.chunksorter.</span>none (chunks)](#apidoc.element.html-webpack-plugin.chunksorter.none)

#### [module html-webpack-plugin.compiler](#apidoc.module.html-webpack-plugin.compiler)
1.  [function <span class="apidocSignatureSpan">html-webpack-plugin.compiler.</span>compileTemplate (template, context, outputFilename, compilation)](#apidoc.element.html-webpack-plugin.compiler.compileTemplate)



# <a name="apidoc.module.html-webpack-plugin"></a>[module html-webpack-plugin](#apidoc.module.html-webpack-plugin)



# <a name="apidoc.module.html-webpack-plugin.chunksorter"></a>[module html-webpack-plugin.chunksorter](#apidoc.module.html-webpack-plugin.chunksorter)

#### <a name="apidoc.element.html-webpack-plugin.chunksorter.auto"></a>[function <span class="apidocSignatureSpan">html-webpack-plugin.chunksorter.</span>auto (chunks)](#apidoc.element.html-webpack-plugin.chunksorter.auto)
- description and source-code
```javascript
auto = function (chunks) {
  if (!chunks) {
    return chunks;
  }

  // We build a map (chunk-id -> chunk) for faster access during graph building.
  var nodeMap = {};

  chunks.forEach(function (chunk) {
    nodeMap[chunk.id] = chunk;
  });

  // Next, we add an edge for each parent relationship into the graph
  var edges = [];

  chunks.forEach(function (chunk) {
    if (chunk.parents) {
      // Add an edge for each parent (parent -> child)
      chunk.parents.forEach(function (parentId) {
        // webpack2 chunk.parents are chunks instead of string id(s)
        var parentChunk = _.isObject(parentId) ? parentId : nodeMap[parentId];
        // If the parent chunk does not exist (e.g. because of an excluded chunk)
        // we ignore that parent
        if (parentChunk) {
          edges.push([parentChunk, chunk]);
        }
      });
    }
  });
  // We now perform a topological sorting on the input chunks and built edges
  return toposort.array(chunks, edges);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.html-webpack-plugin.chunksorter.dependency"></a>[function <span class="apidocSignatureSpan">html-webpack-plugin.chunksorter.</span>dependency (chunks)](#apidoc.element.html-webpack-plugin.chunksorter.dependency)
- description and source-code
```javascript
dependency = function (chunks) {
  if (!chunks) {
    return chunks;
  }

  // We build a map (chunk-id -> chunk) for faster access during graph building.
  var nodeMap = {};

  chunks.forEach(function (chunk) {
    nodeMap[chunk.id] = chunk;
  });

  // Next, we add an edge for each parent relationship into the graph
  var edges = [];

  chunks.forEach(function (chunk) {
    if (chunk.parents) {
      // Add an edge for each parent (parent -> child)
      chunk.parents.forEach(function (parentId) {
        // webpack2 chunk.parents are chunks instead of string id(s)
        var parentChunk = _.isObject(parentId) ? parentId : nodeMap[parentId];
        // If the parent chunk does not exist (e.g. because of an excluded chunk)
        // we ignore that parent
        if (parentChunk) {
          edges.push([parentChunk, chunk]);
        }
      });
    }
  });
  // We now perform a topological sorting on the input chunks and built edges
  return toposort.array(chunks, edges);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.html-webpack-plugin.chunksorter.id"></a>[function <span class="apidocSignatureSpan">html-webpack-plugin.chunksorter.</span>id (chunks)](#apidoc.element.html-webpack-plugin.chunksorter.id)
- description and source-code
```javascript
id = function (chunks) {
  return chunks.sort(function orderEntryLast (a, b) {
    if (a.entry !== b.entry) {
      return b.entry ? 1 : -1;
    } else {
      return b.id - a.id;
    }
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.html-webpack-plugin.chunksorter.none"></a>[function <span class="apidocSignatureSpan">html-webpack-plugin.chunksorter.</span>none (chunks)](#apidoc.element.html-webpack-plugin.chunksorter.none)
- description and source-code
```javascript
none = function (chunks) {
  return chunks;
}
```
- example usage
```shell
...
  }
  // Custom function
  if (typeof sortMode === 'function') {
    return chunks.sort(sortMode);
  }
  // Disabled sorting:
  if (sortMode === 'none') {
    return chunkSorter.none(chunks);
  }
  // Check if the given sort mode is a valid chunkSorter sort mode
  if (typeof chunkSorter[sortMode] !== 'undefined') {
    return chunkSorter[sortMode](chunks);
  }
  throw new Error('"' + sortMode + '" is not a valid chunk sort mode');
};
...
```



# <a name="apidoc.module.html-webpack-plugin.compiler"></a>[module html-webpack-plugin.compiler](#apidoc.module.html-webpack-plugin.compiler)

#### <a name="apidoc.element.html-webpack-plugin.compiler.compileTemplate"></a>[function <span class="apidocSignatureSpan">html-webpack-plugin.compiler.</span>compileTemplate (template, context, outputFilename, compilation)](#apidoc.element.html-webpack-plugin.compiler.compileTemplate)
- description and source-code
```javascript
function compileTemplate(template, context, outputFilename, compilation) {
  // The entry file is just an empty helper as the dynamic template
  // require is added in "loader.js"
  var outputOptions = {
    filename: outputFilename,
    publicPath: compilation.outputOptions.publicPath
  };
  // Store the result of the parent compilation before we start the child compilation
  var assetsBeforeCompilation = _.assign({}, compilation.assets[outputOptions.filename]);
  // Create an additional child compiler which takes the template
  // and turns it into an Node.JS html factory.
  // This allows us to use loaders during the compilation
  var compilerName = getCompilerName(context, outputFilename);
  var childCompiler = compilation.createChildCompiler(compilerName, outputOptions);
  childCompiler.context = context;
  childCompiler.apply(
    new NodeTemplatePlugin(outputOptions),
    new NodeTargetPlugin(),
    new LibraryTemplatePlugin('HTML_WEBPACK_PLUGIN_RESULT', 'var'),
    new SingleEntryPlugin(this.context, template),
    new LoaderTargetPlugin('node')
  );

  // Fix for "Uncaught TypeError: __webpack_require__(...) is not a function"
  // Hot module replacement requires that every child compiler has its own
  // cache. @see https://github.com/ampedandwired/html-webpack-plugin/pull/179
  childCompiler.plugin('compilation', function (compilation) {
    if (compilation.cache) {
      if (!compilation.cache[compilerName]) {
        compilation.cache[compilerName] = {};
      }
      compilation.cache = compilation.cache[compilerName];
    }
  });

  // Compile and return a promise
  return new Promise(function (resolve, reject) {
    childCompiler.runAsChild(function (err, entries, childCompilation) {
      // Resolve / reject the promise
      if (childCompilation && childCompilation.errors && childCompilation.errors.length) {
        var errorDetails = childCompilation.errors.map(function (error) {
          return error.message + (error.error ? ':\n' + error.error : '');
        }).join('\n');
        reject(new Error('Child compilation failed:\n' + errorDetails));
      } else if (err) {
        reject(err);
      } else {
        // Replace [hash] placeholders in filename
        var outputName = compilation.mainTemplate.applyPluginsWaterfall('asset-path', outputOptions.filename, {
          hash: childCompilation.hash,
          chunk: entries[0]
        });
        // Restore the parent compilation to the state like it
        // was before the child compilation
        compilation.assets[outputName] = assetsBeforeCompilation[outputName];
        if (assetsBeforeCompilation[outputName] === undefined) {
          // If it wasn't there - delete it
          delete compilation.assets[outputName];
        }
        resolve({
          // Hash of the template entry point
          hash: entries[0].hash,
          // Output name
          outputName: outputName,
          // Compiled code
          content: childCompilation.assets[outputName].source()
        });
      }
    });
  });
}
```
- example usage
```shell
...
var filename = this.options.filename;
if (path.resolve(filename) === path.normalize(filename)) {
  this.options.filename = path.relative(compiler.options.output.path, filename);
}

compiler.plugin('make', function (compilation, callback) {
  // Compile the template (queued)
  compilationPromise = childCompiler.compileTemplate(self.options.template, compiler.context, self.options.filename, compilation
)
    .catch(function (err) {
      compilation.errors.push(prettyError(err, compiler.context).toString());
      return {
        content: self.options.showErrors ? prettyError(err, compiler.context).toJsonHtml() : 'ERROR',
        outputName: self.options.filename
      };
    })
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
