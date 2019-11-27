---
title: Widening
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 1c9aa78549ca6e41c9fe54c12e0aaec8e7cc30cb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347840"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="306e4-102">Widening(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="306e4-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="306e4-103">변환 연산자 (`CType`)가 클래스 또는 구조체를 원래 클래스 또는 구조체의 가능한 모든 값을 보유할 수 있는 형식으로 변환 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="306e4-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="306e4-104">확대/축소 키워드를 사용 하 여 변환</span><span class="sxs-lookup"><span data-stu-id="306e4-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="306e4-105">변환 프로시저는 `Widening`외에 `Public Shared`를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="306e4-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="306e4-106">확대 변환은 런타임에 항상 성공 하며 데이터 손실이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="306e4-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="306e4-107">예제는 `Double`, `String``Char` 및 파생 된 형식을 기본 형식으로 `Single` 합니다.</span><span class="sxs-lookup"><span data-stu-id="306e4-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="306e4-108">이 마지막 변환은 파생 된 형식에 기본 형식의 모든 멤버가 포함 되어 있으므로 기본 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="306e4-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="306e4-109">`Option Strict`을 `On`경우에도 사용 하는 코드는 확대 변환에 `CType`를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="306e4-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="306e4-110">이 컨텍스트에서는 `Widening` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="306e4-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="306e4-111">Operator 문</span><span class="sxs-lookup"><span data-stu-id="306e4-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="306e4-112">확대 및 축소 변환 연산자의 정의 예제 [는 방법: 변환 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="306e4-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306e4-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="306e4-113">See also</span></span>

- [<span data-ttu-id="306e4-114">Operator 문</span><span class="sxs-lookup"><span data-stu-id="306e4-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="306e4-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="306e4-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="306e4-116">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="306e4-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="306e4-117">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="306e4-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="306e4-118">CType Function</span><span class="sxs-lookup"><span data-stu-id="306e4-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="306e4-119">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="306e4-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="306e4-120">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="306e4-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
