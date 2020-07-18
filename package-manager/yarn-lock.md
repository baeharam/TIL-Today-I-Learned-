## yarn.lock의 역할

프로젝트의 패키지들의 버전을 관리하는 파일이 `package.json` 인데 이것만을 사용하게 되면 `yarn install` 을 통해서 패키지들을 설치하는 시점에 따라 버전이 달라지게 된다. 즉, 여러 사람이 협업하는 프로젝트의 경우, 패키지가 업데이트 됨에 따라서 에러가 발생하거나 의도치 않은 기능으로 이어질 수 있기 때문에 패키지를 업데이트 하는 것에 상당한 주의를 기울여야 한다.

이를 위해서 `yarn.lock` 파일이 존재하는데, 정확히 어떤 버전의 패키지를 설치해야 하는지 잠궈놓은(lock) 파일이라고 할 수 있다. 만약 npm을 사용한다면 `package-lock.json` 파일이 만들어진다. 이렇게 동일한 프로젝트의 다른 환경에서 균일한 패키지 버전을 제공하기 때문에 git과 같은 VCS에 의해 반드시 관리되어야 한다.

`yarn.lock` 파일을 자동으로 생성되며 패키지가 추가/업데이트/제거 될 때 수정된다. 따라서 이를 직접 수정해서는 안된다. 또한 최상위 파일만을 인식하기 때문에 내부 디렉토리에 다른 `yarn.lock` 파일이 있다 하더라도 무시한다.

<br>

## 참고

* [yarn.lock](https://classic.yarnpkg.com/en/docs/yarn-lock/)
* [Yarn 톺아보기](https://www.holaxprogramming.com/2017/12/21/node-yarn-tutorials/)