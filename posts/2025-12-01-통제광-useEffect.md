---
title: "통제광 useEffect"
date: "2025-12-01T20:01:21.966Z"
image: "https://ljneqqwnqsihknviuleb.supabase.co/storage/v1/object/public/post-images/post_images/1764586881234_balloon.jpg"
---

Control Freak useEffect

use 사용할거임 effect 효과
언제? 내가 원할때. 상태 변경, 렌더링 아무것도 접근 ㄴㄴ

```
useEffect(() => {
    // 기본형
}, [])
```

setInterval 메서드 쓰고싶다? 그것도 통제해
(side effect 미연에 방지)
```
useEffect(() => {
    const intervalId = setInterval(callStockData, 600000);

    return () => {
      clearInterval(intervalId);
    };
  }, []);
```

> useEffect는 리렌더링과 상관없이 "마운트 될 때 한 번만 실행하라" 혹은 **"특정 값이 변할 때만 다시 실행하라"**고 통제할 수 있기 때문에 필수적입니다.

내 Gemini Pro의 답변인데 얘한테 통제라는 단어 안썼는데 얘도 인정함. 통제광 useEffect...

참고로 setInterval은 간격(interval)을 고유하게 식별할 수 있는 interval ID를 반환하므로([출처: mdn 문서](https://developer.mozilla.org/ko/docs/Web/API/Window/setInterval)) useEffect의 클린업 기능과 함께 사용하는게 권장됨
