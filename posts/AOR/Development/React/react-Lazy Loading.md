#aor
### Lazy Loading
>[!info]
>지연 로딩
>
>> React는 SPA이기 때문에 처음에 너무 많은 파일을 불러오면, 시간이 오래걸려 사용자 경험이 나빠질 수 있으니, 전체를 미리 불러오는 것이 아닌, 필요한 컴포넌트들만 미리 불러오는 것을 지연 로딩이라고 한다.
>

사용법: 
1. `import`문을 `App.js` 파일에 사용하게 되면 무조건 해당하는 것을 첫 request시 가져와야 한다. 
	-> 그래서 `import`문을 가장 위에 두지 말고  

- `import`문은 `promise`객체를 반환한다.

>[!info]
>`React.lazy()`
>
>>한번에 JavaScript 번들이 사용자에게 전송되지 않기 위해, 필요할 때만 동적으로 컴포넌트를 가져와 React App의 성능을 도와주는 메서드

>[!info]
>`<Suspense>`
>
>> 지연 상태를 표시하기 위해 사용되는 React 구성요소 (Loading Spinner)

- 지연 로딩을 사용하지 않았을 경우의 `App.js`
- `App.js`와 관련된 모든 `import` 된 파일을 렌더링 되기 전에 가져온다.
```jsx
import { createBrowserRouter, RouterProvider } from 'react-router-dom';

import BlogPage, { loader as postsLoader } from './pages/Blog';
import HomePage from './pages/Home';
import PostPage, { loader as postLoader } from './pages/Post';
import RootLayout from './pages/Root';
  
const router = createBrowserRouter([
  {
    path: '/',
    element: <RootLayout />,
    children: [
      {
        index: true,
        element: <HomePage />,
      },
      {
        path: 'posts',
        children: [
          { index: true, element: <BlogPage />, loader: postsLoader },
          { path: ':id', element: <PostPage />, loader: postLoader },
        ],
      },
    ],
  },
]);
  
function App() {
  return <RouterProvider router={router} />;
}
  
export default App;
```

- 지연 로딩을 사용했을 경우의 `App.js`
- `import`된 파일을 렌더링 전에 가져오며, 특정 컴포넌트들은 필요시 `lazy()`메서드에 의해 가져오게 된다.
```jsx
import { createBrowserRouter, RouterProvider } from 'react-router-dom';
import { lazy, Suspense } from 'react'; // <- lazy와 Suspense 요소를 가져와
// import BlogPage, { loader as postsLoader } from './pages/Blog'; <- 지연 로딩 적용 부분

import HomePage from './pages/Home';
// import PostPage, { loader as postLoader } from './pages/Post'; <- 지연 로딩 적용 부분
import RootLayout from './pages/Root';

const BlogPage = lazy() => import('./pages/Blog'); // 컴포넌트를 동적으로 불러오기 위해 React.lazy() 메서드 활용

const PostPage = lazy() => import('./pages/Post'); 

const router = createBrowserRouter([
  {
    path: '/',
    element: <RootLayout />,
    children: [
      {
        index: true,
        element: <HomePage />,
      },
      {
        path: 'posts',
        children: [
          { 
	          index: true, 
	          element: 
	          <Suspense fallback={<p>Loading...</p>}>
		          <BlogPage />
	          </Suspense>, // 코드를 가져오는 동안의 지연 상태를 표시하기 위해 사용하는 요소(Loading Spinner)
		      loader: () => import('./pages/Blog').then(module => module.loader()) },
          { 
          path: ':id', 
          element: 
	          <Suspense fallback={<p>Loading...</p>}>
		          <PostPage />
	          </Suspense>, 
          loader: (meta) => import('./pages/Post').then((module) => module.loader(meta)) 
          },
        ],
      },
    ],
  },
]);
  
function App() {
  return <RouterProvider router={router} />;
}
  
export default App;
```

### [React](../../Dev-Index/React.md)로 돌아가기