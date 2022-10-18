# Todo List using Vue

## tools:

1. Vue 3
2. Vite
3. SASS
4. Composition API with extracted logic

## Features:

1. Use **Vite** to startup project
2. Use **SASS** to style component
3. Use **Vue** as frontend framework
4. Use **Composition API** with **extracted logic** to make code easy-organized.
    - If you want to know more about <u>composition API</u>, please [read this offical document](https://vuejs.org/guide/introduction.html#composition-api).
    - More infomation about <u>extracted logic code</u>, please [read this articles](https://learnvue.co/tutorials/composition-api-reusability). this is a abstract concept like React hook, which make the code logic be more reusable.

## Installation
1. git clone this project
2. run `npm install`
3. run `npm run dev`
4. then you can see this project is running on http://127.0.0.1:5173/

## Deploy
1. run `npm run build`
2. run `npm install -g serve` (a stastic file server from Node.js)
3. (You can't just open dist/index.html, this won't work.)
4. run `serve -s dist`
5. open http://localhost:3000 and you can see your final project
6. read [this document](https://cli.vuejs.org/guide/deployment.html#previewing-locally) if you want to know more detail

> Sometimes your project might work well through executing `npm run dev` but not work as expected when you build out.  So please don't ignore this step!

## Code Steps
(懶得寫英文...)  

我是先寫 Todo component (TodoList)，寫完後覺得有可以再細拆的地方，於是再把 todo 裡面的詳細內容獨立出來成 TodoListItem。

從 template 裡面就能知道一個元件大概需要哪些 props 跟 emits，這時就可以回到 root component (App.vue) 寫 logic 了。在 root component 建立 data (ref) 作為 props；以及 functions 作為 emits。

用同樣方式寫 Form Component。

現在 Todo 的核心功能 (CRUD 沒有 U) 完成了，可以再追加一些額外 features，例如「隱藏已完成清單 (hide completed)」。**但現在會有個問題： todo 的邏輯和 hide complete 的邏輯會全部擠在 App 裡 (root component 或 parent component)**。如此會很難進行後續維護，所以最好把 todo feature 跟 hide complete feature 的邏輯拆開再分別 import。

### Extract logic code

1. create new folder `logic` inside `src`
2. create new files: `useTodoComponent.vue` and `useHidecompletedComponent.vue`
3. move logic codes about <u>todo-feature</u> from `App.vue` to `useTodoComponent.vue`
4. repeat same step in step 3. (migrate code of <u>hide-complete</u> into `useHidecompletedComponent.vue`)
5. import and use `useTodoComponent`, `useHidecompletedComponent` in `App`

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar)
