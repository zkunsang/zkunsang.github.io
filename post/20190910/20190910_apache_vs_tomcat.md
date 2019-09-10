아파치와 톰캣의 차이

아파치 - 정적 서버 
    -web server (+ 여러가지 모듈)

톰캣 - 동적 서버 
    - 아파치가 하는 web server역활
    - java, jsp, db, 같은 백엔드 처리


네오게임즈에서는 왜 apache를 톰캣을 여러개 올리고 사용했는가?
여러 모듈, proxy를 해주기 위해서 jap를 사용해서 처리하기 위해

톰캣역시 아파치의 기능들을 처리 할 수 있다.
단순히 static한 정적 파일들을 사용한다면 톰캣 기능만으로도 충분하다

앞단에 apache를 사용하는 이유는 다른 모듈들을 처리하기위해 사용해야 한다. 그게 아니라면 메모리 낭비
https://animal-park.tistory.com/96
https://limmmee.tistory.com/4 <- 요것이 좀 더 깔끔한 설명. 
