---
description: '자세히 알아보기: BC42026: 식이 포함 하는 속성을 재귀적으로 호출 합니다.<propertyname>'
title: 식이 포함하는 속성 '<propertyname>'을(를) 재귀적으로 호출합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: 4b6abcbab62ae0c4c5b18b0e6946bcfb21857112
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796342"
---
# <a name="bc42026-expression-recursively-calls-the-containing-property-propertyname"></a><span data-ttu-id="d9657-103">BC42026: 식이 포함 하는 속성 ' '을 재귀적으로 호출 합니다. \<propertyname></span><span class="sxs-lookup"><span data-stu-id="d9657-103">BC42026: Expression recursively calls the containing property '\<propertyname>'</span></span>

<span data-ttu-id="d9657-104">`Set`속성 정의 프로시저의 문은 속성 이름에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9657-104">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>

 <span data-ttu-id="d9657-105">속성의 값을 유지 하는 권장 방법은 `Private` 속성의 컨테이너에 변수를 정의 하 고 및 프로시저에서 사용 하는 것입니다 `Get` `Set` .</span><span class="sxs-lookup"><span data-stu-id="d9657-105">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="d9657-106">`Set`그런 다음이 프로시저는 들어오는 값을이 변수에 저장 해야 합니다 `Private` .</span><span class="sxs-lookup"><span data-stu-id="d9657-106">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>

 <span data-ttu-id="d9657-107">`Get`프로시저는 프로시저 처럼 동작 `Function` 하므로 문을 발생 시켜 속성 이름에 값을 할당 하 고 컨트롤을 반환할 수 있습니다 `End Get` .</span><span class="sxs-lookup"><span data-stu-id="d9657-107">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="d9657-108">그러나 권장 되는 방법은 `Private` [Return 문의](../statements/return-statement.md)값으로 변수를 포함 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9657-108">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../statements/return-statement.md).</span></span>

 <span data-ttu-id="d9657-109">`Set`프로시저는 `Sub` 값을 반환 하지 않는 프로시저 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9657-109">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="d9657-110">따라서 프로시저 또는 속성 이름에는 프로시저 내에 특별 한 의미가 없으며 `Set` 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9657-110">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>

 <span data-ttu-id="d9657-111">다음 예제에서는이 오류를 발생 시킬 수 있는 방법 및 권장 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9657-111">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>

```vb
Public Class illustrateProperties
' The code in the following property causes this error.
    Public Property badProp() As Char
        Get
            Dim charValue As Char
            ' Insert code to update charValue.
            badProp = charValue
        End Get
        Set(ByVal Value As Char)
            ' The following statement causes this error.
            badProp = Value
            ' The value stored in the local variable badProp
            ' is not used by the Get procedure in this property.
        End Set
    End Property
' The following code uses the recommended approach.
    Private propValue As Char
    Public Property goodProp() As Char
        Get
            ' Insert code to update propValue.
            Return propValue
        End Get
        Set(ByVal Value As Char)
            propValue = Value
        End Set
    End Property
End Class
```

 <span data-ttu-id="d9657-112">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="d9657-112">By default, this message is a warning.</span></span> <span data-ttu-id="d9657-113">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9657-113">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="d9657-114">**오류 ID:** BC42026</span><span class="sxs-lookup"><span data-stu-id="d9657-114">**Error ID:** BC42026</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d9657-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d9657-115">To correct this error</span></span>

- <span data-ttu-id="d9657-116">앞의 예제에서 설명한 것 처럼 권장 된 방법을 사용 하도록 속성 정의를 다시 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9657-116">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9657-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9657-117">See also</span></span>

- [<span data-ttu-id="d9657-118">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="d9657-118">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="d9657-119">Property Statement</span><span class="sxs-lookup"><span data-stu-id="d9657-119">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="d9657-120">Set 문</span><span class="sxs-lookup"><span data-stu-id="d9657-120">Set Statement</span></span>](../statements/set-statement.md)
