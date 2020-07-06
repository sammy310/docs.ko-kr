---
ms.openlocfilehash: d0de1a262d57c67dd4dfb258d5ac013af5d8783d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617233"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>WPF TextBox.Text가 데이터 바인딩과 비동기화될 수 있음

#### <a name="details"></a>설명

경우에 따라 <xref:System.Windows.Controls.TextBox.Text> 속성은 데이터 바인딩 쓰기 작업 중 속성이 수정되면 데이터 바인딩된 속성 값의 이전 값을 반영합니다.

#### <a name="suggestion"></a>제안 해결 방법

이는 부정적인 영향을 주어서는 안 됩니다. 그러나 <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> 속성을 `false`로 설정하여 이전 동작을 복원할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.5         |
|형식|대상 변경

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType>
