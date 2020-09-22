---
title: 상수는 클래스, 구조체, 형식 매개 변수 또는 배열 형식이 아닌 내장 또는 열거 형식이어야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: a9bbf27615233f4282e481710a0234b2fa589f63
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874568"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="8e87b-102">상수는 클래스, 구조체, 형식 매개 변수 또는 배열 형식이 아닌 내장 또는 열거 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e87b-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>

<span data-ttu-id="8e87b-103">상수를 클래스, 구조체 또는 배열 형식으로 선언 하거나 포함 하는 제네릭 형식에 의해 정의 된 형식 매개 변수로 선언 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8e87b-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="8e87b-104">상수는 내장 형식 (,,,,,,,,,,,,, `Boolean` `Byte` `Date` `Decimal` `Double` `Integer` `Long` `Object` `SByte` `Short` `Single` `String` `UInteger` `ULong` 또는 `UShort` ) 이거나 `Enum` 정수 계열 형식 중 하나를 기반으로 하는 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e87b-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="8e87b-105">**오류 ID:** BC30424</span><span class="sxs-lookup"><span data-stu-id="8e87b-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8e87b-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8e87b-106">To correct this error</span></span>  
  
1. <span data-ttu-id="8e87b-107">상수를 내장 형식 또는 형식으로 선언 합니다 `Enum` .</span><span class="sxs-lookup"><span data-stu-id="8e87b-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2. <span data-ttu-id="8e87b-108">상수는, 또는과 같은 특수 값일 수도 있습니다 `True` `False` `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="8e87b-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="8e87b-109">컴파일러는 이러한 미리 정의 된 값을 적절 한 내장 형식으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e87b-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e87b-110">참조</span><span class="sxs-lookup"><span data-stu-id="8e87b-110">See also</span></span>

- [<span data-ttu-id="8e87b-111">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="8e87b-111">Constants and Enumerations</span></span>](../constants-and-enumerations.md)
- [<span data-ttu-id="8e87b-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8e87b-112">Data Types</span></span>](../../programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="8e87b-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8e87b-113">Data Types</span></span>](../data-types/index.md)
