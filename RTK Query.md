# RTK Query

RTK 쿼리는 Redux 애플리케이션에서 데이터 가져오기를 관리하는 데 도움이 되는 라이브러리입니다. Redux 스토어 및 감속기 생성 프로세스를 단순화하는 유틸리티 세트인 Redux Toolkit과 함께 작동하도록 설계되었습니다.

RTK 쿼리를 사용하면 데이터를 가져올 API 끝점을 정의할 수 있으며 해당 끝점에 대한 Redux 슬라이스 및 후크를 생성합니다. 그런 다음 이러한 후크를 사용하여 API에서 데이터를 가져오고 요청의 로드, 오류 및 캐싱 상태를 관리할 수 있습니다.

RTK 쿼리에는 API 요청이 완료되기 전에 새 데이터로 Redux 스토어를 업데이트할 수 있는 낙관적 업데이트에 대한 기본 제공 지원도 있습니다. 이를 통해 더 나은 사용자 경험을 제공하고 사용자가 데이터 로드를 기다리는 시간을 줄일 수 있습니다.

데이터 가져오기 외에도 RTK 쿼리는 데이터 업데이트 및 삭제, 페이지 매김 및 정렬 관리를 위한 도구도 제공합니다.

전반적으로 RTK 쿼리를 사용하면 Redux 애플리케이션에서 데이터 가져오기를 더 쉽게 관리할 수 있으며 로드, 오류 및 캐싱 상태를 일관되고 예측 가능한 방식으로 처리할 수 있습니다.



### API 엔드포인트 정의

데이터를 가져올 API 엔드포인트를 정의해야 합니다. 이는 `@rtk/query`에서 제공하는 `createApi` 기능을 사용하여 수행할 수 있습니다. 예를 들어:

```js
import { createApi, fetchBaseQuery } from '@rtk/query';

const api = createApi({
  reducerPath: 'myApi',
  baseQuery: fetchBaseQuery({ baseUrl: 'https://api.example.com' }),
  endpoints: (builder) => ({
    getUsers: builder.query({
      query: () => '/users',
    }),
  }),
});
```

이 예에서는 API의 `/users` 엔드포인트에서 데이터를 가져오는 `getUsers`라는 API 엔드포인트를 정의합니다. 또한 API에 대한 Redux 슬라이스를 생성하는 데 사용될 API에 대해 `reducerPath`를 지정합니다.



### 훅 사용

RTK 쿼리는 각 API 엔드포인트에 대한 후크를 생성합니다. 구성 요소에서 이러한 후크를 사용하여 API에서 데이터를 가져올 수 있습니다. 예를 들어:

```js
import { useGetUsersQuery } from './api';

function UserList() {
  const { data, error, isLoading } = useGetUsersQuery();

  if (isLoading) {
    return <div>Loading...</div>;
  }

  if (error) {
    return <div>Error: {error.message}</div>;
  }

  return (
    <ul>
      {data.map((user) => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

이 예에서는 RTK 쿼리에 의해 생성된 `useGetUsersQuery` 후크를 사용하여 `getUsers` 엔드포인트에서 데이터를 가져옵니다. 그런 다음 데이터를 목록으로 렌더링하여 로드 및 오류 상태를 적절하게 처리합니다.