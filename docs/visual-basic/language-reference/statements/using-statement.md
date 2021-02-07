---
description: '자세한 정보: Using 문 (Visual Basic)'
title: Using 문
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: fea77a441182b7c3ecac58d4fe7f1297a87f086c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740888"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="e9aa6-103">Using 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9aa6-103">Using Statement (Visual Basic)</span></span>

<span data-ttu-id="e9aa6-104">블록의 시작을 선언 `Using` 하 고 필요에 따라 블록에서 제어 하는 시스템 리소스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-104">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>

## <a name="syntax"></a><span data-ttu-id="e9aa6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9aa6-105">Syntax</span></span>

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a><span data-ttu-id="e9aa6-106">부분</span><span class="sxs-lookup"><span data-stu-id="e9aa6-106">Parts</span></span>

|<span data-ttu-id="e9aa6-107">용어</span><span class="sxs-lookup"><span data-stu-id="e9aa6-107">Term</span></span>|<span data-ttu-id="e9aa6-108">정의</span><span class="sxs-lookup"><span data-stu-id="e9aa6-108">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="e9aa6-109">를 제공 하지 않는 경우 필수 사항 `resourceexpression` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-109">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="e9aa6-110">이 블록이 제어 하는 하나 이상의 시스템 리소스 목록 `Using` 으로, 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-110">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="e9aa6-111">를 제공 하지 않는 경우 필수 사항 `resourcelist` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-111">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="e9aa6-112">이 블록에 의해 제어 되는 시스템 리소스를 참조 하는 참조 변수 또는 식 `Using` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-112">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="e9aa6-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-113">Optional.</span></span> <span data-ttu-id="e9aa6-114">블록이 실행 하는 문 블록입니다 `Using` .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-114">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="e9aa6-115">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-115">Required.</span></span> <span data-ttu-id="e9aa6-116">블록의 정의를 종료 `Using` 하 고 제어 하는 모든 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-116">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  

 <span data-ttu-id="e9aa6-117">파트의 각 리소스에 `resourcelist` 는 다음과 같은 구문과 파트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-117">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 <span data-ttu-id="e9aa6-118">또는</span><span class="sxs-lookup"><span data-stu-id="e9aa6-118">-or-</span></span>

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a><span data-ttu-id="e9aa6-119">resourcelist 파트</span><span class="sxs-lookup"><span data-stu-id="e9aa6-119">resourcelist Parts</span></span>

