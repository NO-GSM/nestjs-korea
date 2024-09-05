# Hello World!

프로젝트 설치에 대해 알아봤으니 기본적인 프로젝트 구조에 대해서 알아보겠습니다.

## 구성하기

프로젝트 세팅을 위해서 [publish-your-docs.md](../getting-started/publish-your-docs.md "mention")에서 배웠던 대로 Nest CLI를 이용해 보겠습니다.

```bash
$ npm i -g @nestjs/cli
$ nest new project-name
```

구성된 프로젝트의 폴더를 살펴보면 다음과 같이 구성되어 있습니다.

* src
  * `app.controller.spec.ts`: 컨트롤러에서 쓰이는 유닛 테스트입니다.
  * `app.controller.ts`: 하나의 경로로 구성된 기본적인 컨트롤러입니다.
  * `app.module.ts`: 애플리케이션의 루트 모듈입니다.
  * `app.service.ts`: 하나의 함수로 구성된 기본적인 서비스입니다.
  * `main.ts`: `NestFactory`를 통해 생성된 애플리케이션 인스턴스가 시작되는 시작점 파일입니다.

### main.ts에서 부터

다음은 main.ts에 포함된 bootstrap 함수입니다.

{% code title="main.ts" %}
```typescript
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(3000);
}
bootstrap();
```
{% endcode %}

Nest.js 애플리케이션 인스턴스를 생성하기 위해서 `NestFactory`를 사용할 것이며, `create()`으로 애플리케이션 오브젝트를 반환받습니다.
