---
description: '자세한 정보: 파생 된 수학 함수 (Visual Basic)'
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
ms.openlocfilehash: daaed1312f08cecc0c68af0e36d574424fc526a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730774"
---
# <a name="derived-math-functions-visual-basic"></a><span data-ttu-id="1374f-103">파생 된 수학 함수 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1374f-103">Derived Math Functions (Visual Basic)</span></span>

<span data-ttu-id="1374f-104">다음 표에서는 개체의 내장 수학 함수에서 파생 될 수 있는 비 내장 수학 함수를 보여 줍니다 <xref:System.Math?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1374f-104">The following table shows non-intrinsic math functions that can be derived from the intrinsic math functions of the <xref:System.Math?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="1374f-105">파일이 나 프로젝트에을 추가 하 여 내장 수학 함수에 액세스할 수 있습니다 `Imports System.Math` .</span><span class="sxs-lookup"><span data-stu-id="1374f-105">You can access the intrinsic math functions by adding `Imports System.Math` to your file or project.</span></span>  
  
|<span data-ttu-id="1374f-106">함수</span><span class="sxs-lookup"><span data-stu-id="1374f-106">Function</span></span>|<span data-ttu-id="1374f-107">파생 항목</span><span class="sxs-lookup"><span data-stu-id="1374f-107">Derived equivalents</span></span>|  
|--------------|-------------------------|  
|<span data-ttu-id="1374f-108">시가 (초 (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-108">Secant (Sec(x))</span></span>|<span data-ttu-id="1374f-109">1/Cos (x)</span><span class="sxs-lookup"><span data-stu-id="1374f-109">1 / Cos(x)</span></span>|  
|<span data-ttu-id="1374f-110">코시 컨 트 (Csc (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-110">Cosecant (Csc(x))</span></span>|<span data-ttu-id="1374f-111">1/Sin (x)</span><span class="sxs-lookup"><span data-stu-id="1374f-111">1 / Sin(x)</span></span>|  
|<span data-ttu-id="1374f-112">코탄젠트 (Ctan (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-112">Cotangent (Ctan(x))</span></span>|<span data-ttu-id="1374f-113">1/황갈색 (x)</span><span class="sxs-lookup"><span data-stu-id="1374f-113">1 / Tan(x)</span></span>|  
|<span data-ttu-id="1374f-114">역 사인 (Asin (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-114">Inverse sine (Asin(x))</span></span>|<span data-ttu-id="1374f-115">Atan (x/Sqrt (-x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="1374f-115">Atan(x / Sqrt(-x \* x + 1))</span></span>|  
|<span data-ttu-id="1374f-116">역 코사인 (Acos (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-116">Inverse cosine (Acos(x))</span></span>|<span data-ttu-id="1374f-117">Atan (-x/Sqrt (-x \* x + 1)) + 2 \* Atan (1)</span><span class="sxs-lookup"><span data-stu-id="1374f-117">Atan(-x / Sqrt(-x \* x + 1)) + 2 \* Atan(1)</span></span>|  
|<span data-ttu-id="1374f-118">역 시 컨 (Asec (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-118">Inverse secant (Asec(x))</span></span>|<span data-ttu-id="1374f-119">2 \* Atan (1) – Atan (부호 (x)/Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="1374f-119">2 \* Atan(1) – Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="1374f-120">역 코시 컨 트 (Acsc (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-120">Inverse cosecant (Acsc(x))</span></span>|<span data-ttu-id="1374f-121">Atan (부호 (x)/Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="1374f-121">Atan(Sign(x) / Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="1374f-122">역 코탄젠트 (Acot (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-122">Inverse cotangent (Acot(x))</span></span>|<span data-ttu-id="1374f-123">2 \* Atan (1)-Atan (x)</span><span class="sxs-lookup"><span data-stu-id="1374f-123">2 \* Atan(1) - Atan(x)</span></span>|  
|<span data-ttu-id="1374f-124">쌍곡선 사인 (Sinh (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-124">Hyperbolic sine (Sinh(x))</span></span>|<span data-ttu-id="1374f-125">(Exp (x) – Exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="1374f-125">(Exp(x) – Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="1374f-126">쌍 곡 코사인 (x)</span><span class="sxs-lookup"><span data-stu-id="1374f-126">Hyperbolic cosine (Cosh(x))</span></span>|<span data-ttu-id="1374f-127">(Exp (x) + Exp (-x))/2</span><span class="sxs-lookup"><span data-stu-id="1374f-127">(Exp(x) + Exp(-x)) / 2</span></span>|  
|<span data-ttu-id="1374f-128">쌍 곡 탄젠트 (Tanh (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-128">Hyperbolic tangent (Tanh(x))</span></span>|<span data-ttu-id="1374f-129">(Exp (x) – Exp (-x))/(Exp (x) + Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="1374f-129">(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="1374f-130">쌍 곡 시 컨 트 (Sech (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-130">Hyperbolic secant (Sech(x))</span></span>|<span data-ttu-id="1374f-131">2/(exp (x) + Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="1374f-131">2 / (Exp(x) + Exp(-x))</span></span>|  
|<span data-ttu-id="1374f-132">쌍 곡 코시 컨 트 (Csch (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-132">Hyperbolic cosecant (Csch(x))</span></span>|<span data-ttu-id="1374f-133">2/(exp (x)-Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="1374f-133">2 / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="1374f-134">쌍 곡 코탄젠트 (x)</span><span class="sxs-lookup"><span data-stu-id="1374f-134">Hyperbolic cotangent (Coth(x))</span></span>|<span data-ttu-id="1374f-135">(Exp (x) + Exp (-x))/(Exp (x) – Exp (-x))</span><span class="sxs-lookup"><span data-stu-id="1374f-135">(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))</span></span>|  
|<span data-ttu-id="1374f-136">역 하이퍼볼릭 사인 (Asinh (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-136">Inverse hyperbolic sine (Asinh(x))</span></span>|<span data-ttu-id="1374f-137">Log (x + Sqrt (x \* x + 1))</span><span class="sxs-lookup"><span data-stu-id="1374f-137">Log(x + Sqrt(x \* x + 1))</span></span>|  
|<span data-ttu-id="1374f-138">역 쌍 곡 코사인 (Acosh (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-138">Inverse hyperbolic cosine (Acosh(x))</span></span>|<span data-ttu-id="1374f-139">Log (x + Sqrt (x \* x – 1))</span><span class="sxs-lookup"><span data-stu-id="1374f-139">Log(x + Sqrt(x \* x – 1))</span></span>|  
|<span data-ttu-id="1374f-140">역 쌍 곡 탄젠트 (Atanh (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-140">Inverse hyperbolic tangent (Atanh(x))</span></span>|<span data-ttu-id="1374f-141">Log ((1 + x)/(1 – x))/2</span><span class="sxs-lookup"><span data-stu-id="1374f-141">Log((1 + x) / (1 – x)) / 2</span></span>|  
|<span data-ttu-id="1374f-142">역 쌍 곡 시 컨 트 (AsecH (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-142">Inverse hyperbolic secant (AsecH(x))</span></span>|<span data-ttu-id="1374f-143">Log ((Sqrt (-x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="1374f-143">Log((Sqrt(-x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="1374f-144">역 쌍 곡 코시 컨 트 (Acsch (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-144">Inverse hyperbolic cosecant (Acsch(x))</span></span>|<span data-ttu-id="1374f-145">Log ((부호 (x) \* Sqrt (x \* x + 1) + 1)/x)</span><span class="sxs-lookup"><span data-stu-id="1374f-145">Log((Sign(x) \* Sqrt(x \* x + 1) + 1) / x)</span></span>|  
|<span data-ttu-id="1374f-146">역 하이퍼볼릭 코탄젠트 (Acoth (x))</span><span class="sxs-lookup"><span data-stu-id="1374f-146">Inverse hyperbolic cotangent (Acoth(x))</span></span>|<span data-ttu-id="1374f-147">Log ((x + 1)/(x – 1))/2</span><span class="sxs-lookup"><span data-stu-id="1374f-147">Log((x + 1) / (x – 1)) / 2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1374f-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1374f-148">See also</span></span>

- [<span data-ttu-id="1374f-149">수학 함수</span><span class="sxs-lookup"><span data-stu-id="1374f-149">Math Functions</span></span>](../functions/math-functions.md)
