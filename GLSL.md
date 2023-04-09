# GLSL

GLSL은 OpenGL 그래픽 API용 셰이더를 작성하는 데 사용되는 고급 셰이딩 언어입니다. GLSL로 작성된 셰이더는 GPU에서 그래픽을 렌더링하는 방법을 지정하는 데 사용됩니다. GLSL은 빠르고 효율적이며 유연하도록 설계되었으며 다양한 시각 효과를 만드는 데 사용할 수 있습니다.

다음은 GLSL로 작업할 때 염두에 두어야 할 몇 가지 기본 개념과 구문 규칙입니다.

1. 데이터 유형: GLSL에는 float, int, bool, vec2, vec3, vec4, mat3 및 mat4를 비롯한 몇 가지 기본 제공 데이터 유형이 있습니다. 벡터(예: vec2, vec3, vec4)는 위치 및 색상과 같은 기하학적 데이터를 나타내는 데 사용되는 반면 행렬(예: mat3, mat4)은 변환을 나타내는 데 사용됩니다.
2. 변수 : GLSL에서는 다른 프로그래밍 언어와 마찬가지로 변수를 선언하고 사용할 수 있습니다. 예를 들어 "myFloat"라는 float 변수를 선언하려면 "float myFloat;"라고 작성합니다. "float myFloat = 0.0;"과 같이 변수를 선언할 때 초기화할 수도 있습니다. 변수는 값을 저장하고, 계산을 수행하고, 셰이더 간에 데이터를 전달하는 데 사용할 수 있습니다.
3. 함수: GLSL에는 수학 함수, 텍스처 샘플링과 같은 다양한 내장 함수가 있습니다. 기능 및 조명 기능. "functionName()" 구문을 사용하여 고유한 함수를 정의할 수도 있습니다. 함수는 계산을 수행하고, 효과를 적용하고, 셰이더 코드를 단순화하는 데 사용할 수 있습니다.
4. Main 함수: GLSL에서 "Main" 함수는 셰이더의 진입점입니다. 여기에서 정점을 변환하는 방법, 픽셀을 음영 처리하는 방법 등과 같은 셰이더 동작을 지정합니다. 기본 함수는 void를 반환해야 하며 일반적으로 다음과 같이 구성됩니다.
5. 입력 및 출력 변수: 셰이더는 입력 및 출력 변수를 사용하여 서로 통신할 수 있습니다. 입력 변수는 "in" 키워드를 사용하여 선언되며 일반적으로 한 셰이더 단계에서 다른 단계로 데이터를 전달하는 데 사용됩니다(예: 버텍스 셰이더에서 조각 셰이더로). 출력 변수는 "out" 키워드를 사용하여 선언되며 일반적으로 현재 셰이더 단계에서 파이프라인의 다음 단계로 데이터를 전달하는 데 사용됩니다.
6. 제어 구조: GLSL은 공통 구조를 지원합니다. if/else 문, for 루프 및 while 루프와 같은 제어 구조. 조건부 및 반복 작업을 수행하는 데 사용할 수 있습니다.



### Vertex Shader와 Fragment Shader

버텍스 셰이더와 프래그먼트 셰이더는 컴퓨터 그래픽에서 3D 그래픽과 애니메이션을 만드는 데 사용되는 두 가지 유형의 셰이더 프로그램입니다.

버텍스 셰이더는 3D의 각 정점에 대해 GPU에서 실행되는 프로그램입니다. 모델. 버텍스 셰이더의 목적은 버텍스 위치를 모델의 로컬 공간에서 카메라의 클립 공간으로 변환하는 것입니다. 정점 속성(예: 위치, 색상, 법선)을 입력으로 사용하고 변환된 정점 위치를 출력합니다. 이 프로세스를 정점 변환이라고 합니다. 정점 위치를 변환하는 것 외에도 정점 셰이더는 조명 계산, 텍스처 매핑 및 기타 효과와 같은 다른 작업도 수행할 수 있습니다.

프래그먼트 셰이더(픽셀 셰이더라고도 함)는 다음을 수행하는 프로그램입니다. 래스터화 프로세스에 의해 생성된 각 픽셀에 대해 GPU에서 실행됩니다. Fragment Shader의 목적은 픽셀의 색상 및 기타 속성을 결정하는 것입니다. 정점 셰이더의 출력(예: 보간된 정점 위치, 법선 및 텍스처 좌표)을 입력으로 받아 픽셀의 최종 색상을 출력합니다. Fragment Shader는 혼합, 알파 테스트 및 기타 후처리 효과와 같은 다른 작업도 수행할 수 있습니다.



### 예제

삼각형을 그리고 빨간색으로 칠하는 예제

Vertex Shader Code:

```glsl
attribute vec3 position;

void main() {
  gl_Position = vec4(position, 1.0);
}
```

Fragment Shader Code:

```glsl
void main() {
  gl_FragColor = vec4(1.0, 0.0, 0.0, 1.0);
}
```



### gl_FragColor

`gl_FragColor`는 프레그먼트 셰이더에서 조각의 최종 색상을 지정하는 데 사용되는 GLSL(OpenGL Shading Language)의 내장 출력 변수입니다. 프래그먼트 셰이더는 렌더링된 프리미티브의 모든 픽셀에 대해 실행되는 프로그램이며 해당 픽셀의 색상 계산을 담당합니다.

프래그먼트 셰이더에서 `gl_FragColor`는 현재 조각의 색상을 지정하는 데 사용됩니다. `gl_FragColor`에 할당된 값은 일반적으로 색상의 빨강, 녹색, 파랑 및 알파 구성 요소를 나타내는 vec4 벡터입니다. 예를 들어 다음 코드는 `gl_FragColor`를 빨간색으로 설정합니다.

```glsl
void main() {
  // compute the normalized screen coordinates of the fragment
  vec2 normalizedCoords = gl_FragCoord.xy / vec2(800.0, 600.0);

  // set the color of the fragment based on its position in the window
  gl_FragColor = vec4(normalizedCoords.x, normalizedCoords.y, 0.0, 1.0);
}
```



### gl_FragCoord

`gl_FragCoord`는 프레그먼트 셰이더에서 처리 중인 조각의 창 좌표(x, y, z, w)를 나타내는 GLSL(OpenGL Shading Language)의 내장 입력 변수입니다. 

`gl_FragCoord`의 x 및 y 구성 요소는 창에서 현재 프래그먼트의 픽셀 좌표를 나타내고 z 구성 요소는 프래그먼트의 깊이 값(즉, 카메라). 일반적인 렌더링 작업의 경우 w 구성 요소는 항상 1.0입니다.

```glsl
void main() {
  // compute the normalized screen coordinates of the fragment
  vec2 normalizedCoords = gl_FragCoord.xy / vec2(800.0, 600.0);

  // set the color of the fragment based on its position in the window
  gl_FragColor = vec4(normalizedCoords.x, normalizedCoords.y, 0.0, 1.0);
}
```



### uniform 키워드

