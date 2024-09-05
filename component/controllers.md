# Controllers (컨트롤러)

컨트롤러는 들어오는 요청(Request)을 처리하고 응답(Response)을 클라이언트로 반환하는 역할을 합니다.

컨트롤러의 목적은 애플리케이션에 대한 특정 요청을 수신하는 것으로, 각 컨트롤러에는 다수의 경로가 존재하며 서로 다른 작업을 처리할 수 있습니다. 기본적인 컨트롤러는 생성하기 위해서 클래스와 **데코레이터**를 사용합니다. **데코레이터**는 클래스를 필수 메타데이터와 연결하고 Nest.js에서 라우팅 맵을 생성할 수 있도록 합니다.

{% hint style="info" %}
Nest CLI를 통해 간편하게 컨트롤러를 만들 수도 있습니다. <mark style="color:blue;">`nest g resource [name]`</mark>
{% endhint %}

### Routing

예시 코드를 보면 `@Controller` 데코레이터가 사용되고 있습니다. 이것은 기본적인 컨트롤러를 만들기 위해서 필수로 필요한 데코레이터입니다.

{% code title="cats.controller.ts" %}
```typescript
import { Controller, Get } from '@nestjs/common';

@Controller('cats')
export class CatsController {
  @Get()
  findAll(): string {
    return 'This action returns all cats';
  }
}
```
{% endcode %}
