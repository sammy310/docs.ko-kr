---
title: SYSLIB0006 경고
description: 컴파일 시간 경고 SYSLIB0006을 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: a5ab4fe4576bd336cb7de0a91b889fa48ac5650a
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437467"
---
# <a name="syslib0006-threadabort-is-not-supported"></a><span data-ttu-id="f3c57-103">SYSLIB0006: Thread.Abort가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="f3c57-103">SYSLIB0006: Thread.Abort is not supported</span></span>

<span data-ttu-id="f3c57-104">다음 API는 .NET 5.0부터 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c57-104">The following APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="f3c57-105">이러한 API를 사용하면 컴파일 시간에 `SYSLIB0006` 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3c57-105">Use of these APIs generates warning `SYSLIB0006` at compile time.</span></span>

- <xref:System.Threading.Thread.Abort?displayProperty=nameWithType>
- <xref:System.Threading.Thread.Abort(System.Object)?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="f3c57-106">해결 방법</span><span class="sxs-lookup"><span data-stu-id="f3c57-106">Workarounds</span></span>

<span data-ttu-id="f3c57-107"><xref:System.Threading.CancellationToken>을 사용하여 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>를 호출하는 대신 작업 단위 처리를 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c57-107">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f3c57-108">다음 예제에서는 <xref:System.Threading.CancellationToken>합니다.</span><span class="sxs-lookup"><span data-stu-id="f3c57-108">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f3c57-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="f3c57-109">See also</span></span>

- [<span data-ttu-id="f3c57-110">Thread.Abort는 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="f3c57-110">Thread.Abort is obsolete</span></span>](core-libraries/5.0/thread-abort-obsolete.md)
- [<span data-ttu-id="f3c57-111">관리형 스레드에서의 취소</span><span class="sxs-lookup"><span data-stu-id="f3c57-111">Cancellation in managed threads</span></span>](../../standard/threading/cancellation-in-managed-threads.md)
