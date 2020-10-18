---
title: 상수는 클래스, 구조체, 형식 매개 변수 또는 배열 형식이 아닌 내장 또는 열거 형식이어야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: e820287f0ddf462b30867d90501f7d730c9c6739
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163157"
---
# <a name="bc30424-constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="e181e-102">BC30424: 상수는 클래스, 구조체, 형식 매개 변수 또는 배열 형식이 아닌 내장 또는 열거 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e181e-102">BC30424: Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>

<span data-ttu-id="e181e-103">상수를 클래스, 구조체 또는 배열 형식으로 선언 하거나 포함 하는 제네릭 형식에 의해 정의 된 형식 매개 변수로 선언 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e181e-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>

 <span data-ttu-id="e181e-104">상수는 내장 형식 (,,,,,,,,,,,,, `Boolean` `Byte` `Date` `Decimal` `Double` `Integer` `Long` `Object` `SByte` `Short` `Single` `String` `UInteger` `ULong` 또는 `UShort` ) 이거나 `Enum` 정수 계열 형식 중 하나를 기반으로 하는 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e181e-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>

 <span data-ttu-id="e181e-105">**오류 ID:** BC30424</span><span class="sxs-lookup"><span data-stu-id="e181e-105">**Error ID:** BC30424</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e181e-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e181e-106">To correct this error</span></span>

1. <span data-ttu-id="e181e-107">상수를 내장 형식 또는 형식으로 선언 합니다 `Enum` .</span><span class="sxs-lookup"><span data-stu-id="e181e-107">Declare the constant as an intrinsic or `Enum` type.</span></span>

2. <span data-ttu-id="e181e-108">상수는, 또는과 같은 특수 값일 수도 있습니다 `True` `False` `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="e181e-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="e181e-109">컴파일러는 이러한 미리 정의 된 값을 적절 한 내장 형식으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="e181e-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>

## <a name="see-also"></a><span data-ttu-id="e181e-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e181e-110">See also</span></span>

- [<span data-ttu-id="e181e-111">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="e181e-111">Constants and Enumerations</span></span>](../constants-and-enumerations.md)
- [<span data-ttu-id="e181e-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e181e-112">Data Types</span></span>](../../programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="e181e-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e181e-113">Data Types</span></span>](../data-types/index.md)
