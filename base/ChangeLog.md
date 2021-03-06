### 0.20.3

+ Fixes for GHC 8.2.1 (and the corresponding `base-4.10.0`).

### 0.20.2

+ Fix fromGVariant for empty arrays, see [#91](https://github.com/haskell-gi/haskell-gi/issues/91) for details.

### 0.20.1

+ Add Data.GI.Base.CallStack, abstracting (and backporting to the
extent possible) the `HasCallStack` constraint present in newer
GHCs. Using this, we now include callstacks pervasively in the
generated code.

+ Improve the `WrappedPtr` implementation.

+ Deprecate `nulltoNothing`, it is better to simply fix the
overrides when necessary.

+ Make the semantics of GObject ownership transfer closer to those used by the Python bindings.
