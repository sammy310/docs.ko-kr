---
title: 식이 포함하는 속성 '<propertyname>'을(를) 재귀적으로 호출합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: a758d05cca5ca71943b0ef08184aef5b2c457739
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836846"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a><span data-ttu-id="3eccd-102">식이 재귀적으로 호출을 포함 하는 속성 '\<propertyname >'</span><span class="sxs-lookup"><span data-stu-id="3eccd-102">Expression recursively calls the containing property '\<propertyname>'</span></span>
<span data-ttu-id="3eccd-103">문과 `Set` 프로시저 속성 정의의 값을 속성의 이름에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eccd-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="3eccd-104">정의 하는 속성의 값을 보관 하는 것이 좋습니다는 `Private` 속성의 컨테이너에 변수 둘 다에서 사용 하는 `Get` 및 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="3eccd-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="3eccd-105">합니다 `Set` 프로시저는이 들어오는 값을 저장 한 다음 `Private` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3eccd-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="3eccd-106">합니다 `Get` 프로시저 처럼 동작을 `Function` 프로시저, 속성 이름에 값을 할당 하 고 발생 하 여 컨트롤을 반환할 수 있도록는 `End Get` 문.</span><span class="sxs-lookup"><span data-stu-id="3eccd-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="3eccd-107">하지만 포함 것이 좋습니다, 합니다 `Private` 의 값으로 변수를 [Return 문이](../../../visual-basic/language-reference/statements/return-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3eccd-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="3eccd-108">`Set` 프로시저 처럼를 `Sub` 프로시저에 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3eccd-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="3eccd-109">따라서 프로시저 또는 속성 이름을 특별 한 의미가 없으며 내는 `Set` 프로시저에 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3eccd-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="3eccd-110">다음 예에서는 권장 되는 방법은 뒤에이 오류를 일으킬 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3eccd-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
```  
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
  
 <span data-ttu-id="3eccd-111">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="3eccd-111">By default, this message is a warning.</span></span> <span data-ttu-id="3eccd-112">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3eccd-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="3eccd-113">**오류 ID:** BC42026</span><span class="sxs-lookup"><span data-stu-id="3eccd-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3eccd-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3eccd-114">To correct this error</span></span>  
  
-   <span data-ttu-id="3eccd-115">앞의 예제와 같이 권장된 접근 방식을 사용 하 여 속성 정의 다시 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eccd-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eccd-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="3eccd-116">See also</span></span>

- [<span data-ttu-id="3eccd-117">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="3eccd-117">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="3eccd-118">Property 문</span><span class="sxs-lookup"><span data-stu-id="3eccd-118">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="3eccd-119">Set 문</span><span class="sxs-lookup"><span data-stu-id="3eccd-119">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
