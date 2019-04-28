---
title: '방법: 백그라운드 작업을 사용하는 양식 구현'
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
ms.openlocfilehash: 98d51f9c6465186e77784aba080130110545f399
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941190"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="d5d12-102">방법: 백그라운드 작업을 사용하는 양식 구현</span><span class="sxs-lookup"><span data-stu-id="d5d12-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="d5d12-103">다음 예제 프로그램은 피보나치 숫자를 계산하는 폼을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d5d12-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="d5d12-104">계산은 사용자 인터페이스 스레드와 별개인 스레드에서 실행되므로 계산이 진행될 때 사용자 인터페이스가 지연 없이 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d12-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="d5d12-105">Visual Studio에서는 이 작업이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d12-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="d5d12-106">또한 참조 [연습: 백그라운드 작업을 사용 하는 폼 구현](walkthrough-implementing-a-form-that-uses-a-background-operation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d12-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5d12-107">예제</span><span class="sxs-lookup"><span data-stu-id="d5d12-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d5d12-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d5d12-108">Compiling the Code</span></span>  
 <span data-ttu-id="d5d12-109">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d12-109">This example requires:</span></span>  
  
- <span data-ttu-id="d5d12-110">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="d5d12-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="d5d12-111">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d12-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d5d12-112">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d12-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d5d12-113">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d5d12-113">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d5d12-114">모든 종류의 다중 스레딩을 사용할 때는 매우 심각하고 복잡한 버그에 잠재적으로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d12-114">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="d5d12-115">다중 스레딩을 사용하는 솔루션을 구현하기 전에 [관리되는 스레딩을 구현하는 최선의 방법](../../../standard/threading/managed-threading-best-practices.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d5d12-115">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d12-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5d12-116">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="d5d12-117">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="d5d12-117">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="d5d12-118">관리되는 스레딩을 구현하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="d5d12-118">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
