# daisyui

Helper components for using slimplate with daisyui

For more information and general usage instructions, checkout [slimplate](http://slimplate.github.io)


## installation

```
npm i @slimplate/daisyui
```

## usage

Here is an example of a page that has an editor sidebar made with daisyui:

```js
import { EditorPage } from '@slimplate/daisyui'
import s from '@/../.slimplate.json'
const { collections, repo, branch } = s

const collection = collections.blog
const components = {}

// give this component blogPost, and it will render it with an editor sidebar

export default function PageMine({ blogPost }) {
  return (
    <EditorPage onUpdate={updatePost} item={blogPost} collection={collection} proxy={process.env.NEXT_PUBLIC_CORS_PROXY} repo={repo} branch={branch || 'main'}>
      <main className='prose m-auto mb-4'>
        <MDXRemote {...blogPost.mdx} components={components} />
      </main>
    </EditorPage
  )
}
```

There are a few other heloper components you can add to your site to do things:

```js
import {
  ButtonSync, // tracks current state of repo and allows user to sync with remote
  ButtonLoginGithub // tracks current user-state, and allows users to login/logout
} from '@slimplate/daisyui'
```