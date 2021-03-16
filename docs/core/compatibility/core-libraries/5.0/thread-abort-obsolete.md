---
title: '호환성이 손상되는 변경: Thread.Abort는 사용되지 않음'
description: Thread.Abort API가 사용되지 않는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 29c688250593801bab9b32b9e787911e561ec000
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257065"
---
# <a name="threadabort-is-obsolete"></a>Thread.Abort는 사용되지 않음

<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> API는 사용되지 않습니다. 해당 메서드가 호출되는 경우 .NET 5 이상 버전을 대상으로 하는 프로젝트에서는 컴파일 시간 경고 `SYSLIB0006`이 발생합니다.

## <a name="change-description"></a>변경 내용 설명

이전에는 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 호출이 컴파일 시간 경고가 생성되지 않았지만 해당 메서드는 런타임에 <xref:System.PlatformNotSupportedException>을 throw했습니다.

.NET 5부터 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>는 경고로 사용되지 않는 것으로 표시됩니다. 해당 메서드를 호출하면 컴파일러 경고 `SYSLIB0006`이 생성됩니다. 메서드의 구현은 변경되지 않으며 계속해서 <xref:System.PlatformNotSupportedException>을 throw합니다.

## <a name="reason-for-change"></a>변경 이유

<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>가 .NET Framework를 제외한 모든 .NET 구현에서 항상 <xref:System.PlatformNotSupportedException>을 throw하는 것을 고려하여 메서드가 호출된 위치로 주의를 끌기 위해 <xref:System.ObsoleteAttribute>가 메서드에 추가되었습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

- <xref:System.Threading.CancellationToken>을 사용하여 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>를 호출하는 대신 작업 단위 처리를 중단합니다. 다음 예제에서는 <xref:System.Threading.CancellationToken>합니다.

  ```csharp
  void ProcessPendingWorkItemsNew(CancellationToken cancellationToken)
  {
      if (QueryIsMoreWorkPending())
      {
          // If the CancellationToken is marked as "needs to cancel",
          // this will throw the appropriate exception.
          cancellationToken.ThrowIfCancellationRequested();

          WorkItem work = DequeueWorkItem();
          ProcessWorkItem(work);
      }
  }
  ```

  자세한 내용은 [관리형 스레드의 취소](../../../../standard/threading/cancellation-in-managed-threads.md)를 참조하세요.

- 컴파일 시간 경고를 제거하려면 경고 코드 `SYSLIB0006`을 제거합니다. 경고 코드는 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>와 관련되며 경고 코드를 제거해도 코드에서 다른 사용 중지 경고는 제거되지 않습니다. 그러나 경고를 제거하는 대신 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 호출을 제거하는 것이 좋습니다.

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  프로젝트 파일에서도 경고를 표시하지 않을 수 있습니다.

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
