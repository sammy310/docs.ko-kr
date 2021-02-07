---
description: 다음에 대해 자세히 알아보세요. Convert 메서드
title: System.Convert 메서드
ms.date: 03/30/2017
ms.assetid: 3ca6c5b6-ea5d-4ab0-b675-f082135b342c
ms.openlocfilehash: a323f8d0c3c4a8d1248409d2ec27565acdc58222
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681411"
---
# <a name="systemconvert-methods"></a>System.Convert 메서드

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 다음 <xref:System.Convert> 메서드를 지원하지 않습니다.

- <xref:System.IFormatProvider> 매개 변수를 사용하는 버전

- 문자 배열 또는 바이트 배열과 관련된 메서드

  - <xref:System.Convert.FromBase64CharArray%2A>

  - <xref:System.Convert.ToBase64CharArray%2A>

  - <xref:System.Convert.FromBase64String%2A>

  - <xref:System.Convert.ToBase64String%2A>

- 다음과 같은 메서드

  - `public static <Type2> To<Type2>(<Type1> value);` 여기서 각 값은 다음과 같습니다.

    여기서 `Type1` 및 `Type2`은(는) 각각 `sbyte`, `uint`, `ulong` 또는 `ushort` 중 하나입니다.

  - C#:

    `int To<int type>(string value, int fromBase),`

    `ToString(... value, int toBase)`

  - Visual Basic:

    `Function To(Of [Numeric])(value as String, fromBase As Integer)`

    `As [Numeric], ToString( value As …, toBase As Integer)`

  - <xref:System.Convert.IsDBNull%2A>

  - <xref:System.Convert.GetTypeCode%2A>

  - <xref:System.Convert.ChangeType%2A>

## <a name="see-also"></a>참고 항목

- [데이터 형식 및 함수](data-types-and-functions.md)
