---
title: '방법: 백그라운드 작업을 사용하는 양식 구현'
description: 다른 작업이 진행 되는 동안 한 작업을 계속 실행할 수 있도록 백그라운드 작업을 사용 하는 Windows Form을 구현 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
ms.openlocfilehash: 23bf4bc02fbf998d92dfce6d84e4e337cbefe7d9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174525"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="a9b47-103">방법: 백그라운드 작업을 사용하는 양식 구현</span><span class="sxs-lookup"><span data-stu-id="a9b47-103">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="a9b47-104">다음 예제 프로그램은 피보나치 숫자를 계산하는 폼을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a9b47-104">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="a9b47-105">계산은 사용자 인터페이스 스레드와 별개인 스레드에서 실행되므로 계산이 진행될 때 사용자 인터페이스가 지연 없이 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9b47-105">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="a9b47-106">Visual Studio에서는 이 작업이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9b47-106">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="a9b47-107">또한 [연습: 백그라운드 작업을 사용하는 양식 구현](walkthrough-implementing-a-form-that-uses-a-background-operation.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9b47-107">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9b47-108">예제</span><span class="sxs-lookup"><span data-stu-id="a9b47-108">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a9b47-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a9b47-109">Compiling the Code</span></span>  
 <span data-ttu-id="a9b47-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b47-110">This example requires:</span></span>  
  
- <span data-ttu-id="a9b47-111">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="a9b47-111">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a9b47-112">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="a9b47-112">Robust Programming</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="a9b47-113">모든 종류의 다중 스레딩을 사용할 때는 매우 심각하고 복잡한 버그에 잠재적으로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9b47-113">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="a9b47-114">다중 스레딩을 사용하는 솔루션을 구현하기 전에 [관리되는 스레딩을 구현하는 최선의 방법](../../../standard/threading/managed-threading-best-practices.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9b47-114">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9b47-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9b47-115">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="a9b47-116">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="a9b47-116">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="a9b47-117">관리되는 스레딩을 구현하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="a9b47-117">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
