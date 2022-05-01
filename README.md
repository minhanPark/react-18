# React-18 기능

## Suspense

리액트의 Suspense는 컴포넌트가 읽어들이고 있는 데이터가 아직 준비되지 않았다고 React에 알려줄 수 있는, **데이터 불러오기 라이브러리에서 사용할 수 있는 메커니즘**입니다.  
데이터 로딩, 이미지, 스크립트, 그밖의 비동기 작업을 기다리는데 사용할 수 있고, **기다리는 동안 로딩 상태를 선언적으로 지정**할 수 있습니다.

```js
function ProfilePage() {
  return (
    <Suspense fallback={<h1>Loading profile...</h1>}>
      <ProfileDetails />
      <Suspense fallback={<h1>Loading posts...</h1>}>
        <ProfileTimeline />
      </Suspense>
    </Suspense>
  );
}
```

위와 같이 리다리는 동안 보여 줄 로딩 컴포넌트 등은 fallback 속성에 넣어주면 된다.

## React Server Component

서버 컴포넌트는 리액트 컴포넌트를 서버에서 렌더링 할 수 있도록 해준다.  
그러면 클라이언트 쪽에선 자바스크립트가 필요없어질 것이고, 중간에 서버가 사라지니까, 페이지 렌더링도 더 빠르게 만들어줄 수 있다.

> 중간 이름 server를 추가해주자. ex) home.server.js  
> 서버 컴포넌트를 사용하도록 설정했다면 클라이언트에서만 렌더링 되는 것은 중간 이름에 client를 넣어줘야한다.
