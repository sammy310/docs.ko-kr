---
title: Using 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 346a26ad5751599831d8b0d3e0497e4d488eb76c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957540"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="2fc20-102">Using 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fc20-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="2fc20-103">`Using` 블록의 시작을 선언 하 고 필요에 따라 블록에서 제어 하는 시스템 리소스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fc20-104">구문</span><span class="sxs-lookup"><span data-stu-id="2fc20-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="2fc20-105">요소</span><span class="sxs-lookup"><span data-stu-id="2fc20-105">Parts</span></span>  
  
|<span data-ttu-id="2fc20-106">용어</span><span class="sxs-lookup"><span data-stu-id="2fc20-106">Term</span></span>|<span data-ttu-id="2fc20-107">정의</span><span class="sxs-lookup"><span data-stu-id="2fc20-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="2fc20-108">를 제공 `resourceexpression`하지 않는 경우 필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="2fc20-109">이 `Using` 블록이 제어 하는 하나 이상의 시스템 리소스 목록으로, 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="2fc20-110">를 제공 `resourcelist`하지 않는 경우 필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="2fc20-111">이 `Using` 블록에 의해 제어 되는 시스템 리소스를 참조 하는 참조 변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="2fc20-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-112">Optional.</span></span> <span data-ttu-id="2fc20-113">`Using` 블록이 실행 하는 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="2fc20-114">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2fc20-114">Required.</span></span> <span data-ttu-id="2fc20-115">`Using` 블록의 정의를 종료 하 고 제어 하는 모든 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="2fc20-116">`resourcelist` 파트의 각 리소스에는 다음과 같은 구문과 파트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="2fc20-117">또는</span><span class="sxs-lookup"><span data-stu-id="2fc20-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="2fc20-118">resourcelist 파트</span><span class="sxs-lookup"><span data-stu-id="2fc20-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="2fc20-119">용어</span><span class="sxs-lookup"><span data-stu-id="2fc20-119">Term</span></span>|<span data-ttu-id="2fc20-120">정의</span><span class="sxs-lookup"><span data-stu-id="2fc20-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="2fc20-121">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2fc20-121">Required.</span></span> <span data-ttu-id="2fc20-122">블록에서 `Using` 제어 하는 시스템 리소스를 참조 하는 참조 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="2fc20-123">문이 리소스를 `Using` 획득 하는 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="2fc20-124">이미 리소스를 취득 한 경우 두 번째 구문 대체 방법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="2fc20-125">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2fc20-125">Required.</span></span> <span data-ttu-id="2fc20-126">리소스의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-126">The class of the resource.</span></span> <span data-ttu-id="2fc20-127">클래스는 인터페이스를 <xref:System.IDisposable> 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="2fc20-128">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-128">Optional.</span></span> <span data-ttu-id="2fc20-129">인스턴스를 만들기 위해 생성자에 전달 하는 인수 목록입니다 `resourcetype`.</span><span class="sxs-lookup"><span data-stu-id="2fc20-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="2fc20-130">[매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2fc20-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="2fc20-131">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2fc20-131">Required.</span></span> <span data-ttu-id="2fc20-132">의 `resourcetype`요구 사항을 충족 하는 시스템 리소스를 참조 하는 변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="2fc20-133">두 번째 구문 대체 방법을 사용 하는 경우 제어 `Using` 를 문에 전달 하기 전에 리소스를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fc20-134">설명</span><span class="sxs-lookup"><span data-stu-id="2fc20-134">Remarks</span></span>  
 <span data-ttu-id="2fc20-135">코드에 파일 핸들, COM 래퍼 또는 SQL 연결과 같은 관리 되지 않는 리소스가 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="2fc20-136">블록 `Using` 은 코드가 완료 될 때 이러한 리소스를 하나 이상 삭제 하는 것을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="2fc20-137">이렇게 하면 다른 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="2fc20-138">관리 되는 리소스는 추가 코딩 없이 GC (.NET Framework 가비지 수집기)에 의해 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="2fc20-139">관리 되는 리소스에 `Using` 대 한 블록이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="2fc20-140">그러나 가비지 수집기를 대기 하는 `Using` 대신 블록을 사용 하 여 관리 되는 리소스를 강제로 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="2fc20-141">블록 `Using` 은 획득, 사용 및 삭제의 세 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
- <span data-ttu-id="2fc20-142">*취득* 은 변수를 만들고 초기화 하 여 시스템 리소스를 참조 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="2fc20-143">문은 하나 이상의 리소스를 얻거나 블록을 입력 하기 전에 정확히 하나의 리소스를 획득 한 후 `Using` 문에 제공할 수 있습니다. `Using`</span><span class="sxs-lookup"><span data-stu-id="2fc20-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="2fc20-144">를 제공 `resourceexpression`하는 경우 `Using` 문에 제어를 전달 하기 전에 리소스를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
- <span data-ttu-id="2fc20-145">*사용* 은 리소스에 액세스 하 고 작업을 수행 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="2fc20-146">`Using` 과`End Using` 사이의 문은 리소스의 사용을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
- <span data-ttu-id="2fc20-147">*삭제* 는의 <xref:System.IDisposable.Dispose%2A> `resourcename`개체에 대해 메서드를 호출 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="2fc20-148">이렇게 하면 개체가 리소스를 완전히 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="2fc20-149">`End Using` 문은 `Using` 블록의 컨트롤에 있는 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="2fc20-150">동작</span><span class="sxs-lookup"><span data-stu-id="2fc20-150">Behavior</span></span>  
 <span data-ttu-id="2fc20-151">`Using` 블록`Try`은 ... 블록에서 리소스 를`Finally` 사용 하 고 블록에서 리소스를 삭제 하는 구문입니다. `Finally` `Try`</span><span class="sxs-lookup"><span data-stu-id="2fc20-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="2fc20-152">따라서 블록을 종료 하 `Using` 는 방법에 관계 없이 블록은 리소스 삭제를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="2fc20-153">이는를 <xref:System.StackOverflowException>제외 하 고 처리 되지 않은 예외의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="2fc20-154">`Using` 문에 의해 획득 된 모든 리소스 변수의 범위는 `Using` 블록으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="2fc20-155">`Using` 문에서 둘 이상의 시스템 리소스를 지정 하는 경우 다른 범위 내에 블록을 중첩 `Using` 한 것과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="2fc20-156">가 이면에 대<xref:System.IDisposable.Dispose%2A> 한 호출이 수행 되지 않으며 예외가 throw 되지 않습니다. `Nothing` `resourcename`</span><span class="sxs-lookup"><span data-stu-id="2fc20-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="2fc20-157">Using 블록 내에서 구조적 예외 처리</span><span class="sxs-lookup"><span data-stu-id="2fc20-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="2fc20-158">`Using` 블록에서 발생할 수 있는 예외를 처리 해야 하는 경우 전체 `Try`를 추가할 수 있습니다. `Finally` 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="2fc20-159">`Using` 문이 리소스를 획득 하는 데 실패 한 경우를 처리 해야 하는 경우를 테스트 하 여 `resourcename` 가 인지 `Nothing`를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="2fc20-160">Using 블록 대신 구조적 예외 처리</span><span class="sxs-lookup"><span data-stu-id="2fc20-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="2fc20-161">리소스 획득을 보다 세부적으로 제어 해야 하는 경우 또는 `Finally` 블록 `Using` 에 추가 코드가 필요한 경우 블록 `Try`을 ... `Finally` 생성.</span><span class="sxs-lookup"><span data-stu-id="2fc20-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="2fc20-162">다음 예제에서는의 `Try` `resource`획득 및 `Using` 삭제에 해당 하는 해골 및 생성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
> <span data-ttu-id="2fc20-163">`Using` 블록 내의 코드는 `resourcename` 개체를 다른 변수에 할당 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="2fc20-164">`Using` 블록을 종료 하면 리소스가 삭제 되 고 다른 변수는 가리키는 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fc20-165">예제</span><span class="sxs-lookup"><span data-stu-id="2fc20-165">Example</span></span>  
 <span data-ttu-id="2fc20-166">다음 예에서는 .log 라는 파일을 만들고 두 줄의 텍스트를 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="2fc20-167">또한이 예제에서는 동일한 파일을 읽고 텍스트 줄을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="2fc20-168">및 <xref:System.IO.TextWriter> <xref:System.IDisposable> 클래스는 인터페이스를 구현 하기 때문에 코드는 문을 `Using` 사용 하 여 쓰기 및 읽기 작업 후에 파일이 올바르게 닫혀 있는지 확인할 수 있습니다. <xref:System.IO.TextReader></span><span class="sxs-lookup"><span data-stu-id="2fc20-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a><span data-ttu-id="2fc20-169">참고자료</span><span class="sxs-lookup"><span data-stu-id="2fc20-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="2fc20-170">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="2fc20-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="2fc20-171">방법: 시스템 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc20-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
