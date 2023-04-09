# WASM

WASM 또는 WebAssembly는 웹에서 코드를 실행하도록 설계된 저수준 바이너리 형식입니다. C, C++ 및 Rust와 같은 고급 프로그래밍 언어의 컴파일을 위한 이식 가능한 대상으로 고안되어 개발자가 이러한 언어로 코드를 작성한 다음 웹 브라우저에서 실행할 수 있습니다.

WASM은 빠르고 컴팩트하며 안전하도록 설계되었습니다. 시스템의 나머지 부분과 격리되는 샌드박스 환경에서 실행되므로 신뢰할 수 없는 코드를 안전하게 실행할 수 있습니다. 또한 하드웨어에 대한 낮은 수준의 액세스를 제공하여 특정 플랫폼 및 장치에 맞게 코드를 최적화할 수 있습니다.

WASM은 클라이언트 측 또는 서버 측에서 코드를 실행하는 데 사용할 수 있습니다. 클라이언트 측에서는 컴퓨팅 집약적인 작업을 브라우저로 오프로드하여 웹 애플리케이션의 성능을 높이는 데 사용할 수 있습니다. 여기에는 이미지 또는 비디오 처리, 게임 논리 또는 복잡한 수학적 계산과 같은 것들이 포함될 수 있습니다.

서버 측에서 WASM을 사용하여 완전히 클라우드에서 실행되는 고성능 웹 애플리케이션을 구축할 수 있습니다. 이는 채팅 애플리케이션, 금융 거래 플랫폼 또는 게임 백엔드와 같이 높은 수준의 확장성 또는 실시간 성능이 필요한 애플리케이션에 특히 유용할 수 있습니다.

WASM은 Chrome, Firefox, Safari 및 Edge를 포함한 모든 주요 웹 브라우저에서 지원됩니다. 또한 Google, Mozilla 및 Microsoft를 비롯한 여러 주요 기술 회사의 지원을 받습니다.



### React와 WASM

WebAssembly는 React와 함께 사용하여 웹 애플리케이션의 성능을 향상시킬 수 있습니다. WebAssembly를 사용하면 C++, Rust 및 Go와 같은 언어로 고성능 코드를 작성한 다음 React 애플리케이션에서 사용할 수 있습니다.

React를 사용한 WebAssembly의 일반적인 사용 사례 중 하나는 계산 집약적인 작업을 JavaScript 런타임에서 WebAssembly 런타임으로 오프로드하는 것입니다. 예를 들어 복잡한 계산을 많이 수행해야 하는 React 구성 요소가 있는 경우 해당 코드를 C++ 또는 Rust로 작성하고 WebAssembly로 컴파일할 수 있습니다. 그런 다음 WebAssembly 모듈을 React 애플리케이션에 로드하고 JavaScript 코드에서 함수를 호출할 수 있습니다.

React에서 WebAssembly를 더 쉽게 로드하려면 `@wasm-tool/wasm-loader` 패키지를 사용할 수 있습니다. 이 패키지는 일반 JavaScript 모듈인 것처럼 WebAssembly 모듈을 가져올 수 있는 Webpack 로더를 제공합니다.

다음은 React 구성 요소에서 WebAssembly 모듈을 로드하기 위해 `@wasm-tool/wasm-loader`를 사용하는 방법의 예입니다.

```js
import React, { useState } from 'react';
import wasmFactorial from './factorial.wasm';

function Factorial() {
  const [result, setResult] = useState(0);

  function handleClick() {
    const n = parseInt(prompt('Enter a number:'));
    wasmFactorial().then((module) => {
      const factorial = module.factorial;
      const result = factorial(n);
      setResult(result);
    });
  }

  return (
    <div>
      <button onClick={handleClick}>Calculate factorial</button>
      <p>Result: {result}</p>
    </div>
  );
}

export default Factorial;
```

​	



### React-three-fiber 와 WASM

