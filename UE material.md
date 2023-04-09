# 머티리얼

언리얼 엔진의 머티리얼은 게임 엔진에서 표면을 렌더링하는 방법을 정의하는 지침 세트입니다. 색상, 반사도, 거칠기 및 기타 속성을 포함하여 개체의 시각적 모양을 제어합니다. 재료는 서로 다른 노드의 연결을 통해 복잡한 재료를 생성할 수 있는 노드 기반 시스템인 재료 편집기를 사용하여 생성됩니다.

언리얼 엔진의 머티리얼 에디터는 머티리얼을 만드는 데 사용할 수 있는 다양한 노드와 기능을 제공합니다. 이러한 노드에는 색상 및 텍스처 샘플러와 같은 기본 기능과 노이즈 생성기 및 수학 연산과 같은 보다 복잡한 기능이 포함됩니다. 이러한 노드를 다양한 방식으로 결합함으로써 아티스트는 매우 상세하고 복잡한 재료를 만들 수 있습니다.

언리얼 엔진에서 머티리얼의 핵심 기능 중 하나는 동적이고 게임 환경의 변화에 반응하는 능력입니다. 예를 들어 카메라 각도나 장면의 조명에 따라 반사율이나 텍스처를 변경하도록 재질을 설정할 수 있습니다. 이를 통해 플레이어는 매우 몰입감 있고 상호 작용하는 경험을 할 수 있습니다.

### UV 맵핑

UV("UV 매핑"의 줄임말)는 3D 컴퓨터 그래픽에서 2D 이미지를 3D 개체에 매핑하는 데 사용되는 기술입니다. 텍스처를 3D 개체의 표면에 왜곡을 최소화하면서 정확하게 적용할 수 있으므로 텍스처링 프로세스의 필수 단계입니다.

UV 맵을 만들려면 먼저 3D 객체를 2D 표현으로 풀어야 합니다. 이것은 일반적으로 오렌지 껍질을 벗기는 것과 같이 개체를 2D 평면으로 평평하게 하여 수행됩니다. 결과 2D 표현을 UV 맵이라고 하며 오브젝트에 텍스처를 적용하는 데 필요한 모든 정보가 포함되어 있습니다.

UV 맵은 Maya, Blender 또는 3ds Max와 같은 특수 소프트웨어 도구를 사용하여 생성됩니다. 이러한 프로그램에서 아티스트는 3D 개체와 해당 UV 맵을 동시에 조작할 수 있으므로 텍스처가 올바르게 적용되었는지 쉽게 확인할 수 있습니다.

### 노드

언리얼 엔진 머티리얼 에디터는 게임, 건축 시각화, 가상 현실 경험과 같은 실시간 애플리케이션에서 3D 모델용 머티리얼을 만드는 데 사용되는 노드 기반 비주얼 프로그래밍 환경입니다. 다음은 Material Editor에서 사용되는 대표 노드 목록과 간략한 설명입니다.

