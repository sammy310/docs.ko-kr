---
title: '방법: 백그라운드에서 작업 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 77f75a7eb1d7cc536df7110ef55727fbdf789f23
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591607"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="a9265-102">방법: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="a9265-102">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="a9265-103">완료하는 데 오랜 시간이 걸리는 작업이 있으며 사용자 인터페이스에서 지연이 발생되지 않게 하려는 경우 <xref:System.ComponentModel.BackgroundWorker> 클래스를 사용하여 다른 스레드에서 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9265-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="a9265-104">다음 코드 예제에서는 시간이 많이 걸리는 작업을 백그라운드에서 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9265-104">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="a9265-105">양식에는 **시작** 및 **취소** 단추가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9265-105">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="a9265-106">비동기 작업을 실행하려면 **시작** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a9265-106">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="a9265-107">비동기 작업 실행을 중지하려면 **취소** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a9265-107">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="a9265-108">각 작업의 결과가 <xref:System.Windows.Forms.MessageBox>에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9265-108">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="a9265-109">Visual Studio에서는 이 작업이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9265-109">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="a9265-110">또한 참조 [연습: 백그라운드에서 작업 실행](walkthrough-running-an-operation-in-the-background.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a9265-110">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9265-111">예제</span><span class="sxs-lookup"><span data-stu-id="a9265-111">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a9265-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a9265-112">Compiling the Code</span></span>  
 <span data-ttu-id="a9265-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a9265-113">This example requires:</span></span>  
  
- <span data-ttu-id="a9265-114">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="a9265-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9265-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="a9265-115">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="a9265-116">방법: 백그라운드 작업을 사용하는 양식 구현</span><span class="sxs-lookup"><span data-stu-id="a9265-116">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="a9265-117">BackgroundWorker 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a9265-117">BackgroundWorker Component</span></span>](backgroundworker-component.md)
