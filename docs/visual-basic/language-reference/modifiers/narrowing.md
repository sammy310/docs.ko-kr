---
title: Narrowing(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: eb5f021371291483b8eb2a13727a9fda94540638
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920642"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="1b84f-102">Narrowing(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b84f-102">Narrowing (Visual Basic)</span></span>
<span data-ttu-id="1b84f-103">나타내는 변환 연산자 (`CType`) 클래스 또는 구조체를 원래 클래스 또는 구조체의 가능한 값의 일부를 저장 하지 못할 수 있는 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84f-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="1b84f-104">축소 키워드를 사용 하 여 변환</span><span class="sxs-lookup"><span data-stu-id="1b84f-104">Converting with the Narrowing Keyword</span></span>  
 <span data-ttu-id="1b84f-105">변환 절차 지정 해야 합니다 `Public Shared` 외에 `Narrowing`합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84f-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="1b84f-106">축소 변환 수행 항상 런타임에 성공 및 실패 하거나 하 데이터 손실이 발생할 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84f-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="1b84f-107">예로 `Long` 하 `Integer`, `String` 를 `Date`, 및 파생된 형식에 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b84f-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="1b84f-108">기본 형식을 파생 된 유형의 모든 멤버를 포함 하지 않을 수 파생 형식의 인스턴스를 따라서 이기 때문에 마지막으로이 변환이 축소 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84f-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="1b84f-109">경우 `Option Strict` 은 `On`를 사용 하는 코드를 사용 해야 합니다 `CType` 모든 축소 변환에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84f-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="1b84f-110">`Narrowing` 키워드는이 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b84f-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="1b84f-111">Operator 문</span><span class="sxs-lookup"><span data-stu-id="1b84f-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1b84f-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="1b84f-112">See also</span></span>

- [<span data-ttu-id="1b84f-113">Operator 문</span><span class="sxs-lookup"><span data-stu-id="1b84f-113">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="1b84f-114">확장</span><span class="sxs-lookup"><span data-stu-id="1b84f-114">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="1b84f-115">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="1b84f-115">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="1b84f-116">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="1b84f-116">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="1b84f-117">CType 함수</span><span class="sxs-lookup"><span data-stu-id="1b84f-117">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="1b84f-118">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="1b84f-118">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
