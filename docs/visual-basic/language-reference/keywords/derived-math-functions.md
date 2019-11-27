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
# <a name="derived-math-functions-visual-basic"></a>파생된 수학 함수(Visual Basic)
다음 표에서는 <xref:System.Math?displayProperty=nameWithType> 개체의 내장 수학 함수에서 파생 될 수 있는 비 내장 수학 함수를 보여 줍니다. 파일이 나 프로젝트에 `Imports System.Math`을 추가 하 여 내장 된 수학 함수에 액세스할 수 있습니다.  
  
|함수|파생 항목|  
|--------------|-------------------------|  
|시가 (초 (x))|1 / Cos(x)|  
|코시 컨 트 (Csc (x))|1/Sin (x)|  
|코탄젠트 (Ctan (x))|1/황갈색 (x)|  
|역 사인 (Asin (x))|Atan(x / Sqrt(-x * x + 1))|  
|역 코사인 (Acos (x))|Atan (-x/Sqrt (-x * x + 1)) + 2 \* Atan (1)|  
|역 시 컨 (Asec (x))|2 * Atan (1) – Atan (부호 (x)/Sqrt (x \* x – 1))|  
|역 코시 컨 트 (Acsc (x))|Atan(Sign(x) / Sqrt(x * x – 1))|  
|역 코탄젠트 (Acot (x))|2 * Atan(1) - Atan(x)|  
|쌍곡선 사인 (Sinh (x))|(Exp(x) – Exp(-x)) / 2|  
|쌍 곡 코사인 (x)|(Exp(x) + Exp(-x)) / 2|  
|쌍 곡 탄젠트 (Tanh (x))|(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))|  
|쌍 곡 시 컨 트 (Sech (x))|2 / (Exp(x) + Exp(-x))|  
|쌍 곡 코시 컨 트 (Csch (x))|2 / (Exp(x) – Exp(-x))|  
|쌍 곡 코탄젠트 (x)|(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))|  
|역 하이퍼볼릭 사인 (Asinh (x))|Log(x + Sqrt(x * x + 1))|  
|역 쌍 곡 코사인 (Acosh (x))|Log(x + Sqrt(x * x – 1))|  
|역 쌍 곡 탄젠트 (Atanh (x))|Log((1 + x) / (1 – x)) / 2|  
|역 쌍 곡 시 컨 트 (AsecH (x))|Log ((Sqrt (-x * x + 1) + 1)/x)|  
|역 쌍 곡 코시 컨 트 (Acsch (x))|Log ((부호 (x) * Sqrt (x \* x + 1) + 1)/x)|  
|역 하이퍼볼릭 코탄젠트 (Acoth (x))|Log ((x + 1)/(x – 1))/2|  
  
## <a name="see-also"></a>참고 항목

- [수학 함수](../../../visual-basic/language-reference/functions/math-functions.md)
