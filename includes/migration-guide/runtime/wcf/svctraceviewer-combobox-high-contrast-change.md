---
ms.openlocfilehash: 4bc8db52efdfe483acb4f6b6e33c4fa7716e0b79
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770961"
---
### <a name="svctraceviewer-combobox-high-contrast-change"></a>svcTraceViewer ComboBox 고대비 변경

#### <a name="details"></a>설명

[Microsoft Service Trace Viewer 도구](~/docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)에서 ComboBox 컨트롤이 특정 고대비 테마에서 올바른 색으로 표시되지 않았습니다. 이 문제는 .NET Framework 4.7.2에서 해결되었습니다. 그러나 .NET Framework SDK의 이전 버전과의 호환성 요구 사항으로 인해, 이 수정 사항은 기본적으로 고객에게 보이지 않습니다. .NET 4.8은 다음 [AppContext 구성 스위치](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 svcTraceViewer.exe.config 파일에 추가하여 이 변경 내용을 표시합니다.

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

#### <a name="suggestion"></a>제안 해결 방법

고대비 동작을 변경하지 않으려는 경우 svcTraceViewer.exe.config 파일에서 다음 섹션을 제거하여 비활성화할 수 있습니다.

```xml
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
```

| 이름    | 값   |
|:--------|:--------|
| Scope   | Microsoft Edge    |
| 버전 | 4.8     |
| 형식    | 런타임 |

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