1. 텍스처 샘플: 이 노드는 색상, 거칠기 또는 기타 재료 속성에 사용할 수 있는 텍스처 맵을 샘플링하는 데 사용됩니다.
2. Material Attributes: 이 노드는 거칠기, 금속성 및 방출과 같은 재질의 다양한 속성을 제어하는 데 사용됩니다.
3. 스칼라 매개변수: 이 노드를 사용하면 반사 하이라이트의 강도와 같은 재료 속성을 조정하는 데 사용할 수 있는 스칼라 값 매개변수를 만들 수 있습니다.
4. 벡터 매개변수: 이 노드를 사용하면 난반사 색상과 같은 재료 속성을 조정하는 데 사용할 수 있는 벡터 값 매개변수를 만들 수 있습니다.
5. 상수: 이 노드를 사용하면 반사광 색상과 같은 재료 속성으로 사용할 수 있는 상수 값을 정의할 수 있습니다.
6. Lerp: 이 노드는 두 입력 값 사이에 선형 보간을 수행하여 두 텍스처 사이를 혼합하거나 시간 경과에 따라 재료 속성을 조정하는 데 사용할 수 있습니다.
7. 곱하기: 이 노드는 표면 거칠기와 같은 재료 속성의 강도를 제어하는 데 사용할 수 있는 두 개의 입력 값을 곱합니다.
8. 추가: 이 노드는 텍스처의 밝기와 같은 재료 속성의 전체 강도를 제어하는 데 사용할 수 있는 두 개의 입력 값을 함께 추가합니다.
9. 텍스처 좌표: 이 노드는 3D 모델의 표면을 기반으로 텍스처 좌표를 생성하며, 모델에 대한 텍스처 매핑을 제어하는 데 사용할 수 있습니다.
10. 노멀 맵: 이 노드는 범프, 스크래치, 주름과 같은 표면 세부 사항을 시뮬레이션하는 데 사용할 수 있는 텍스처에서 노멀 맵을 생성합니다.
11. 반사 벡터: 이 노드는 주어진 표면 점에 대한 반사 벡터를 계산하여 사실적인 반사 및 반사 하이라이트를 생성하는 데 사용할 수 있습니다.
12. 프레넬: 이 노드는 주어진 표면 점에 대한 프레넬 효과를 계산하며, 이는 빛이 비스듬한 각도에서 표면에서 반사되는 방식을 시뮬레이션하는 데 사용할 수 있습니다.
13. 패너: 이 노드는 텍스처를 지정된 방향과 속도로 패닝하여 애니메이션을 적용합니다. 이 노드는 흐르는 물이나 깜박이는 불꽃과 같은 효과를 만드는 데 사용할 수 있습니다.
14. 시간: 이 노드는 시간이 지남에 따라 재료 속성을 애니메이션하는 데 사용할 수 있는 지속적으로 증가하는 시간 값을 제공합니다.
15. 텍스처 좌표(월드 공간): 이 노드는 모델의 표면이 아닌 월드 공간을 기반으로 텍스처 좌표를 생성하여 배경을 스크롤하거나 구름을 움직이는 것과 같은 효과를 만드는 데 사용할 수 있습니다.
16. 픽셀 깊이: 이 노드는 카메라에서 렌더링 중인 현재 픽셀까지의 거리를 계산하며 깊이 기반 안개 또는 선택적 블러링과 같은 효과를 만드는 데 사용할 수 있습니다.
17. 장면 색상: 이 노드는 지정된 위치에서 장면의 색상을 샘플링하여 빛샘 또는 렌즈 플레어와 같은 효과를 만드는 데 사용할 수 있습니다.
18. Static Switch Parameter: 이 노드를 사용하면 두 가지 재료 속성 사이를 전환하는 데 사용할 수 있는 부울 매개변수를 만들 수 있습니다. 이는 여러 변형이 있는 복잡한 재료를 만드는 데 유용할 수 있습니다.
19. 머티리얼 함수: 서로 다른 머티리얼 간에 만들고 공유할 수 있는 재사용 가능한 노드 그룹으로, 복잡한 머티리얼을 보다 효율적으로 만들 수 있습니다.
20. 사용자 정의 노드: 재료 내에서 사용자 정의 계산 또는 작업을 수행하는 데 사용할 수 있는 사용자 생성 노드로, 훨씬 더 큰 유연성과 사용자 정의가 가능합니다.
21. 동적 머티리얼 인스턴스: 이 노드를 사용하면 런타임 시 머티리얼 인스턴스를 생성하고 매개변수를 수정할 수 있습니다. 이는 실시간 애플리케이션에서 상호작용 및 반응형 머티리얼을 만드는 데 유용할 수 있습니다.
22. 텍스처 개체 매개변수: 이 노드를 사용하면 질감 개체를 재질의 매개변수로 사용할 수 있습니다. 이는 런타임에 교체할 수 있는 동적 및 유연한 재질을 만드는 데 유용할 수 있습니다.
23. 장면 텍스처: 이 노드를 사용하면 다양한 효과를 만드는 데 사용할 수 있는 깊이, 일반 및 기본 색상을 포함하여 장면에서 다양한 유형의 텍스처를 샘플링할 수 있습니다.
24. 텍스처 샘플 매개변수: 이 노드를 사용하면 재료의 텍스처를 교체하는 데 사용할 수 있는 텍스처 매개변수를 만들 수 있습니다. 이는 동적 및 사용자 정의 가능한 재료를 만드는 데 유용할 수 있습니다.
25. 텍스처 개체: 이 노드를 사용하면 재질에서 직접 텍스처 개체를 참조할 수 있으므로 보다 효율적이고 최적화된 재질을 만드는 데 유용할 수 있습니다.
26. 텍스처 좌표(카메라 벡터): 이 노드는 카메라의 시점 방향을 기반으로 텍스처 좌표를 생성하며, 카메라 각도나 거리에 민감한 재질을 만드는 데 유용할 수 있습니다.
27. 벡터 매개변수(색상): 이 노드를 사용하면 반사 하이라이트의 색상이나 기본 색상 텍스처의 색조와 같은 재료 속성의 색상을 조정하는 데 사용할 수 있는 벡터 매개변수를 만들 수 있습니다.
28. 벡터 매개변수(선형 색상): 이 노드를 사용하면 재료 속성의 선형 색상을 조정하는 데 사용할 수 있는 벡터 매개변수를 생성할 수 있으며, 이는 보다 정확하고 정확한 색상 조정을 생성하는 데 유용할 수 있습니다.

전반적으로 이러한 노드와 다른 많은 노드는 언리얼 엔진에서 머티리얼을 생성하기 위한 다양한 도구와 옵션을 제공하여 아티스트와 개발자가 프로젝트의 특정 요구 사항을 충족하도록 맞춤화 및 최적화할 수 있는 풍부하고 몰입도 높은 3D 환경을 생성할 수 있도록 합니다.
