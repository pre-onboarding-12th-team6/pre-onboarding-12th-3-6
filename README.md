# TEAM6 - 검색 자동완성 애플리케이션

프리온보딩 3주차에 진행한 과제물입니다.  
기간 : 2023.09.05. ~ 2023.09.08.  

## 배포 링크

[배포 링크](https://clinical-trials-398306.du.r.appspot.com/)

## 👥 팀원

<table border>
  <tbody>
    <tr>
      <td align="center" width="200px">
        <img width="100%" src="https://avatars.githubusercontent.com/u/106734517?v=4"  alt=""/><br />
        <a href="https://github.com/iziz9">
          <img src="https://img.shields.io/badge/강현주-1E90FF?style=flat-round&logo=GitHub&logoColor=white"/>
        </a>
      </td>
      <td align="center" width="200px">
        <img width="100%" src="https://avatars.githubusercontent.com/u/94212747?s=96&v=4"  alt=""/><br />
        <a href="https://github.com/NR0617">
          <img src="https://img.shields.io/badge/오나래-1E90FF?style=flat-round&logo=GitHub&logoColor=white"/>
        </a>
      </td>
      <td align="center" width="200px">
        <img width="100%" src="https://avatars.githubusercontent.com/u/80497049?s=96&v=4"  alt=""/>
        <a href="https://github.com/thumbthing">
          <img src="https://img.shields.io/badge/이민구-1E90FF?style=flat-round&logo=GitHub&logoColor=white"/>
        </a>
      </td>
      <td align="center" width="200px">
        <img width="100%" src="https://avatars.githubusercontent.com/u/68311202?s=96&v=4"  alt=""/>
        <a href="https://github.com/slowteady">
          <img src="https://img.shields.io/badge/이용민-1E90FF?style=flat-round&logo=GitHub&logoColor=white"/>
        </a>
      </td>
      <td align="center" width="200px">
        <img width="100%" src="https://avatars.githubusercontent.com/u/43225974?s=96&v=4"  alt=""/>
        <a href="https://github.com/lyn94">
          <img src="https://img.shields.io/badge/이유나-1E90FF?style=flat-round&logo=GitHub&logoColor=white"/>
        </a>
      </td>
      <td align="center" width="200px">
        <img width="100%" src="https://avatars.githubusercontent.com/u/110447844?s=96&v=4"  alt=""/>
        <a href="https://github.com/337yj">
          <img src="https://img.shields.io/badge/이윤정-1E90FF?style=flat-round&logo=GitHub&logoColor=white"/>
        </a>
      </td>
     </tr>
  </tbody>
</table>
<br/>

## 실행 방법

1. 로컬 환경에 프로젝트 복사본 생성

```bash
git clone https://github.com/pre-onboarding-12th-team6/pre-onboarding-12th-3-6.git
```

2. 프로젝트 폴더로 이동

```bash
cd pre-onboarding-12th-3-6
```

3. 프로젝트 종속성 설치

```bash
npm install
```

4. 프로젝트 실행

```bash
npm start
```

## 기술 스택

![React](https://img.shields.io/badge/ReactJS-61DAFB?style=for-the-badge&logo=React&logoColor=white)
![Typescript](https://img.shields.io/badge/Typescript-3178C6?style=for-the-badge&logo=Typescript&logoColor=white)
![Axios](https://img.shields.io/badge/Axios-5A29E4?style=for-the-badge&logo=Axios&logoColor=white)
![styledComponents](https://img.shields.io/badge/styledComponents-DB7093?style=for-the-badge&logo=styledComponents&logoColor=white)
![GoogleCloud](https://img.shields.io/badge/GoogleCloud-4285F4?style=for-the-badge&logo=GoogleCloud&logoColor=white)

## BEST PRACTICE

### 로컬 캐싱

캐싱 라이브러리를 사용하지 않는게 조건이었기 때문에 여러가지 방법을 생각했습니다.  
메모리 사용, 브라우저의 로컬, 세션, 캐시 스토리지 사용 등 여러 방법을 찾았고 프로젝트의 규모를 고려했을 때,  
브라우저의 스토리지를 사용하는게 적합하다 생각했습니다.

#### 1. 로컬 vs 세션 vs 캐시

브라우저의 어떤 스토리지를 사용하는 것이 적합할지 고민했고 각각의 특징을 찾았습니다.  

1. 로컬 스토리지

- 다른 스토리지와 비교했을 때, 많은 양의 리소스를 보관할 수 있다.
- 만료 날짜가 없기 때문에 페이지를 새로고침하거나 브라우저를 종료해도 데이터가 남아있다.  
- 자동으로 지워지지 않기 때문에 정보가 오래 유지된다.

2. 세션 스토리지

- 각 세션마다 데이터가 개별적으로 저장된다. 브라우저의 탭이 여러개라면 개별적으로 데이터를 저장한다.
- 세션을 종료하면 데이터가 자동으로 제거된다. 브라우저 탭이 닫히면 데이터가 제거된다.
- 저장되는 데이터의 만료 기간이 있다.

3. 캐시 스토리지

- 저장된 리소스를 웹페이지를 다시 방문할 때 빠르게 로드할 수 있다.
- 네트워크 연결이 없을 때도 사용이 가능하다.  
- 만료 날짜가 없기 때문에 페이지를 새로고침하거나 브라우저를 종료해도 데이터가 남아있다.  
- 데이터 공간이 부족할 경우, 브라우저가 데이터를 임의로 제거할 수 있다.

고민을 통해 최종적으로 **캐시 스토리지**를 선택했습니다.  
검색 관련 캐싱이 목적이었기 때문에 속도가 중요하다고 생각했습니다.  
용량이 작다는 단점이 있지만, 검색어 문자 보관에는 충분하다고 판단했고  
네트워크 연결이 없을 때도 캐싱 데이터를 가져와 출력해준다는 점도 큰 이점이라 생각했습니다.

#### 2. 구현

```ts
const REQUEST_SUCCESS = 200;
const EXPIRE_TIME = 1000 * 60 * 60;

class CacheManager {
  cacheName: string;

  constructor(cacheName: string) {
    this.cacheName = cacheName;
  }

  async set(key: string, value: string) {
    const cache = await caches.open(this.cacheName);
    const now = new Date();
    const item = {
      value,
      expire: now.getTime() + EXPIRE_TIME
    };
    const response = new Response(JSON.stringify(item));
    await cache.put(key, response);
  }

  async get(key: string) {
    const cache = await caches.open(this.cacheName);
    const response = await cache.match(key);

    if (response) {
      const item = await response.json();
      const now = new Date();
      if (now.getTime() > item.expire) {
        await cache.delete(key);
        return null;
      }
      return item;
    }
  }

  async getSearchData(path: string) {
    const cachedData = await this.get(path);

    if (cachedData) {
      return Promise.resolve({ data: cachedData.value, status: REQUEST_SUCCESS });
    } else {
      const response = await apiClient.get(path);
      await this.set(path, response.data);

      return response;
    }
  }
}

```

- 클래스 문법을 활용하여 캐시를 한곳에서 관리할 수 있도록 구현했습니다.
- 만료시간이 지나지 않은 캐시 데이터가 있는지 검증을 거친 후에 데이터가 없으면 새로운 요청과 캐시 저장, 데이터가 있으면 캐시 데이터를 그대로 제공하는 로직으로 구현했습니다.

> ❗️ 만료: 캐시 스토리지에 데이터를 저장할 때 만료 시간값을 같이 저장하여 만료 여부를 검증하고, 만료 되었으면 삭제 후 새로 요청하는 프로세스로 구현했습니다.

### 요청 최소화

문자를 입력할 때 마다 Http 요청을 보내는 현상을 최소화하기 위해 방법을 고민했습니다.  
여러가지 방법들을 고민한 결과 **디바운스**와 **쓰로틀링**을 사용하는 것이 대표적인 방법이었습니다.

#### 1-1. 디바운스 vs 쓰로틀링

1. 디바운스

- 연속적으로 이벤트가 발생할 때 이를 그룹화하여 특정 시간이 지난 뒤 마지막 이벤트만 실행합니다.

2. 쓰로틀링

- 이벤트를 일정 주기마다 실행하도록 합니다.

검색 데이터 요청에 어떤 방식이 더 적합할지 고민을 했고  
최종적으로 **디바운스**를 선택했습니다.  
검색 데이터 요청이라는 조건을 두고 생각 했을 때, 일정 주기마다 이벤트를 발생시켜 UX를 저하 시킬 수 있는 쓰로틀링에 비해  
문자 입력 후 시간이 지난 후에 검색 데이터 요청을 하는 디바운스가 더 안정적이라고 생각했습니다.

#### 1-2. 구현

```ts
function useDebounce(value: string, timeTerm: number) {
  const [debouncedValue, setDebouncedValue] = useState(value);

  useEffect(() => {
    const timeoutId = setTimeout(() => setDebouncedValue(value), timeTerm);

    return () => {
      clearTimeout(timeoutId);
    };
  }, [value, timeTerm]);

  return debouncedValue;
}

```

- 확장성과 재사용성을 고려하여 Custom Hook으로 구현했습니다.

#### 2-1. input validation

- 자음 또는 모음만 입력한 경우, 공백 문자만 입력한 경우 api요청을 보내지 않도록 입력값을 validation 함수로 필터링하였습니다.

#### 2-2. 구현

```ts
export const strCheck = {
  isEmpty: (str: string) => {
    return str === undefined || str.trim() === '';
  },
  isNotEmpty: (str: string) => {
    return !strCheck.isEmpty(str);
  }
};
export const checkInputValid = (keyword: string) => {
  const ConsonantRegex = /^[ㄱ-ㅎ]+$/;
  const VowelRegex = /^[ㅏ-ㅣ]+$/;
  const isInputConsonant = !ConsonantRegex.test(keyword);
  const isInputVowel = !VowelRegex.test(keyword);
  const isValid = isInputConsonant && isInputVowel && strCheck.isNotEmpty(keyword);

  return isValid;
};

```

#### 3-1. 캐싱데이터 활용

- 요청 이전 단계에서 입력한 검색어가 캐싱되어 있는지 확인하고, 있다면 캐싱된 데이터를 불러오는 방식으로 api요청을 최소화했습니다.

#### 3-2. 구현

```ts

```

### 키보드를 이용한 추천 검색어 이동

키보드를 이용하여 추천 검색어에 포커싱을 주는 것이 요구사항이었습니다.  
추천 검색어가 리스트 형태였기 때문에 index를 이용하여 구현하는 것이 적합할 것이라 생각했습니다.  
map 함수를 통해 index를 부여해 리스트를 렌더링하고, 키보드 이벤트를 통해 관리할 index를 매치 시켜서  
일치 여부에 따라 포커싱을 주는 것으로 설계 후 구현했습니다.

#### 1. 구현

```tsx
import { DEFAULT_INDEX } from '../components/search/SearchIndex';

interface Action {
  type: 'INDEX_INCREMENT' | 'INDEX_DECREMENT' | 'INDEX_RESET';
}

export const focusIndexReducer = (focusIndex: number, action: Action) => {
  switch (action.type) {
    case 'INDEX_INCREMENT':
      return focusIndex + 1;
    case 'INDEX_DECREMENT':
      return focusIndex - 1;
    case 'INDEX_RESET':
      return (focusIndex = DEFAULT_INDEX);
    default:
      return focusIndex;
  }
};

```

```tsx
const handleKeyDown = (e: KeyboardEvent<HTMLInputElement>) => {
    if (!e.nativeEvent.isComposing) {
      switch (e.key) {
        case 'ArrowDown':
          dispatch({ type: 'INDEX_INCREMENT' });
          break;
        case 'ArrowUp':
          dispatch({ type: 'INDEX_DECREMENT' });
          break;
        case 'Escape':
          dispatch({ type: 'INDEX_RESET' });
          e.currentTarget.blur();
          break;
        case 'Enter':
          if (focusIndex >= MIN_INDEX) changeInputValue();
          break;
      }
    }
  };
```

- focusIndex를 효율적으로 관리하기 위해 reducer를 만들어서 구현했습니다.

```ts
function AutoCompleteList({ sicks, isLoading, focusIndex }: ResultProps, ref: Ref<HTMLUListElement>) {
  const isNotEmpty = sicks && sicks.length > 0;

  return (
    <DropDownUl ref={ref}>
      {isLoading ? <Loading /> : isNotEmpty && <RecommandP>추천 검색어</RecommandP>}
      {!isNotEmpty ? (
        <NoData />
      ) : (
        sicks.map(({ sickNm, sickCd }, index) => {
          return <AutoCompleteItem key={sickCd} isFocus={focusIndex === index} sickNm={sickNm} />;
        })
      )}
    </DropDownUl>
  );
}
```

- 자식 컴포넌트에게 focusIndex를 props로 넘겨주어 map 함수를 통해 렌더링을 할 때, isFocus props로 일치 여부를 넘겨주도록 구현했습니다.
- 자식 컴포넌트는 isFocus가 true면 포커싱 디자인을 적용합니다.

### STATE 관리

#### 1. 구현
```tsx
function SearchIndex() {
  const [open, setOpen] = useState(false);
  const [value, setValue] = useState(DEFAULT_VALUE);
  const [focusIndex, dispatch] = useReducer(focusIndexReducer, DEFAULT_INDEX);
  const ulRef = useRef<HTMLUListElement>(null);
  const debouncedValue = useDebounce(value, TIME_TERM);
  const { sicks, isLoading } = useRequest(debouncedValue);

                                  .
                                  .
                                  .

  const onChangeValue = (e: ChangeEvent<HTMLInputElement>) => {
    const { value } = e.currentTarget;
    setValAndResetIdx(value);
  };

  const handleKeyDown = (e: KeyboardEvent<HTMLInputElement>) => {
    if (!e.nativeEvent.isComposing) {
      switch (e.key) {
        case 'ArrowDown':
          dispatch({ type: 'INDEX_INCREMENT' });
          break;
        case 'ArrowUp':
          dispatch({ type: 'INDEX_DECREMENT' });
          break;
        case 'Escape':
          dispatch({ type: 'INDEX_RESET' });
          e.currentTarget.blur();
          break;
        case 'Enter':
          if (focusIndex >= MIN_INDEX) changeInputValue();
          break;
      }
    }
  };

  const changeInputValue = () => {
    const focusedList = ulRef.current?.children[focusIndex + 1];
    const textValue = focusedList?.textContent;
    if (textValue && strCheck.isNotEmpty(textValue)) {
      setValAndResetIdx(textValue);
    }
  };

  const handleInputFocus = (e: FocusEvent<HTMLInputElement>) => {
    setOpen(e.type === 'focus');
    if (e.type === 'blur') {
      dispatch({ type: 'INDEX_RESET' });
    }
  };

  const setValAndResetIdx = (value: string) => {
    setValue(value);
    dispatch({ type: 'INDEX_RESET' });
  };

  return (
    <InputLayout>
      <Input
        placeholder={PLACEHOLDER_TEXT}
        onFocus={handleInputFocus}
        onBlur={handleInputFocus}
        onChange={onChangeValue}
        onKeyDown={handleKeyDown}
        value={value}
      />
      {open && (
        <>
          <EmptyButton onClick={() => setValAndResetIdx(DEFAULT_VALUE)} />
          <AutoCompleteList sicks={sicks} isLoading={isLoading} focusIndex={focusIndex} ref={ulRef} />
        </>
      )}
    </InputLayout>
  );
}
```

```ts
import { DEFAULT_INDEX } from '../components/search/SearchIndex';

interface Action {
  type: 'INDEX_INCREMENT' | 'INDEX_DECREMENT' | 'INDEX_RESET';
}

export const focusIndexReducer = (focusIndex: number, action: Action) => {
  switch (action.type) {
    case 'INDEX_INCREMENT':
      return focusIndex + 1;
    case 'INDEX_DECREMENT':
      return focusIndex - 1;
    case 'INDEX_RESET':
      return (focusIndex = DEFAULT_INDEX);
    default:
      return focusIndex;
  }
};

```

#### 2. props drilling
- 규모를 생각했을 때, 한 곳에서 state를 관리할 수 있다고 판단하여 최상위 부모 컴포넌트에서 state를 관리 하도록 구현했습니다.
- 요청을 통해 가져올 데이터와 로딩 여부 상태는 Custom Hook을 통해 가져올 수 있도록 구현했습니다.
- 소스의 가독성 향상과 효율을 위해 focusInput state를 reducer를 사용하여 구현했습니다.

## 프로젝트 구조

```bash
.
└── src/
    ├── api/
    │   ├── axiosInstance.ts
    │   └── searchApi.ts
    ├── components/
    │   ├── common/
    │   │   ├── Loading.tsx
    │   │   └── NoData.tsx
    │   └── search/
    │       ├── icon/
    │       │   └── SearchIcon.tsx
    │       ├── layout/
    │       │   ├── AutoCompleteItemLayout.tsx
    │       │   └── InputLayout.tsx
    │       ├── AutoCompleteItem.tsx
    │       ├── AutoCompleteList.tsx
    │       ├── EmptyButton.tsx
    │       └── SearchIndex.tsx
    ├── hooks/
    │   ├── useDebounce.ts
    │   └── useRequest.ts
    ├── pages/
    │   ├── error/
    │   │   └── Error.tsx
    │   └── search/
    │       └── Search.tsx
    ├── router/
    │   ├── Router.tsx
    │   └── routerPaths.ts
    ├── state/
    │   └── focusindexReducer.ts
    ├── types/
    │   ├── commonTypes.ts
    │   └── sickTypes.ts
    ├── utils/
    │   ├── CacheManager.ts
    │   ├── handleError.ts
    │   └── validate.ts
    ├── App.tsx
    └── index.tsx
```
