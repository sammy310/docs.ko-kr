---
title: 파생된 수학 함수(Visual Basic)
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
ms.openlocfilehash: 0d0606c52d1d50fcc2fd8eea3ad2851c95b18a69
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836586"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="9a5e8-102">파생된 수학 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a5e8-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="9a5e8-103">다음 표에서 기본 수학 함수의에서 파생 될 수 있는 비 내장 수치 연산 함수는 <xref:System.Math?displayProperty=nameWithType> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5e8-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="9a5e8-104">기본 수학 함수를 추가 하 여 액세스할 수 있습니다 `Imports System.Math` 을 파일이 나 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="9a5e8-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="9a5e8-105">함수</span><span class="sxs-lookup"><span data-stu-id="9a5e8-105">Function</span></span>|<span data-ttu-id="9a5e8-106">해당 파생된 항목</span><span class="sxs-lookup"><span data-stu-id="9a5e8-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="9a5e8-107">시 컨 트 (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-107">Secant (Sec(x))</span></span>|<span data-ttu-id="9a5e8-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="9a5e8-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="9a5e8-109">코시 컨 트 (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="9a5e8-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="9a5e8-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="9a5e8-111">코탄젠트 (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="9a5e8-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="9a5e8-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="9a5e8-113">역 사인 (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="9a5e8-114">Atan(x / Sqrt(-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="9a5e8-115">역 코사인 (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="9a5e8-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="9a5e8-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="9a5e8-117">역 시 컨 트 (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="9a5e8-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="9a5e8-119">역 코시 컨 트 (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="9a5e8-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="9a5e8-121">역 코탄젠트 (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="9a5e8-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="9a5e8-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="9a5e8-123">쌍 곡 사인 (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="9a5e8-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="9a5e8-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="9a5e8-125">쌍 곡 코사인 (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="9a5e8-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="9a5e8-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="9a5e8-127">Hyperbolic tangent (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="9a5e8-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="9a5e8-129">쌍 곡 시 컨 트 (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="9a5e8-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="9a5e8-131">Hyperbolic cosecant (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="9a5e8-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="9a5e8-133">Hyperbolic cotangent (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="9a5e8-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="9a5e8-135">역 쌍 곡 사인 (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="9a5e8-136">Log(x + Sqrt(x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="9a5e8-137">역 쌍 곡 코사인 (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="9a5e8-138">Log(x + Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="9a5e8-139">역 쌍 곡 탄젠트 (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="9a5e8-140">Log((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="9a5e8-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="9a5e8-141">역 쌍 곡 시 컨 트 (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="9a5e8-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="9a5e8-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="9a5e8-143">역 쌍 곡 코시 컨 트 (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="9a5e8-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="9a5e8-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="9a5e8-145">역 쌍 곡 코탄젠트 (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="9a5e8-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="9a5e8-146">로그 ((x + 1) / (x-1)) / 2</span><span class="sxs-lookup"><span data-stu-id="9a5e8-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a5e8-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="9a5e8-147">See also</span></span>

- [<span data-ttu-id="9a5e8-148">수학 함수</span><span class="sxs-lookup"><span data-stu-id="9a5e8-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
