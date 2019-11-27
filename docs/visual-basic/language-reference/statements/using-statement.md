---
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
ms.openlocfilehash: 6ec0e228b3898f66f27e322b5db2dd7f3bf3d7d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352765"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="12205-102">Using 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12205-102">Using Statement (Visual Basic)</span></span>

<span data-ttu-id="12205-103">`Using` 블록의 시작을 선언 하 고, 선택적으로 블록에서 제어 하는 시스템 리소스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="12205-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>

## <a name="syntax"></a><span data-ttu-id="12205-104">구문</span><span class="sxs-lookup"><span data-stu-id="12205-104">Syntax</span></span>

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a><span data-ttu-id="12205-105">요소</span><span class="sxs-lookup"><span data-stu-id="12205-105">Parts</span></span>

|<span data-ttu-id="12205-106">용어</span><span class="sxs-lookup"><span data-stu-id="12205-106">Term</span></span>|<span data-ttu-id="12205-107">정의</span><span class="sxs-lookup"><span data-stu-id="12205-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="12205-108">`resourceexpression`를 제공 하지 않는 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="12205-109">이 `Using` 차단 하는 하나 이상의 시스템 리소스 목록으로, 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="12205-110">`resourcelist`를 제공 하지 않는 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="12205-111">이 `Using` 블록에 의해 제어 되는 시스템 리소스를 참조 하는 변수 또는 식 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="12205-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="12205-112">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="12205-112">Optional.</span></span> <span data-ttu-id="12205-113">`Using` 블록이 실행 하는 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="12205-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="12205-114">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="12205-114">Required.</span></span> <span data-ttu-id="12205-115">`Using` 블록의 정의를 종료 하 고 제어 하는 모든 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  

 <span data-ttu-id="12205-116">`resourcelist` 파트의 각 리소스에는 다음과 같은 구문과 파트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 <span data-ttu-id="12205-117">-또는-</span><span class="sxs-lookup"><span data-stu-id="12205-117">-or-</span></span>

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a><span data-ttu-id="12205-118">resourcelist 파트</span><span class="sxs-lookup"><span data-stu-id="12205-118">resourcelist Parts</span></span>

|<span data-ttu-id="12205-119">용어</span><span class="sxs-lookup"><span data-stu-id="12205-119">Term</span></span>|<span data-ttu-id="12205-120">정의</span><span class="sxs-lookup"><span data-stu-id="12205-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="12205-121">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="12205-121">Required.</span></span> <span data-ttu-id="12205-122">`Using` 블록에서 제어 하는 시스템 리소스를 참조 하는 참조 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="12205-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="12205-123">`Using` 문이 리소스를 획득 하는 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="12205-124">이미 리소스를 취득 한 경우 두 번째 구문 대체 방법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="12205-125">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="12205-125">Required.</span></span> <span data-ttu-id="12205-126">리소스의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="12205-126">The class of the resource.</span></span> <span data-ttu-id="12205-127">클래스는 <xref:System.IDisposable> 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="12205-128">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="12205-128">Optional.</span></span> <span data-ttu-id="12205-129">`resourcetype`인스턴스를 만들기 위해 생성자에 전달 하는 인수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="12205-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="12205-130">[매개 변수 목록](parameter-list.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="12205-130">See [Parameter List](parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="12205-131">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="12205-131">Required.</span></span> <span data-ttu-id="12205-132">`resourcetype`요구 사항을 충족 하는 시스템 리소스를 참조 하는 변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="12205-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="12205-133">두 번째 구문 대체 방법을 사용 하는 경우 제어를 `Using` 문에 전달 하기 전에 리소스를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12205-134">주의</span><span class="sxs-lookup"><span data-stu-id="12205-134">Remarks</span></span>

 <span data-ttu-id="12205-135">코드에 파일 핸들, COM 래퍼 또는 SQL 연결과 같은 관리 되지 않는 리소스가 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="12205-136">`Using` 블록은 코드가 완료 될 때 이러한 리소스를 하나 이상 삭제 하는 것을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="12205-137">이렇게 하면 다른 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-137">This makes them available for other code to use.</span></span>

 <span data-ttu-id="12205-138">관리 되는 리소스는 추가 코딩 없이 GC (.NET Framework 가비지 수집기)에 의해 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12205-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="12205-139">관리 되는 리소스에 대 한 `Using` 블록은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="12205-140">그러나 계속 해 서 `Using` 블록을 사용 하 여 가비지 수집기를 대기 하지 않고 관리 되는 리소스를 강제로 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

 <span data-ttu-id="12205-141">`Using` 블록은 획득, 사용 및 삭제의 세 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12205-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>

