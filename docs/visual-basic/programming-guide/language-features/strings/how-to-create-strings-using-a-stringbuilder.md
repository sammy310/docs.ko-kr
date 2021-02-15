---
description: '자세히 알아보기: 방법: Visual Basic StringBuilder를 사용 하 여 문자열 만들기'
title: '방법: StringBuilder를 사용 하 여 문자열 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 6def32517f71ec3c2a7795c3395e3e572903ce1e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429821"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="12ed1-103">방법: Visual Basic StringBuilder를 사용 하 여 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="12ed1-103">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="12ed1-104">이 예제에서는 클래스를 사용 하 여 여러 개의 작은 문자열에서 긴 문자열을 생성 <xref:System.Text.StringBuilder> 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ed1-104">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="12ed1-105"><xref:System.Text.StringBuilder>클래스는 `&=` 여러 문자열을 연결 하기 위한 연산자 보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="12ed1-105">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="12ed1-106">예</span><span class="sxs-lookup"><span data-stu-id="12ed1-106">Example</span></span>

<span data-ttu-id="12ed1-107">다음 예제에서는 클래스의 인스턴스를 만들고 <xref:System.Text.StringBuilder> 해당 인스턴스에 1000 문자열을 추가한 다음 해당 문자열 표현을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ed1-107">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="12ed1-108">추가 정보</span><span class="sxs-lookup"><span data-stu-id="12ed1-108">See also</span></span>

- [<span data-ttu-id="12ed1-109">StringBuilder 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="12ed1-109">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="12ed1-110">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="12ed1-110">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="12ed1-111">문자열</span><span class="sxs-lookup"><span data-stu-id="12ed1-111">Strings</span></span>](index.md)
- [<span data-ttu-id="12ed1-112">새 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="12ed1-112">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="12ed1-113">문자열 조작</span><span class="sxs-lookup"><span data-stu-id="12ed1-113">Manipulating Strings</span></span>](../../../../standard/base-types/best-practices-strings.md)