|<span data-ttu-id="e9aa6-120">용어</span><span class="sxs-lookup"><span data-stu-id="e9aa6-120">Term</span></span>|<span data-ttu-id="e9aa6-121">정의</span><span class="sxs-lookup"><span data-stu-id="e9aa6-121">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="e9aa6-122">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-122">Required.</span></span> <span data-ttu-id="e9aa6-123">블록에서 제어 하는 시스템 리소스를 참조 하는 참조 변수입니다 `Using` .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-123">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="e9aa6-124">문이 리소스를 획득 하는 경우에 필요 `Using` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-124">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="e9aa6-125">이미 리소스를 취득 한 경우 두 번째 구문 대체 방법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-125">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="e9aa6-126">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-126">Required.</span></span> <span data-ttu-id="e9aa6-127">리소스의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-127">The class of the resource.</span></span> <span data-ttu-id="e9aa6-128">클래스는 인터페이스를 구현 해야 합니다 <xref:System.IDisposable> .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-128">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="e9aa6-129">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-129">Optional.</span></span> <span data-ttu-id="e9aa6-130">인스턴스를 만들기 위해 생성자에 전달 하는 인수 목록입니다 `resourcetype` .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-130">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="e9aa6-131">[매개 변수 목록](parameter-list.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-131">See [Parameter List](parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="e9aa6-132">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-132">Required.</span></span> <span data-ttu-id="e9aa6-133">의 요구 사항을 충족 하는 시스템 리소스를 참조 하는 변수 또는 식 `resourcetype` 입니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-133">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="e9aa6-134">두 번째 구문 대체 방법을 사용 하는 경우 제어를 문에 전달 하기 전에 리소스를 가져와야 합니다 `Using` .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-134">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9aa6-135">설명</span><span class="sxs-lookup"><span data-stu-id="e9aa6-135">Remarks</span></span>

 <span data-ttu-id="e9aa6-136">코드에 파일 핸들, COM 래퍼 또는 SQL 연결과 같은 관리 되지 않는 리소스가 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-136">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="e9aa6-137">`Using`블록은 코드가 완료 될 때 이러한 리소스를 하나 이상 삭제 하는 것을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-137">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="e9aa6-138">이렇게 하면 다른 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-138">This makes them available for other code to use.</span></span>

 <span data-ttu-id="e9aa6-139">관리 되는 리소스는 추가 코딩 없이 GC (.NET Framework 가비지 수집기)에 의해 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-139">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="e9aa6-140">`Using`관리 되는 리소스에 대 한 블록이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-140">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="e9aa6-141">그러나 `Using` 가비지 수집기를 대기 하는 대신 블록을 사용 하 여 관리 되는 리소스를 강제로 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-141">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

 <span data-ttu-id="e9aa6-142">`Using`블록은 획득, 사용 및 삭제의 세 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-142">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>

- <span data-ttu-id="e9aa6-143">*취득* 은 변수를 만들고 초기화 하 여 시스템 리소스를 참조 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-143">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="e9aa6-144">`Using`문은 하나 이상의 리소스를 얻거나 블록을 입력 하기 전에 정확히 하나의 리소스를 획득 한 후 문에 제공할 수 있습니다 `Using` .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-144">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="e9aa6-145">를 제공 하는 경우 `resourceexpression` 문에 제어를 전달 하기 전에 리소스를 얻어야 합니다 `Using` .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-145">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>

- <span data-ttu-id="e9aa6-146">*사용* 은 리소스에 액세스 하 고 작업을 수행 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-146">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="e9aa6-147">과 사이의 문은 `Using` `End Using` 리소스의 사용을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-147">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>

- <span data-ttu-id="e9aa6-148">*삭제* 는 <xref:System.IDisposable.Dispose%2A> 의 개체에 대해 메서드를 호출 하는 것을 의미 `resourcename` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-148">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="e9aa6-149">이렇게 하면 개체가 리소스를 완전히 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-149">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="e9aa6-150">`End Using`문은 블록의 컨트롤에 있는 리소스를 삭제 합니다 `Using` .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-150">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>

## <a name="behavior"></a><span data-ttu-id="e9aa6-151">동작</span><span class="sxs-lookup"><span data-stu-id="e9aa6-151">Behavior</span></span>

 <span data-ttu-id="e9aa6-152">블록은 `Using` `Try` `Finally` `Try` 블록이 리소스를 사용 하 고 블록에서 해당 리소스를 `Finally` 삭제 하는 ... 생성 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-152">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="e9aa6-153">따라서 블록을 `Using` 종료 하는 방법에 관계 없이 블록은 리소스 삭제를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-153">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="e9aa6-154">이는를 제외 하 고 처리 되지 않은 예외의 경우에도 마찬가지입니다 <xref:System.StackOverflowException> .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-154">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>

 <span data-ttu-id="e9aa6-155">문에 의해 획득 된 모든 리소스 변수의 범위는 `Using` 블록으로 제한 됩니다 `Using` .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-155">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>

 <span data-ttu-id="e9aa6-156">문에서 둘 이상의 시스템 리소스를 지정 하는 경우 `Using` 다른 범위 내에 블록을 중첩 한 것과 같은 결과가 나타납니다 `Using` .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-156">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>

 <span data-ttu-id="e9aa6-157">`resourcename`가 이면 `Nothing` 에 대 한 호출이 <xref:System.IDisposable.Dispose%2A> 수행 되지 않으며 예외가 throw 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-157">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>

## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="e9aa6-158">Using 블록 내에서 구조적 예외 처리</span><span class="sxs-lookup"><span data-stu-id="e9aa6-158">Structured Exception Handling Within a Using Block</span></span>

 <span data-ttu-id="e9aa6-159">블록에서 발생할 수 있는 예외를 처리 해야 하는 경우 `Using` 전체 `Try` ... 생성을 추가할 수 있습니다. `Finally`</span><span class="sxs-lookup"><span data-stu-id="e9aa6-159">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="e9aa6-160">문이 리소스를 획득 하는 데 실패 한 경우를 처리 해야 하는 경우를 테스트 하 여 `Using` 가 인지를 확인할 수 있습니다 `resourcename` `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-160">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>

## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="e9aa6-161">Using 블록 대신 구조적 예외 처리</span><span class="sxs-lookup"><span data-stu-id="e9aa6-161">Structured Exception Handling Instead of a Using Block</span></span>

 <span data-ttu-id="e9aa6-162">리소스 획득을 보다 세부적으로 제어 해야 하거나 블록에 추가 코드가 필요한 경우 `Finally` `Using` 블록을 `Try` ... `Finally` 생성으로 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-162">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="e9aa6-163">다음 예제에서는 `Try` `Using` 의 획득 및 삭제에 해당 하는 해골 및 생성을 보여 줍니다 `resource` .</span><span class="sxs-lookup"><span data-stu-id="e9aa6-163">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>

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
> <span data-ttu-id="e9aa6-164">블록 내의 코드는 `Using` 개체를 다른 변수에 할당 하면 안 `resourcename` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-164">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="e9aa6-165">블록을 종료 하면 `Using` 리소스가 삭제 되 고 다른 변수는 가리키는 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-165">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>

## <a name="example"></a><span data-ttu-id="e9aa6-166">예제</span><span class="sxs-lookup"><span data-stu-id="e9aa6-166">Example</span></span>

 <span data-ttu-id="e9aa6-167">다음 예에서는 log.txt 라는 파일을 만들고 두 줄의 텍스트를 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-167">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="e9aa6-168">또한이 예제에서는 동일한 파일을 읽고 텍스트 줄을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-168">The example also reads that same file and displays the lines of text:</span></span>

 <span data-ttu-id="e9aa6-169">및 클래스는 인터페이스를 구현 하기 때문에 <xref:System.IO.TextWriter> <xref:System.IO.TextReader> <xref:System.IDisposable> 코드는 `Using` 문을 사용 하 여 쓰기 및 읽기 작업 후에 파일이 올바르게 닫혀 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9aa6-169">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a><span data-ttu-id="e9aa6-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9aa6-170">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="e9aa6-171">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="e9aa6-171">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="e9aa6-172">방법: 시스템 리소스 삭제</span><span class="sxs-lookup"><span data-stu-id="e9aa6-172">How to: Dispose of a System Resource</span></span>](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
