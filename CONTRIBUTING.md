# Contributing

## Ideas / decisions

- Abstract over Js_of_ocaml "native" types (`js_string `, `js_array`) as much as
possible behind the bindings. To do so, the library uses [`gen_js_api`](https://github.com/LexiFi/gen_js_api)
to convert from/to these types to their more idiomatic OCaml representation.
- Keep the API as close as possible to ReasonReact. This is useful for many reasons:
  - Battle tested.
  - Reduce cognitive load by leveraging ReasonReact knowledge.
  - Maximize potential reuse of existing components and libraries.

## Bindings

See [`interop.md`](interop.md).

## Running the example

```bash
git clone https://github.com/jchavarri/jsoo-react/
cd ./jsoo-react
make init
eval $(opam env)
make start
# in another tab / terminal session 
cd ./jsoo-react/example
yarn && yarn start
```

After that, open up `localhost:8000`. Then modify `App.re` file in `src` and refresh the page to see the changes. The example
will not work without server as it relies on history / client-side routing using `jsoo-react` router to navigate through the pages.

### Ppx

- `make test` to run the test against the expected result.
- `make test-promote` when you want to update the expected results.

