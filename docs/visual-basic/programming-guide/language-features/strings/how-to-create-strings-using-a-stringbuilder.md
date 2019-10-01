---
title: '방법: Visual Basic StringBuilder를 사용 하 여 문자열 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 19e036abc9d25ec7fdfd6c33ebb420ec4f503cbc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700101"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="d4231-102">방법: Visual Basic StringBuilder를 사용 하 여 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="d4231-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="d4231-103">이 예제에서는 <xref:System.Text.StringBuilder> 클래스를 사용 하 여 여러 개의 작은 문자열에서 긴 문자열을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4231-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="d4231-104">@No__t-0 클래스는 여러 문자열을 연결 하는 `&=` 연산자 보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="d4231-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="d4231-105">예제</span><span class="sxs-lookup"><span data-stu-id="d4231-105">Example</span></span>

<span data-ttu-id="d4231-106">다음 예에서는 <xref:System.Text.StringBuilder> 클래스의 인스턴스를 만들고 해당 인스턴스에 1000 문자열을 추가한 다음 해당 문자열 표현을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4231-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="d4231-107">참조</span><span class="sxs-lookup"><span data-stu-id="d4231-107">See also</span></span>

- [<span data-ttu-id="d4231-108">StringBuilder 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="d4231-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="d4231-109">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="d4231-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="d4231-110">문자열</span><span class="sxs-lookup"><span data-stu-id="d4231-110">Strings</span></span>](index.md)
- [<span data-ttu-id="d4231-111">새 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="d4231-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="d4231-112">문자열 조작</span><span class="sxs-lookup"><span data-stu-id="d4231-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
