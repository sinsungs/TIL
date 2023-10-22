# recoil 사용법

## recoil 설치 
```
npm install recoil
```

## index.js
```
RecoilRoot로 감싸주기
ReactDOM.render(
  <RecoilRoot>
    <App />
  </RecoilRoot>,
  document.getElementById('root')
);
```

## recoil.js 
```
import { atom, RecoilRoot, useRecoilState } from 'recoil';

export const habitsState = atom({
  key: 'habitsState',
  default: [],
});
```

## RecoilState 사용해서 데이터 보관
```
import { useRecoilState } from 'recoil';

const [recoil, setRecoil] = useRecoilState(habitsState);
```

## RecoilValue 사용해서 데이터 사용 
```
import { useRecoilValue } from 'recoil';

const habits = useRecoilValue(habitsState);
```