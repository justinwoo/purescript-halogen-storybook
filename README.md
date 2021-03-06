# purescript-halogen-storybook

<a href="https://pursuit.purescript.org/packages/purescript-halogen-storybook">
  <img src="https://pursuit.purescript.org/packages/purescript-halogen-storybook/badge"
       alt="purescript-halogen-storybook on Pursuit">
  </img>
</a>

A library to assemble examples or develop components separately.

[DEMO](https://rnons.github.io/purescript-halogen-storybook/)

## How to use

First define the stories. Each story consists of a name and a component.

```
import Halogen.Storybook (Stories, runStorybook, proxy)

stories :: forall m. Stories m
stories = SM.fromFoldable
  [ Tuple "count" $ proxy $ ExpCount.component
  , Tuple "input" $ proxy $ ExpInput.component
  ]
```

Then add a `runStorybook` line to your main function. That's it.

```
main = HA.runHalogenAff do
  body <- HA.awaitBody
  runStorybook stories body
```
