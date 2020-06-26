---
title: '방법: 애플리케이션 코드에 추적 문 추가'
description: .NET의 응용 프로그램 코드에 trace 문을 추가 하는 방법에 대해 알아봅니다. 추적에 가장 자주 사용 되는 메서드는 출력을 수신기에 쓰기 위한 메서드입니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], conditional writes based on switches
- trace statements
- WriteLineIf method
- tracing [.NET Framework], adding trace statements
- Assert method, tracing code
- trace switches, conditional writes based on switches
- WriteIf method
ms.assetid: f3a93fa7-1717-467d-aaff-393e5c9828b4
ms.openlocfilehash: 0c75a8775649aabe73b02187c4604d2eb3a8435b
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415890"
---
# <a name="how-to-add-trace-statements-to-application-code"></a><span data-ttu-id="a9b90-104">방법: 애플리케이션 코드에 추적 문 추가</span><span class="sxs-lookup"><span data-stu-id="a9b90-104">How to: Add Trace Statements to Application Code</span></span>
<span data-ttu-id="a9b90-105">추적에 가장 자주 사용되는 메서드는 **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert**, **Fail** 등 수신기로 출력을 작성하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-105">The methods used most often for tracing are the methods for writing output to listeners: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert**, and **Fail**.</span></span> <span data-ttu-id="a9b90-106">이러한 메서드는 두 범주로 나눌 수 있습니다. 즉, **Write**, **WriteLine** 및 **Fail** 메서드는 모두 조건 없이 출력을 내보내지만, **WriteIf**, **WriteLineIf** 및 **Assert** 메서드는 부울 조건을 테스트하고 조건의 값에 따라 기록하거나 기록하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-106">These methods can be divided into two categories: **Write**, **WriteLine**, and **Fail** all emit output unconditionally, whereas **WriteIf**, **WriteLineIf**, and **Assert** test a Boolean condition, and write or do not write based on the value of the condition.</span></span> <span data-ttu-id="a9b90-107">**WriteIf** 및 **WriteLineIf** 메서드는 조건이 `true`인 경우 출력을 내보내며 **Assert** 메서드는 조건이 `false`인 경우 출력을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-107">**WriteIf** and **WriteLineIf** emit output if the condition is `true`, and **Assert** emits output if the condition is `false`.</span></span>  
  
 <span data-ttu-id="a9b90-108">추적 및 디버깅 전략을 디자인할 때 원하는 출력 모양을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-108">When designing your tracing and debugging strategy, you should think about how you want the output to look.</span></span> <span data-ttu-id="a9b90-109">관련 없는 정보로 채워진 여러 **Write** 문은 읽기 어려운 로그를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-109">Multiple **Write** statements filled with unrelated information will create a log that is difficult to read.</span></span> <span data-ttu-id="a9b90-110">다른 한편으로는 **WriteLine**을 사용하여 별도의 줄에 관련된 문을 넣으면 함께 속한 정보를 구분하기 어렵게 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-110">On the other hand, using **WriteLine** to put related statements on separate lines may make it difficult to distinguish what information belongs together.</span></span> <span data-ttu-id="a9b90-111">일반적으로 여러 소스의 정보를 결합하여 단일 정보 메시지를 생성하려는 경우 여러 **Write** 문을 사용하고, 완전한 단일 메시지를 생성하려는 경우 **WriteLine** 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-111">In general, use multiple **Write** statements when you want to combine information from multiple sources to create a single informative message, and use the **WriteLine** statement when you want to create a single, complete message.</span></span>  
  
### <a name="to-write-a-complete-line"></a><span data-ttu-id="a9b90-112">완전한 줄을 작성하려면</span><span class="sxs-lookup"><span data-stu-id="a9b90-112">To write a complete line</span></span>  
  
