---
title: SYSLIB0006 경고
description: 컴파일 시간 경고 SYSLIB0006을 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 222b669a8a0260713e85721e6031144bb7bda5cc
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440662"
---
# <a name="syslib0006-threadabort-is-not-supported"></a>SYSLIB0006: Thread.Abort가 지원되지 않음

다음 API는 .NET 5.0부터 사용되지 않는 것으로 표시됩니다. 이러한 API를 사용하면 컴파일 시간에 `SYSLIB0006` 경고가 생성됩니다.

- <xref:System.Threading.Thread.Abort?displayProperty=nameWithType>
- <xref:System.Threading.Thread.Abort(System.Object)?displayProperty=nameWithType>

## <a name="workarounds"></a>해결 방법

<xref:System.Threading.CancellationToken>을 사용하여 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>를 호출하는 대신 작업 단위 처리를 중단합니다. 다음 예제에서는 <xref:System.Threading.CancellationToken>합니다.

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

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>추가 정보

- [Thread.Abort가 사용되지 않음 - 호환성이 손상되는 변경](3.1-5.0.md#threadabort-is-obsolete)
- [관리형 스레드에서의 취소](../../standard/threading/cancellation-in-managed-threads.md)
