---
title: '방법: 이벤트 기반 비동기 패턴의 클라이언트 구현'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET], asynchronous features
- components [.NET], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
ms.openlocfilehash: 95997f219a08c131905cfc86b78e94c36f3ec851
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888817"
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a><span data-ttu-id="115a4-102">방법: 이벤트 기반 비동기 패턴의 클라이언트 구현</span><span class="sxs-lookup"><span data-stu-id="115a4-102">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="115a4-103">다음 코드 예제는 [이벤트 기반 비동기 패턴 개요](event-based-asynchronous-pattern-overview.md)를 준수하는 구성 요소를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="115a4-103">The following code example demonstrates how to use a component that adheres to the [Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md).</span></span> <span data-ttu-id="115a4-104">이 예제의 양식은 [방법: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현](component-that-supports-the-event-based-asynchronous-pattern.md)에 설명된 `PrimeNumberCalculator` 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="115a4-104">The form for this example uses the `PrimeNumberCalculator` component described in [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="115a4-105">이 예제를 사용하는 프로젝트를 실행하는 경우 그리드와 2개의 단추 즉, **새 작업 시작** 및 **취소** 단추가 있는 “소수 계산기” 양식이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="115a4-105">When you run a project that uses this example, you will see a "Prime Number Calculator" form with a grid and two buttons: **Start New Task** and **Cancel** .</span></span> <span data-ttu-id="115a4-106">**새 작업 시작** 단추를 연속으로 여러 번 클릭할 수 있습니다. 클릭할 때마다 비동기 작업이 무작위로 생성된 테스트 숫자가 소수인지 여부를 확인하기 위해 계산을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="115a4-106">You can click the **Start New Task** button several times in succession, and for each click, an asynchronous operation will begin a computation to determine if a randomly generated test number is prime.</span></span> <span data-ttu-id="115a4-107">양식은 진행률 및 증분 결과를 주기적으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="115a4-107">The form will periodically display progress and incremental results.</span></span> <span data-ttu-id="115a4-108">각 작업에는 고유한 작업 ID가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="115a4-108">Each operation is assigned a unique task ID.</span></span> <span data-ttu-id="115a4-109">계산의 결과는 **결과** 열에 표시됩니다. 테스트 숫자가 소수가 아닌 경우 **합성수** 로 레이블이 지정되며 첫 번째 약수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="115a4-109">The result of the computation is displayed in the **Result** column; if the test number is not prime, it is labeled as **Composite,** and its first divisor is displayed.</span></span>  
  
 <span data-ttu-id="115a4-110">보류 중인 작업은 **취소** 단추로 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="115a4-110">Any pending operation can be canceled with the **Cancel** button.</span></span> <span data-ttu-id="115a4-111">여러 번 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="115a4-111">Multiple selections can be made.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="115a4-112">대부분의 숫자는 소수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="115a4-112">Most numbers will not be prime.</span></span> <span data-ttu-id="115a4-113">몇 가지 작업을 완료한 후에도 소수를 찾지 못한 경우 단지 더 많은 작업을 시작하면 결국 몇 개의 소수를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="115a4-113">If you have not found a prime number after several completed operations, simply start more tasks, and eventually you will find some prime numbers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="115a4-114">예제</span><span class="sxs-lookup"><span data-stu-id="115a4-114">Example</span></span>  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="115a4-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="115a4-115">See also</span></span>

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