1. <span data-ttu-id="a9b90-113"><xref:System.Diagnostics.Trace.WriteLine%2A> 또는 <xref:System.Diagnostics.Trace.WriteLineIf%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-113">Call the <xref:System.Diagnostics.Trace.WriteLine%2A> or <xref:System.Diagnostics.Trace.WriteLineIf%2A> method.</span></span>  
  
     <span data-ttu-id="a9b90-114">이 메서드가 반환하는 메시지의 끝에 캐리지 리턴을 추가합니다. 그러면 **Write**, **WriteIf**, **WriteLine** 또는 **WriteLineIf**에서 반환한 다음 메시지가 다음 줄에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-114">A carriage return is appended to the end of the message this method returns, so that the next message returned by **Write**, **WriteIf**, **WriteLine**, or **WriteLineIf** will begin on the following line:</span></span>  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteLine("Error in AppendData procedure.")  
    Trace.WriteLineIf(errorFlag, "Error in AppendData procedure.")  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteLine ("Error in AppendData procedure.");  
    System.Diagnostics.Trace.WriteLineIf(errorFlag,
       "Error in AppendData procedure.");  
    ```  
  
### <a name="to-write-a-partial-line"></a><span data-ttu-id="a9b90-115">부분 줄을 작성하려면</span><span class="sxs-lookup"><span data-stu-id="a9b90-115">To write a partial line</span></span>  
  
1. <span data-ttu-id="a9b90-116"><xref:System.Diagnostics.Trace.Write%2A> 또는 <xref:System.Diagnostics.Trace.WriteIf%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-116">Call the <xref:System.Diagnostics.Trace.Write%2A> or <xref:System.Diagnostics.Trace.WriteIf%2A> method.</span></span>  
  
     <span data-ttu-id="a9b90-117">**Write**, **WriteIf**, **WriteLine** 또는 **WriteLineIf**에서 출력하는 다음 메시지는 **Write** 또는 **WriteIf** 문에서 출력하는 메시지와 동일한 줄에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-117">The next message put out by a **Write**, **WriteIf**, **WriteLine**, or **WriteLineIf** will begin on the same line as the message put out by the **Write** or **WriteIf** statement:</span></span>  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteIf(errorFlag, "Error in AppendData procedure.")  
    Debug.WriteIf(errorFlag, "Transaction abandoned.")  
    Trace.Write("Invalid value for data request")  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteIf(errorFlag,
       "Error in AppendData procedure.");  
    System.Diagnostics.Debug.WriteIf(errorFlag, "Transaction abandoned.");  
    Trace.Write("Invalid value for data request");  
    ```  
  
### <a name="to-verify-that-certain-conditions-exist-either-before-or-after-you-execute-a-method"></a><span data-ttu-id="a9b90-118">메서드를 실행하기 전후에 특정 조건이 있는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="a9b90-118">To verify that certain conditions exist either before or after you execute a method</span></span>  
  
1. <span data-ttu-id="a9b90-119"><xref:System.Diagnostics.Trace.Assert%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-119">Call the <xref:System.Diagnostics.Trace.Assert%2A> method.</span></span>  
  
    ```vb  
    Dim i As Integer = 4  
    Trace.Assert(i = 5, "i is not equal to 5.")  
    ```  
  
    ```csharp  
    int i = 4;  
    System.Diagnostics.Trace.Assert(i == 5, "i is not equal to 5.");  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="a9b90-120">추적과 디버깅 둘 다에 **Assert**를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-120">You can use **Assert** with both tracing and debugging.</span></span> <span data-ttu-id="a9b90-121">이 예제에서는 **수신기** 컬렉션의 수신기로 호출 스택을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b90-121">This example outputs the call stack to any listener in the **Listeners** collection.</span></span> <span data-ttu-id="a9b90-122">자세한 내용은 [관리 코드의 어설션](/visualstudio/debugger/assertions-in-managed-code) 및 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9b90-122">For more information, see [Assertions in Managed Code](/visualstudio/debugger/assertions-in-managed-code) and <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9b90-123">추가 정보</span><span class="sxs-lookup"><span data-stu-id="a9b90-123">See also</span></span>

- <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a9b90-124">애플리케이션 추적 및 조율</span><span class="sxs-lookup"><span data-stu-id="a9b90-124">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="a9b90-125">방법: 추적 스위치 만들기, 초기화 및 구성</span><span class="sxs-lookup"><span data-stu-id="a9b90-125">How to: Create, Initialize and Configure Trace Switches</span></span>](how-to-create-initialize-and-configure-trace-switches.md)
- [<span data-ttu-id="a9b90-126">추적 스위치</span><span class="sxs-lookup"><span data-stu-id="a9b90-126">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="a9b90-127">추적 수신기</span><span class="sxs-lookup"><span data-stu-id="a9b90-127">Trace Listeners</span></span>](trace-listeners.md)
