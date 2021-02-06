---
description: "자세히 알아보기: BC42110: ' ' 변수의 형식은 <variablename> 바깥쪽 범위의 필드에 바인딩되어 있으므로 유추 되지 않습니다."
title: "'<variablename>' 변수가 바깥쪽 범위의 필드에 바인딩되어 있으므로 변수의 형식을 유추할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: db31f1a6e87a2fd133f095e2fbdde7bc6bded97e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641241"
---
# <a name="bc42110-the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="aa205-103">BC42110: ' ' 변수의 형식은 \<variablename> 바깥쪽 범위의 필드에 바인딩되어 있으므로 유추 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa205-103">BC42110: The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope</span></span>

<span data-ttu-id="aa205-104">' ' 변수의 형식은 \<variablename> 바깥쪽 범위의 필드에 바인딩되므로 유추 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa205-104">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="aa205-105">' '의 이름을 변경 \<variablename> 하거나 정규화 된 이름 (예: ' variablename ' 또는 ' variablename ')을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa205-105">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>

<span data-ttu-id="aa205-106">코드의 루프 제어 변수 이름이 클래스 또는 다른 바깥쪽 범위의 필드와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa205-106">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="aa205-107">제어 변수는 절 없이 사용 되므로 `As` 바깥쪽 범위의 필드에 바인딩되고 컴파일러는 새 변수를 만들거나 해당 유형을 유추 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa205-107">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>

<span data-ttu-id="aa205-108">다음 예제에서 `Index` 문의 제어 변수는 `For` `Index` 클래스의 필드에 바인딩됩니다 `Customer` .</span><span class="sxs-lookup"><span data-stu-id="aa205-108">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="aa205-109">컴파일러는 컨트롤 변수에 대 한 새 변수를 만들거나 `Index` 해당 형식을 유추 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa205-109">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

    ' The following line will raise this warning.
        For Index = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

<span data-ttu-id="aa205-110">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="aa205-110">By default, this message is a warning.</span></span> <span data-ttu-id="aa205-111">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa205-111">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="aa205-112">**오류 ID:** BC42110</span><span class="sxs-lookup"><span data-stu-id="aa205-112">**Error ID:** BC42110</span></span>

## <a name="to-address-this-warning"></a><span data-ttu-id="aa205-113">이 경고를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="aa205-113">To address this warning</span></span>

- <span data-ttu-id="aa205-114">해당 이름을 클래스의 필드 이름이 아닌 식별자로 변경 하 여 루프 제어 변수를 로컬으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aa205-114">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>

  ```vb
  For I = 1 To 10
  ```

- <span data-ttu-id="aa205-115">변수 이름에 접두사로 loop 제어 변수가 클래스 필드에 바인딩되도록 명시 합니다 `Me.` .</span><span class="sxs-lookup"><span data-stu-id="aa205-115">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>

  ```vb
  For Me.Index = 1 To 10
  ```

- <span data-ttu-id="aa205-116">지역 형식 유추를 사용 하는 대신 절을 사용 `As` 하 여 루프 제어 변수의 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa205-116">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a><span data-ttu-id="aa205-117">예제</span><span class="sxs-lookup"><span data-stu-id="aa205-117">Example</span></span>

 <span data-ttu-id="aa205-118">다음 코드에서는 첫 번째 수정이 적용 된 이전 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa205-118">The following code shows the earlier example with the first correction in place.</span></span>

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

        For I = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="aa205-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa205-119">See also</span></span>

- [<span data-ttu-id="aa205-120">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="aa205-120">Option Infer Statement</span></span>](../statements/option-infer-statement.md)
- [<span data-ttu-id="aa205-121">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="aa205-121">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="aa205-122">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="aa205-122">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="aa205-123">방법: 개체의 현재 인스턴스 참조</span><span class="sxs-lookup"><span data-stu-id="aa205-123">How to: Refer to the Current Instance of an Object</span></span>](../../programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="aa205-124">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="aa205-124">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="aa205-125">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="aa205-125">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
