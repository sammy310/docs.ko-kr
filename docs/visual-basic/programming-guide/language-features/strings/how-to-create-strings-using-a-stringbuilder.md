---
title: '방법: 문자열 빌더를 사용 하 여 문자열을 만듭니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: c41db584df83782dab99b90043045aa2cabcb6ff
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645334"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="558c4-102">방법: Visual Basic에서 StringBuilder를 사용하여 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="558c4-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="558c4-103">이 예제는 클래스를 사용하는 많은 작은 <xref:System.Text.StringBuilder> 문자열에서 긴 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="558c4-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="558c4-104">클래스는 <xref:System.Text.StringBuilder> 많은 문자열을 `&=` 연결하기 위한 연산자보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="558c4-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="558c4-105">예제</span><span class="sxs-lookup"><span data-stu-id="558c4-105">Example</span></span>

<span data-ttu-id="558c4-106">다음 예제에서는 <xref:System.Text.StringBuilder> 클래스의 인스턴스를 만들고 해당 인스턴스에 1,000개의 문자열을 추가한 다음 문자열 표현을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="558c4-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="558c4-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="558c4-107">See also</span></span>

- [<span data-ttu-id="558c4-108">StringBuilder 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="558c4-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="558c4-109">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="558c4-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="558c4-110">문자열</span><span class="sxs-lookup"><span data-stu-id="558c4-110">Strings</span></span>](index.md)
- [<span data-ttu-id="558c4-111">새 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="558c4-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="558c4-112">문자열 조작</span><span class="sxs-lookup"><span data-stu-id="558c4-112">Manipulating Strings</span></span>](../../../../standard/base-types/best-practices-strings.md)
