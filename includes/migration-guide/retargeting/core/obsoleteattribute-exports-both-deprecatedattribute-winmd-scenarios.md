---
ms.openlocfilehash: 7d7424b3ca0d295022999e95ed9862b5226b6220
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606781"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>ObsoleteAttribute가 WinMD 시나리오에서 ObsoleteAttribute와 DeprecatedAttribute를 내보냄

#### <a name="details"></a>설명

Windows 메타데이터 라이브러리(.winmd 파일)를 만들 때 <xref:System.ObsoleteAttribute?displayProperty=fullName> 특성은 <xref:System.ObsoleteAttribute?displayProperty=fullName> 및 [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute)로서 내보내집니다.

#### <a name="suggestion"></a>제안 해결 방법

<xref:System.ObsoleteAttribute?displayProperty=fullName> 특성이 사용된 기존 소스 코드를 다시 컴파일하면 C++/CX 또는 JavaScript의 해당 코드가 사용될 때 경고가 발생할 수 있습니다. <xref:System.ObsoleteAttribute?displayProperty=fullName> 및 [Windows.Foundation.DeprecatedAttribute](/uwp/api/windows.foundation.metadata.deprecatedattribute) 모두를 관리되는 어셈블리의 코드에 적용하는 것은 좋지 않습니다. 빌드 경고가 발생할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.5.1       |
| 형식    | 대상 변경 |
