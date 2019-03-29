---
title: s_isDebuggerCheckDisabledForTestPurposes 필드
ms.date: 03/30/2017
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: ab71ab6aa2b0ed454b86388ba369204a2131cca5
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634429"
---
# <a name="sisdebuggercheckdisabledfortestpurposes-field"></a>s_isDebuggerCheckDisabledForTestPurposes 필드

이 개인 필드에는 `System.Windows.Diagnostics.VisualDiagnostics` 클래스는 현재 디버거의 내부 검사를 수행할지 여부를 확인 하려면 Visual Studio에서 사용 됩니다.

## <a name="syntax"></a>구문

```csharp
private static bool s_isDebuggerCheckDisabledForTestPurposes
```

> [!WARNING]
> Api는 `System.Windows.Diagnostics.VisualDiagnostics` 클래스 디버거에서 응용 프로그램이 실행 되는 경우에 사용할 수 있습니다. 설정할 `s_isDebuggerCheckDisabledForTestPurposes` 에 `true` 디버거 외부에서 Api에 액세스할 수 있습니다.
>
> Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Windows.Diagnostics>

**어셈블리:** PresentationCore (presentationcore.dll)

**.NET framework 버전:** 4.6부터 사용할 수 있습니다.