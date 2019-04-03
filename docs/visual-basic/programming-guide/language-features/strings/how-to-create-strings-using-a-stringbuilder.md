---
title: '방법: Visual Basic에서 StringBuilder를 사용 하 여 문자열 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 00fefcc138164288d872cd339f165dc6ffc0131a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834194"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="266c8-102">방법: Visual Basic에서 StringBuilder를 사용 하 여 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="266c8-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="266c8-103">이 예제를 사용 하 여 많은 짧은 문자열에서 긴 문자열을 생성 합니다 <xref:System.Text.StringBuilder> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="266c8-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="266c8-104">합니다 <xref:System.Text.StringBuilder> 클래스 보다 더 효율적입니다는 `&=` 여러 문자열 연결 연산자.</span><span class="sxs-lookup"><span data-stu-id="266c8-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="266c8-105">예제</span><span class="sxs-lookup"><span data-stu-id="266c8-105">Example</span></span>  
 <span data-ttu-id="266c8-106">다음 예에서는 인스턴스에 <xref:System.Text.StringBuilder> 클래스는 해당 인스턴스를 1,000 문자열을 추가 하 고 다음의 문자열 표현을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="266c8-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a><span data-ttu-id="266c8-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="266c8-107">See also</span></span>

- [<span data-ttu-id="266c8-108">StringBuilder 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="266c8-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="266c8-109">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="266c8-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="266c8-110">문자열</span><span class="sxs-lookup"><span data-stu-id="266c8-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="266c8-111">새 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="266c8-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="266c8-112">문자열 조작</span><span class="sxs-lookup"><span data-stu-id="266c8-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
