---
ms.openlocfilehash: e6e10b2ec451c07bf397cbdcac51ef57c29dab47
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568188"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a>Json 직렬 변환기 예외 형식을 `JsonException`에서 `NotSupportedException`으로 변경

.Net Core 3.0 미리 보기 6~8에서는 지원되지 않는 파생 컬렉션 형식이 발견되면 직렬 변환기가 <xref:System.Text.Json.JsonException>을 throw합니다. .Net Core 3.0 미리 보기 9부터 직렬 변환기가 대신 <xref:System.NotSupportedException>을 throw합니다.

#### <a name="change-description"></a>변경 내용 설명

.Net Core 3.0 미리 보기 6~8에서는 지원되지 않는 파생 컬렉션 형식이 발견되면 직렬 변환기가 <xref:System.Text.Json.JsonException>을 throw합니다. *지원되지 않는 파생 컬렉션 형식*은 다음 형식 중 하나에 할당할 수 없는 컬렉션 형식입니다.

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [IDictionary\<String,T>](xref:System.Collections.Generic.IDictionary%602)

.Net Core 3.0 미리 보기 9부터 직렬 변환기는 지원되지 않는 컬렉션 형식이 발생하면 <xref:System.NotSupportedException>을 throw합니다. 새 예외 형식이 역직렬화 작업이 실패하는 이유를 더 잘 반영합니다.

#### <a name="version-introduced"></a>도입된 버전

3.0 미리 보기 9

#### <a name="recommended-action"></a>권장 조치

역직렬화할 때 <xref:System.Text.Json.JsonException>을 확인하는 경우 <xref:System.NotSupportedException>도 확인합니다.

#### <a name="category"></a>범주

CoreFx

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
