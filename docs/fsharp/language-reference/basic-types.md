---
title: 기본 형식
description: 'F # 언어에서 사용 되는 기본 기본 형식을 검색 합니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 2bfc9ba9370cb8ba1fcc1d42369c2551cbb57623
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456915"
---
# <a name="basic-types"></a>기본 형식

이 항목에서는 F # 언어에 정의 된 기본 형식을 나열 합니다. 이러한 형식은 F #에서 가장 기본적인 것 이며 거의 모든 F # 프로그램의 기본을 형성 합니다. .NET 기본 형식의 상위 집합입니다.

|Type|.NET 형식|설명|예|
|----|---------|-----------|-------|
|`bool`|<xref:System.Boolean>|가능한 값은 `true` 및 `false`입니다.|`true`/`false`|
|`byte`|<xref:System.Byte>|0에서 255 사이의 값입니다.|`1uy`|
|`sbyte`|<xref:System.SByte>|값은-128에서 127 사이입니다.|`1y`|
|`int16`|<xref:System.Int16>|값은-32768에서 32767 사이입니다.|`1s`|
|`uint16`|<xref:System.UInt16>|0에서 65535 사이의 값입니다.|`1us`|
|`int`|<xref:System.Int32>|값은-2147483648에서 2147483647 사이입니다.|`1`|
|`uint`|<xref:System.UInt32>|0에서 4294967295 사이의 값입니다.|`1u`|
|`int64`|<xref:System.Int64>|-9223372036854775808에서 9223372036854775807 까지의 값입니다.|`1L`|
|`uint64`|<xref:System.UInt64>|0에서 18446744073709551615 사이의 값입니다.|`1UL`|
|`nativeint`|<xref:System.IntPtr>|부호 있는 정수에 해당 하는 네이티브 포인터입니다.|`nativeint 1`|
|`unativeint`|<xref:System.UIntPtr>|부호 없는 정수 인 네이티브 포인터입니다.|`unativeint 1`|
|`decimal`|<xref:System.Decimal>|유효 자릿수가 28 개 이상인 부동 소수점 데이터 형식입니다.|`1.0`|
|`float`, `double`|<xref:System.Double>|64 비트 부동 소수점 형식입니다.|`1.0`|
|`float32`, `single`|<xref:System.Single>|32 비트 부동 소수점 형식입니다.|`1.0f`|
|`char`|<xref:System.Char>|유니코드 문자 값입니다.|`'c'`|
|`string`|<xref:System.String>|유니코드 텍스트입니다.|`"str"`|
|`unit`|적용할 수 없음|실제 값이 없음을 나타냅니다. 형식에는로 표시 되는 하나의 형식 값만 있습니다 `()` . 단위 값은 `()` 일반적으로 값이 필요한 자리 표시자로 사용 되지만 실제 값을 사용할 수 없거나 의미가 없습니다.|`()`|

> [!NOTE]
> 형식을 사용 하 여 64 비트 정수 형식에 대해 너무 큰 정수를 사용 하 여 계산을 수행할 수 있습니다 `bigint` . `bigint` 는 기본 형식으로 간주 되지 않습니다. 의 약어입니다 `System.Numerics.BigInteger` .

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
