---
description: '자세히 알아보기: 확대 (Visual Basic)'
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
ms.openlocfilehash: de290296ba2b7716ba992c6bed46443053048282
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700704"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="e8cb8-103">Widening(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8cb8-103">Widening (Visual Basic)</span></span>

<span data-ttu-id="e8cb8-104">변환 연산자 ( `CType` )가 클래스 또는 구조체를 원래 클래스 또는 구조체의 가능한 모든 값을 보유할 수 있는 형식으로 변환 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e8cb8-104">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="e8cb8-105">확대/축소 키워드를 사용 하 여 변환</span><span class="sxs-lookup"><span data-stu-id="e8cb8-105">Converting with the Widening Keyword</span></span>  

 <span data-ttu-id="e8cb8-106">변환 프로시저는 `Public Shared` 와 함께를 지정 해야 합니다 `Widening` .</span><span class="sxs-lookup"><span data-stu-id="e8cb8-106">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="e8cb8-107">확대 변환은 런타임에 항상 성공 하며 데이터 손실이 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cb8-107">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="e8cb8-108">예를 들어, `Single` `Double` 파생 된 `Char` `String` 형식을 기본 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cb8-108">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="e8cb8-109">이 마지막 변환은 파생 된 형식에 기본 형식의 모든 멤버가 포함 되어 있으므로 기본 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cb8-109">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="e8cb8-110">를 사용 하는 코드는 `CType` 가 인 경우에도 확대 변환에를 사용할 필요가 없습니다. `Option Strict` `On`</span><span class="sxs-lookup"><span data-stu-id="e8cb8-110">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="e8cb8-111">`Widening`키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cb8-111">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="e8cb8-112">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="e8cb8-112">Operator Statement</span></span>](../statements/operator-statement.md)  
  
 <span data-ttu-id="e8cb8-113">확대 및 축소 변환 연산자의 정의 예제 [는 방법: 변환 연산자 정의](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8cb8-113">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8cb8-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8cb8-114">See also</span></span>

- [<span data-ttu-id="e8cb8-115">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="e8cb8-115">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="e8cb8-116">Narrowing</span><span class="sxs-lookup"><span data-stu-id="e8cb8-116">Narrowing</span></span>](narrowing.md)
- [<span data-ttu-id="e8cb8-117">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="e8cb8-117">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="e8cb8-118">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="e8cb8-118">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="e8cb8-119">CType Function</span><span class="sxs-lookup"><span data-stu-id="e8cb8-119">CType Function</span></span>](../functions/ctype-function.md)
- [<span data-ttu-id="e8cb8-120">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="e8cb8-120">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
- [<span data-ttu-id="e8cb8-121">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="e8cb8-121">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
