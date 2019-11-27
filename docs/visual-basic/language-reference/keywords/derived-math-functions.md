---
title: 파생된 수학 함수
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operations, derived math functions
- cosecant function
- arcsecant function
- arccotangent function
- functions [Visual Basic], derived math functions
- inverse functions
- math functions, derived
- derived math functions
- cotangent function
- angles
- secant function
- trigonometric functions
- logarithms
- arccosecant function
- hyperbolic functions
- arcsine function
- degrees
- arccosine function
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
ms.openlocfilehash: 73cf56dd72f2baac0474d6f5c4e88228a1fe38cf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349846"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="83bd8-102">파생된 수학 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83bd8-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="83bd8-103">다음 표에서는 <xref:System.Math?displayProperty=nameWithType> 개체의 내장 수학 함수에서 파생 될 수 있는 비 내장 수학 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83bd8-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="83bd8-104">파일이 나 프로젝트에 `Imports System.Math`을 추가 하 여 내장 된 수학 함수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83bd8-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="83bd8-105">함수</span><span class="sxs-lookup"><span data-stu-id="83bd8-105">Function</span></span>|<span data-ttu-id="83bd8-106">파생 항목</span><span class="sxs-lookup"><span data-stu-id="83bd8-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="83bd8-107">시가 (초 (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-107">Secant (Sec(x))</span></span>|<span data-ttu-id="83bd8-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="83bd8-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="83bd8-109">코시 컨 트 (Csc (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="83bd8-110">1/Sin (x)</span><span class="sxs-lookup"><span data-stu-id="83bd8-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="83bd8-111">코탄젠트 (Ctan (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="83bd8-112">1/황갈색 (x)</span><span class="sxs-lookup"><span data-stu-id="83bd8-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="83bd8-113">역 사인 (Asin (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="83bd8-114">Atan(x / Sqrt(-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="83bd8-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="83bd8-115">역 코사인 (Acos (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="83bd8-116">Atan (-x/Sqrt (-x \* x + 1)) + 2 \* Atan (1)</span><span class="sxs-lookup"><span data-stu-id="83bd8-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="83bd8-117">역 시 컨 (Asec (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="83bd8-118">2 \* Atan (1) – Atan (부호 (x)/Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="83bd8-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="83bd8-119">역 코시 컨 트 (Acsc (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="83bd8-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="83bd8-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="83bd8-121">역 코탄젠트 (Acot (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="83bd8-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="83bd8-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="83bd8-123">쌍곡선 사인 (Sinh (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="83bd8-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="83bd8-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="83bd8-125">쌍 곡 코사인 (x)</span><span class="sxs-lookup"><span data-stu-id="83bd8-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="83bd8-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="83bd8-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="83bd8-127">쌍 곡 탄젠트 (Tanh (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="83bd8-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="83bd8-129">쌍 곡 시 컨 트 (Sech (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="83bd8-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="83bd8-131">쌍 곡 코시 컨 트 (Csch (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="83bd8-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="83bd8-133">쌍 곡 코탄젠트 (x)</span><span class="sxs-lookup"><span data-stu-id="83bd8-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="83bd8-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="83bd8-135">역 하이퍼볼릭 사인 (Asinh (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="83bd8-136">Log(x + Sqrt(x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="83bd8-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="83bd8-137">역 쌍 곡 코사인 (Acosh (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="83bd8-138">Log(x + Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="83bd8-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="83bd8-139">역 쌍 곡 탄젠트 (Atanh (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="83bd8-140">Log((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="83bd8-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="83bd8-141">역 쌍 곡 시 컨 트 (AsecH (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="83bd8-142">Log ((Sqrt (-x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="83bd8-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="83bd8-143">역 쌍 곡 코시 컨 트 (Acsch (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="83bd8-144">Log ((부호 (x) \* Sqrt (x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="83bd8-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="83bd8-145">역 하이퍼볼릭 코탄젠트 (Acoth (x))</span><span class="sxs-lookup"><span data-stu-id="83bd8-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="83bd8-146">Log ((x + 1)/(x – 1))/2</span><span class="sxs-lookup"><span data-stu-id="83bd8-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83bd8-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83bd8-147">See also</span></span>

- [<span data-ttu-id="83bd8-148">수학 함수</span><span class="sxs-lookup"><span data-stu-id="83bd8-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
