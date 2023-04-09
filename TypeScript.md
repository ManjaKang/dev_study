# TypeScript

TypeScript는 Microsoft에서 개발하고 유지 관리하는 JavaScript의 상위 집합인 프로그래밍 언어입니다. 2012년에 처음 출시되었으며 대규모 프로젝트를 위해 보다 유지 관리 및 확장 가능한 코드를 작성하는 방법으로 최근 몇 년 동안 인기를 얻었습니다.

TypeScript는 JavaScript에 선택적 정적 유형 지정을 추가하여 개발자가 런타임 전에 오류를 포착할 수 있도록 합니다. 편집기 및 IDE를 위한 더 나은 도구 지원을 제공합니다. 변수, 매개변수 및 반환 값에 대한 유형을 지정함으로써 TypeScript는 특히 프로젝트의 규모와 복잡성이 증가함에 따라 코드가 정확하고 유지 관리 가능하도록 보장할 수 있습니다.



### 타입 스크립트 문법

TypeScript에는 유형 검사 및 더 나은 개발 환경을 위한 추가 기능 및 구성으로 JavaScript의 구문을 확장하는 자체 구문이 있습니다. 다음은 몇 가지 주요 TypeScript 구문 기능입니다.

1. 유형 주석 - TypeScript를 사용하면 개발자가 콜론(:)을 사용하여 유형 정보로 변수, 함수 매개변수 및 함수 반환 유형에 주석을 달 수 있습니다. 예:

   ```tsx
   let myString: string = 'Hello world';
   function myFunction(num1: number, num2: number): number {
     return num1 + num2;
   }
   ```

2. 인터페이스 - 인터페이스를 사용하면 개체 또는 클래스의 모양을 정의할 수 있습니다. 개체가 가져야 하는 속성 및 메서드의 유형을 설명하는 데 사용할 수 있습니다. 예:

   ```tsx
   interface Person {
     name: string;
     age: number;
     sayHello(): void;
   }
   ```

3. 클래스 - TypeScript에는 다른 객체 지향 프로그래밍 언어와 유사한 클래스 구문이 있습니다. 클래스는 속성 및 메서드가 있는 개체를 만들기 위한 청사진을 정의하는 데 사용할 수 있습니다. 예:

   ```tsx
   class Animal {
     constructor(public name: string) {}
     sayHello() {
       console.log(`Hello, my name is ${this.name}`);
     }
   }
   ```

4. 제네릭 - 제네릭을 사용하면 다른 유형의 데이터와 함께 재사용할 수 있는 유형을 정의할 수 있습니다. 재사용 가능한 함수와 클래스를 만드는 데 사용할 수 있습니다. 예:

   ```tsx
   function identity<T>(arg: T): T {
     return arg;
   }
   
   let myNumber: number = identity<number>(42);
   let myString: string = identity<string>('Hello');
   ```

5. 열거형 - 열거형을 사용하면 명명된 상수 집합을 정의할 수 있습니다. 숫자 값에 의미 있는 이름을 지정하여 더 읽기 쉬운 코드를 만드는 데 사용할 수 있습니다. 예:

   ```tsx
   enum Color {
     Red,
     Green,
     Blue,
   }
   
   let myColor: Color = Color.Green;
   ```

6. 유니온 유형 - 유니온 유형을 사용하면 변수가 하나 이상의 가능한 유형을 가질 수 있음을 지정할 수 있습니다. 파이프(|) 기호를 사용하여 유형을 구분할 수 있습니다. 예:

   ```tsx
   let myVar: string | number;
   myVar = 'Hello';
   myVar = 42;
   ```

7. 유형 별칭 - 유형 별칭을 사용하면 코드 전체에서 사용할 수 있는 사용자 지정 유형을 정의할 수 있습니다. 유형 별칭을 사용하여 복합 유형에 더 설명적인 이름을 지정하거나 코드를 더 읽기 쉽게 만들 수 있습니다. 예:

   ```tsx
   type Point = {
     x: number;
     y: number;
   };
   
   function distance(p1: Point, p2: Point): number {
     return Math.sqrt((p1.x - p2.x) ** 2 + (p1.y - p2.y) ** 2);
   }
   ```

8. 선택적 속성 - TypeScript를 사용하면 속성 뒤에 물음표(?)를 추가하여 객체 속성을 선택적으로 정의할 수 있습니다. 이름. 모든 속성이 정의되어 있지 않을 수 있는 개체에 대한 인터페이스를 정의할 때 유용할 수 있습니다. 예:

   ```tsx
   interface Person {
     name: string;
     age?: number;
   }
   
   let john: Person = { name: 'John' }; // age is optional
   let mary: Person = { name: 'Mary', age: 30 };
   ```

9. 유형 가드 - 유형 가드를 사용하면 런타임에 변수의 유형을 확인하고 상황에 따라 다른 작업을 수행할 수 있습니다. 유형. 타입 가드는 가능한 변수 타입의 범위를 좁히기 위해 공용체 타입과 함께 사용할 수 있습니다. 예:

   ```tsx
   function printValue(value: string | number) {
     if (typeof value === 'string') {
       console.log(`Value is a string: ${value}`);
     } else {
       console.log(`Value is a number: ${value}`);
     }
   }
   ```

   

