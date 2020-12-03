---
title: '호환성이 손상되는 변경: RCW를 `InterfaceIsIInspectable`로 캐스팅하면 예외가 throw됨'
description: RCW를 `InterfaceIsIInspectable` 인터페이스로 캐스팅하면 PlatformNotSupportedException이 throw되는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 09/13/2020
ms.openlocfilehash: 7c0f37057aebcc41d0c00d949b921ec3a4bdf012
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759816"
---
# <a name="casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception"></a>RCW를 `InterfaceIsIInspectable` 인터페이스로 캐스팅하면 PlatformNotSupportedException이 throw됨

<xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>로 표시된 인터페이스로 RCW(런타임 호출 가능 래퍼)를 캐스팅하면 이제 <xref:System.PlatformNotSupportedException>이 throw됩니다. 이 변경 내용은 [.NET에서 WinRT 지원 제거](built-in-support-for-winrt-removed.md)에 따른 후속 조치입니다.

## <a name="version-introduced"></a>도입된 버전

5.0 RC2

## <a name="change-description"></a>변경 내용 설명

.NET 5.0 미리 보기 6 이전의 .NET 버전에서는 <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>로 표시된 인터페이스로 RCW를 캐스팅하는 기능이 예상대로 작동합니다. .NET 5.0 미리 보기 6~8 및 RC1에서는 RCW를 <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> 인터페이스로 캐스팅할 수 있습니다. 그러나 런타임에서의 기본 지원이 [.NET 5.0 미리 보기 6에서 제거](built-in-support-for-winrt-removed.md)되었으므로 인터페이스에서 메서드를 실행하면 액세스를 위반할 수 있습니다.

.NET 5.0 RC2 이상 버전에서 <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>로 표시된 인터페이스로 RCW를 캐스팅하면 캐스트 시간에 <xref:System.PlatformNotSupportedException>이 throw됩니다.

## <a name="reason-for-change"></a>변경 이유

<xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> 지원은 [이전 .NET 5.0 미리 보기에서 제거](built-in-support-for-winrt-removed.md)되었습니다. 그러나 <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> 인터페이스로의 캐스팅은 실수로 간과되었습니다. 런타임에서 기본 지원이 더 이상 존재하지 않으므로 <xref:System.PlatformNotSupportedException>을 throw하여 정상적인 실패 경로를 지원합니다. 또한 예외를 throw하여 기능이 더 이상 지원되지 않음을 더 쉽게 검색할 수 있게 합니다.

## <a name="recommended-action"></a>권장 조치

- Windows 런타임 메타데이터(WinMD) 파일에서 인터페이스를 정의할 수 있는 경우에는 C#/WinRT 도구를 대신 사용합니다.

- 그렇지 않은 경우에는 인터페이스를 <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> 대신 <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown>으로 표시하고, <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> 메서드의 인터페이스 시작 부분에 더미 항목 3개를 추가합니다. 다음 코드 조각은 예제를 보여 줍니다.

  ```csharp
  [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
  interface IMine
  {
      // Do not call these three methods.
      // They're exclusively to fill in the slots in the vtable.
      void GetIIdsSlot();
      void GetRuntimeClassNameSlot();
      void GetTrustLevelSlot();

      // The original members of the IMine interface go here.
      ...
  }
  ```

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable`

### Category

Interop

-->