React Three Fiber와 WebAssembly를 결합하면 React 애플리케이션에서 3D 그래픽의 성능을 향상시킬 수 있습니다. 방법은 다음과 같습니다.



1. React Three Fiber를 사용하여 3D 그래픽 코드를 작성합니다. 이 코드는 3D 장면을 만들고 여기에 개체를 추가하고 화면에 렌더링해야 합니다.
2. C++, Rust 또는 WebAssembly로 컴파일할 수 있는 다른 언어로 계산 집약적인 코드를 작성합니다. `emscripten`과 같은 라이브러리를 사용하여 코드를 컴파일할 수 있습니다.
3. `emcc` 명령 또는 다른 WebAssembly 컴파일러를 사용하여 코드에서 WebAssembly 모듈을 만듭니다.
4. 계산 집약적인 계산을 수행하는 함수를 노출하는 WebAssembly 모듈 주위에 JavaScript 래퍼를 만듭니다. 'emscripten'과 같은 라이브러리를 사용하여 WebAssembly 모듈에 대한 JavaScript 바인딩을 생성할 수 있습니다.
5. Webpack과 같은 모듈 번들러를 사용하여 JavaScript 래퍼 및 WebAssembly 모듈을 React 애플리케이션에 로드합니다. `@wasm-tool/wasm-loader` 패키지를 사용하여 WebAssembly 모듈을 더 쉽게 로드할 수 있습니다.
6. React Three Fiber 구성 요소에서 JavaScript 래퍼에 의해 노출된 기능을 사용하여 계산 집약적인 계산을 수행하고 그에 따라 3D 장면을 업데이트합니다.

다음은 코드의 예입니다.

```js
// main.cpp
#include <emscripten.h>

extern "C" {

EMSCRIPTEN_KEEPALIVE
float calculate_new_position(float current_position, float speed, float time) {
    return current_position + speed * time;
}

}

// compile to WebAssembly using emscripten:
// emcc main.cpp -s WASM=1 -s EXPORTED_FUNCTIONS="['_calculate_new_position']" -o main.wasm

// main.js
import wasm from './main.wasm';

export function calculateNewPosition(currentPosition, speed, time) {
  return wasm.then((module) => {
    return module.calculate_new_position(currentPosition, speed, time);
  });
}

// App.js
import React, { useState } from 'react';
import { Canvas } from '@react-three/fiber';
import { calculateNewPosition } from './main.js';

function Box() {
  const [position, setPosition] = useState(0);

  function animate() {
    calculateNewPosition(position, 1, 1).then((newPosition) => {
      setPosition(newPosition);
    });
  }

  return (
    <mesh onClick={animate}>
      <boxBufferGeometry />
      <meshBasicMaterial />
      <mesh position={[position, 0, 0]} />
    </mesh>
  );
}

function App() {
  return (
    <Canvas>
      <Box />
    </Canvas>
  );
}

export default App;
```

이 예에서는 React Three Fiber를 사용하여 클릭하면 움직이는 상자가 있는 간단한 3D 장면을 만듭니다. 상자의 위치를 추적하기 위해 `useState` 후크를 사용하고 있습니다.

또한 상자를 클릭할 때 상자의 새 위치를 계산하기 위해 WebAssembly를 사용하고 있습니다. 우리는 `main.js` 파일에 정의되어 있고 WebAssembly 모듈에서 `calculate_new_position` 함수를 호출하는 `calculateNewPosition` 함수를 사용하고 있습니다.

상자를 클릭하면 현재 위치, 속도 1, 시간 1초로 `calculateNewPosition` 함수를 호출합니다. 약속이 확인되면 `setPosition` 함수를 사용하여 상자의 위치를 업데이트합니다.

이것은 단순한 예일 뿐이지만, 자신의 애플리케이션에서 React Three Fiber 및 WebAssembly를 사용하여 3D 그래픽의 성능을 향상시키는 방법에 대한 아이디어를 얻을 수 있기를 바랍니다.
