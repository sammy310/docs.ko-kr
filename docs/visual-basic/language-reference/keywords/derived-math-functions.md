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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801896"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="8ff3a-102">파생된 수학 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ff3a-102">Derived Math Functions (Visual Basic)</span></span>
<span data-ttu-id="8ff3a-103">다음 표에서 기본 수학 함수의에서 파생 될 수 있는 비 내장 수치 연산 함수는 <xref:System.Math?displayProperty=nameWithType> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8ff3a-103">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="8ff3a-104">기본 수학 함수를 추가 하 여 액세스할 수 있습니다 `Imports System.Math` 을 파일이 나 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="8ff3a-104">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="8ff3a-105">함수</span><span class="sxs-lookup"><span data-stu-id="8ff3a-105">Function</span></span>|<span data-ttu-id="8ff3a-106">해당 파생된 항목</span><span class="sxs-lookup"><span data-stu-id="8ff3a-106">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="8ff3a-107">시 컨 트 (Sec(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-107">Secant (Sec(x))</span></span>|<span data-ttu-id="8ff3a-108">1 / Cos(x)</span><span class="sxs-lookup"><span data-stu-id="8ff3a-108">1 / Cos(x)</span></span>|  
|<span data-ttu-id="8ff3a-109">코시 컨 트 (Csc(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-109">Cosecant (Csc(x))</span></span>|<span data-ttu-id="8ff3a-110">1 / Sin(x)</span><span class="sxs-lookup"><span data-stu-id="8ff3a-110">1 / Sin(x)</span></span>|  
|<span data-ttu-id="8ff3a-111">코탄젠트 (Ctan(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-111">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="8ff3a-112">1 / Tan(x)</span><span class="sxs-lookup"><span data-stu-id="8ff3a-112">1 / Tan(x)</span></span>|  
|<span data-ttu-id="8ff3a-113">역 사인 (Asin(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-113">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="8ff3a-114">Atan(x / Sqrt(-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-114">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="8ff3a-115">역 코사인 (Acos(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-115">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="8ff3a-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span><span class="sxs-lookup"><span data-stu-id="8ff3a-116">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="8ff3a-117">역 시 컨 트 (Asec(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-117">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="8ff3a-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-118">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="8ff3a-119">역 코시 컨 트 (Acsc(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-119">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="8ff3a-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-120">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="8ff3a-121">역 코탄젠트 (Acot(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-121">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="8ff3a-122">2 \* Atan(1) - Atan(x)</span><span class="sxs-lookup"><span data-stu-id="8ff3a-122">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="8ff3a-123">쌍 곡 사인 (Sinh(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-123">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="8ff3a-124">(Exp(x) – Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="8ff3a-124">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="8ff3a-125">쌍 곡 코사인 (Cosh(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-125">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="8ff3a-126">(Exp(x) + Exp(-x)) / 2</span><span class="sxs-lookup"><span data-stu-id="8ff3a-126">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="8ff3a-127">Hyperbolic tangent (Tanh(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-127">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="8ff3a-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-128">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="8ff3a-129">쌍 곡 시 컨 트 (Sech(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-129">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="8ff3a-130">2 / (Exp(x) + Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-130">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="8ff3a-131">Hyperbolic cosecant (Csch(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-131">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="8ff3a-132">2 / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-132">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="8ff3a-133">Hyperbolic cotangent (Coth(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-133">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="8ff3a-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-134">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="8ff3a-135">역 쌍 곡 사인 (Asinh(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-135">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="8ff3a-136">Log(x + Sqrt(x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-136">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="8ff3a-137">역 쌍 곡 코사인 (Acosh(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-137">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="8ff3a-138">Log(x + Sqrt(x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-138">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="8ff3a-139">역 쌍 곡 탄젠트 (Atanh(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-139">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="8ff3a-140">Log((1 + x) / (1 – x)) / 2</span><span class="sxs-lookup"><span data-stu-id="8ff3a-140">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="8ff3a-141">역 쌍 곡 시 컨 트 (AsecH(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-141">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="8ff3a-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="8ff3a-142">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="8ff3a-143">역 쌍 곡 코시 컨 트 (Acsch(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-143">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="8ff3a-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span><span class="sxs-lookup"><span data-stu-id="8ff3a-144">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="8ff3a-145">역 쌍 곡 코탄젠트 (Acoth(x))</span><span class="sxs-lookup"><span data-stu-id="8ff3a-145">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="8ff3a-146">로그 ((x + 1) / (x-1)) / 2</span><span class="sxs-lookup"><span data-stu-id="8ff3a-146">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ff3a-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="8ff3a-147">See also</span></span>

- [<span data-ttu-id="8ff3a-148">수학 함수</span><span class="sxs-lookup"><span data-stu-id="8ff3a-148">Math Functions</span></span>](../../../visual-basic/language-reference/functions/math-functions.md)
