---
title: 정수 데이터 형식 표 - C# 참조
ms.custom: seodec18
description: 기본 제공 C# 정수 계열 형식 개요
ms.date: 08/20/2018
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
ms.assetid: 62e86126-46ff-40b0-9028-e61d7558268c
ms.openlocfilehash: b4a3a46ba98c0c621b747284ce39e03d68a5b62d
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421726"
---
# <a name="integral-types-table-c-reference"></a>정수 계열 형식 표(C# 참조)

다음 표에서는 단순 형식의 하위 집합을 구성하는 정수 형식의 크기와 범위를 보여 줍니다.  
  
|형식|범위|크기|  
|----------|-----------|----------|  
|[sbyte](sbyte.md)|-128 ~ 127|부호 있는 8비트 정수|  
|[byte](byte.md)|0 ~ 255|부호 없는 8비트 정수|  
|[char](char.md)|U+0000 ~ U+ffff|유니코드 16비트 문자|  
|[short](short.md)|–32,768 ~ 32,767|부호 있는 16비트 정수|  
|[ushort](ushort.md)|0 ~ 65,535|부호 없는 16비트 정수|  
|[int](int.md)|–2,147,483,648 ~ 2,147,483,647|부호 있는 32비트 정수|  
|[uint](uint.md)|0 ~ 4,294,967,295|부호 없는 32비트 정수|  
|[long](long.md)|–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807|부호 있는 64비트 정수|  
|[ulong](ulong.md)|0 ~ 18,446,744,073,709,551,615|부호 없는 64비트 정수|  

## <a name="remarks"></a>주의
  
정수 리터럴로 표시되는 값이 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>를 초과하면 컴파일 오류 [CS1021](../../misc/cs1021.md)이 발생합니다.

<xref:System.Numerics.BigInteger?displayProperty=nameWithType> 구조체를 사용하여 부호 있는 임의의 큰 정수를 나타냅니다.
  
## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
- [부동 소수점 형식 표](floating-point-types-table.md)
- [기본값 표](default-values-table.md)
- [숫자 결과 형식 지정 표](formatting-numeric-results-table.md)
- [기본 제공 형식 표](built-in-types-table.md)
- [.NET의 숫자](../../../standard/numerics.md)