- <span data-ttu-id="12205-142">*취득* 은 변수를 만들고 초기화 하 여 시스템 리소스를 참조 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="12205-143">`Using` 문은 하나 이상의 리소스를 얻거나, 블록을 입력 하기 전에 정확히 하나의 리소스를 획득 한 다음 `Using` 문에 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="12205-144">`resourceexpression`를 제공 하는 경우 `Using` 문으로 제어를 전달 하기 전에 리소스를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>

- <span data-ttu-id="12205-145">*사용* 은 리소스에 액세스 하 고 작업을 수행 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="12205-146">`Using`와 `End Using` 사이에 있는 문은 리소스 사용을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12205-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>

- <span data-ttu-id="12205-147">*삭제* 는 `resourcename`에서 개체에 대 한 <xref:System.IDisposable.Dispose%2A> 메서드를 호출 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="12205-148">이렇게 하면 개체가 리소스를 완전히 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="12205-149">`End Using` 문은 `Using` 블록의 컨트롤에 있는 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>

## <a name="behavior"></a><span data-ttu-id="12205-150">동작</span><span class="sxs-lookup"><span data-stu-id="12205-150">Behavior</span></span>

 <span data-ttu-id="12205-151">`Using` 블록은 `Try` 블록이 리소스를 사용 하 고 `Finally` 블록이 해당 리소스를 삭제 하는 `Try`...`Finally` 생성 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="12205-152">이로 인해 `Using` 블록은 블록을 종료 하는 방법에 관계 없이 리소스 삭제를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="12205-153">이는 <xref:System.StackOverflowException>를 제외 하 고 처리 되지 않은 예외의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="12205-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>

 <span data-ttu-id="12205-154">`Using` 문에서 획득 한 모든 리소스 변수의 범위는 `Using` 블록으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12205-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>

 <span data-ttu-id="12205-155">`Using` 문에서 둘 이상의 시스템 리소스를 지정 하는 경우 결과는 다른 `Using` 블록 내에 중첩 된 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>

 <span data-ttu-id="12205-156">`resourcename` `Nothing`되는 경우에는 <xref:System.IDisposable.Dispose%2A>에 대 한 호출이 수행 되지 않으며 예외가 throw 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>

## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="12205-157">Using 블록 내에서 구조적 예외 처리</span><span class="sxs-lookup"><span data-stu-id="12205-157">Structured Exception Handling Within a Using Block</span></span>

 <span data-ttu-id="12205-158">`Using` 블록 내에서 발생할 수 있는 예외를 처리 해야 하는 경우 전체 `Try`...`Finally` 생성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="12205-159">`Using` 문이 리소스를 획득 하는 데 실패 한 경우를 처리 해야 하는 경우를 테스트 하 여 `resourcename` `Nothing`있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>

## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="12205-160">Using 블록 대신 구조적 예외 처리</span><span class="sxs-lookup"><span data-stu-id="12205-160">Structured Exception Handling Instead of a Using Block</span></span>

 <span data-ttu-id="12205-161">리소스 획득을 보다 세부적으로 제어 해야 하거나 `Finally` 블록에 추가 코드가 필요한 경우 `Using` 블록을 `Try`...`Finally` 생성으로 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="12205-162">다음 예제에서는 `resource`의 획득 및 삭제에 해당 하는 기본 `Try` 및 `Using` 생성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12205-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>

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
> <span data-ttu-id="12205-163">`Using` 블록 내의 코드는 `resourcename`의 개체를 다른 변수에 할당 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12205-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="12205-164">`Using` 블록을 종료 하면 리소스가 삭제 되 고 다른 변수는 가리키는 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>

## <a name="example"></a><span data-ttu-id="12205-165">예제</span><span class="sxs-lookup"><span data-stu-id="12205-165">Example</span></span>

 <span data-ttu-id="12205-166">다음 예에서는 .log 라는 파일을 만들고 두 줄의 텍스트를 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="12205-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="12205-167">또한이 예제에서는 동일한 파일을 읽고 텍스트 줄을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="12205-167">The example also reads that same file and displays the lines of text:</span></span>

 <span data-ttu-id="12205-168"><xref:System.IO.TextWriter> 및 <xref:System.IO.TextReader> 클래스가 <xref:System.IDisposable> 인터페이스를 구현 하기 때문에 코드는 `Using` 문을 사용 하 여 쓰기 및 읽기 작업 후에 파일이 올바르게 닫 혔는 지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12205-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a><span data-ttu-id="12205-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12205-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="12205-170">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="12205-170">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="12205-171">방법: 시스템 리소스 해제</span><span class="sxs-lookup"><span data-stu-id="12205-171">How to: Dispose of a System Resource</span></span>](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
