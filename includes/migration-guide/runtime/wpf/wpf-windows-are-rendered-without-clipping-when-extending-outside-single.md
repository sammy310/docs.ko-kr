---
ms.openlocfilehash: d276e2bbf24c8b2389a0a8078c62c327c3729d50
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621357"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a>WPF 창이 단일 모니터 외부로 확장될 때 잘림 없이 렌더링됩니다.

#### <a name="details"></a>세부 정보

Windows 8 이상에서 실행되는 .NET Framework 4.6에서, 다중 모니터 시나리오에서 전체 창이 단일 디스플레이를 벗어나 확장되는 경우 잘림 없이 렌더링됩니다. 이는 단일 디스플레이를 벗어나 확장된 WPF 창을 잘라 냈던 이전 버전의 .NET Framework와 다릅니다.

#### <a name="suggestion"></a>제안 해결 방법

이 동작(잘라 내는지 여부)은 애플리케이션 구성 파일의 <code>&lt;appSettings&gt;</code>에 있는 <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> 요소를 사용하거나 앱 시작 시 <code>EnableMultiMonitorDisplayClipping</code> 속성을 설정하여 명시적으로 설정할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.6|
|형식|런타임|
