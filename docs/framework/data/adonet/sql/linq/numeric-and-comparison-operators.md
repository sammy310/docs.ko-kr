---
title: 숫자 및 비교 연산자
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: 7e7af725864aa191f092055fa32b403093321aa5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781290"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="a6e90-102">숫자 및 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="a6e90-102">Numeric and Comparison Operators</span></span>

<span data-ttu-id="a6e90-103">산술 및 비교 연산자는 CLR(공용 언어 런타임) 예외에서 다음과 같이 예상대로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="a6e90-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>

- <span data-ttu-id="a6e90-104">SQL에서는 부동 소수점 숫자에 대해 모듈 연산자를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6e90-104">SQL does not support the modulus operator on floating-point numbers.</span></span>

- <span data-ttu-id="a6e90-105">SQL에서는 unchecked 산술 연산을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6e90-105">SQL does not support unchecked arithmetic.</span></span>

- <span data-ttu-id="a6e90-106">증가 및 감소 연산자를 SQL에서 복제할 수 없는 식에 사용하면 예기치 않은 결과가 발생할 수 있기 때문에 두 연산자는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6e90-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>

## <a name="supported-operators"></a><span data-ttu-id="a6e90-107">지원되는 연산자</span><span class="sxs-lookup"><span data-stu-id="a6e90-107">Supported Operators</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a6e90-108">에서는 다음 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a6e90-108">supports the following operators.</span></span>

- <span data-ttu-id="a6e90-109">기본 산술 연산자:</span><span class="sxs-lookup"><span data-stu-id="a6e90-109">Basic arithmetic operators:</span></span>

  - `+`

  - <span data-ttu-id="a6e90-110">`-`(빼기)</span><span class="sxs-lookup"><span data-stu-id="a6e90-110">`-` (subtraction)</span></span>

  - `*`

  - `/`

  - <span data-ttu-id="a6e90-111">`\`(Visual Basic 정수 나누기)</span><span class="sxs-lookup"><span data-stu-id="a6e90-111">Visual Basic integer division (`\`)</span></span>

  - <span data-ttu-id="a6e90-112">`%`(Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="a6e90-112">`%` (Visual Basic `Mod`)</span></span>

  - `<<`

  - `>>`

  - <span data-ttu-id="a6e90-113">`-`(단항 부정 연산자)</span><span class="sxs-lookup"><span data-stu-id="a6e90-113">`-` (unary negation)</span></span>

- <span data-ttu-id="a6e90-114">기본 비교 연산자:</span><span class="sxs-lookup"><span data-stu-id="a6e90-114">Basic comparison operators:</span></span>

  - <span data-ttu-id="a6e90-115">Visual Basic `=` 및 C# `==`</span><span class="sxs-lookup"><span data-stu-id="a6e90-115">Visual Basic `=` and C# `==`</span></span>

  - <span data-ttu-id="a6e90-116">Visual Basic `<>` 및 C# `!=`</span><span class="sxs-lookup"><span data-stu-id="a6e90-116">Visual Basic `<>` and C# `!=`</span></span>

  - <span data-ttu-id="a6e90-117">Visual Basic `Is/IsNot`</span><span class="sxs-lookup"><span data-stu-id="a6e90-117">Visual Basic `Is/IsNot`</span></span>

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a><span data-ttu-id="a6e90-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="a6e90-118">See also</span></span>

- [<span data-ttu-id="a6e90-119">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="a6e90-119">Data Types and Functions</span></span>](data-types-and-functions.md)
- [<span data-ttu-id="a6e90-120">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="a6e90-120">C# Operators</span></span>](../../../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="a6e90-121">연산자</span><span class="sxs-lookup"><span data-stu-id="a6e90-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
