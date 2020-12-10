---
title: System.Text.Json을 사용하여 참조를 보존하는 방법
description: .NET에서 JSON으로 직렬화하고 JSON에서 역직렬화할 때 참조를 보존하고 순환 참조를 처리하는 방법을 알아봅니다.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 9254ca261c7d748c04c311fa56359014f752ff31
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439836"
---
# <a name="how-to-handle-circular-references-with-no-locsystemtextjson"></a>System.Text.Json을 사용하여 순환 참조를 처리하는 방법

이 문서에서는 `System.Text.Json` 네임스페이스를 사용하여 순환 참조를 처리하는 방법을 알아봅니다.

## <a name="preserve-references-and-handle-circular-references"></a>참조를 보존하고 순환 참조를 처리

::: zone pivot="dotnet-5-0"

참조를 보존하고 순환 참조를 처리하려면 <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A>를 <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>로 설정합니다. 이렇게 설정하면 다음과 같은 동작이 발생합니다.

* 직렬화 시:

  복합 형식을 쓸 때 직렬 변환기는 메타데이터 속성(`$id`, `$values`, `$ref`)도 씁니다.

* 역직렬화 시:

  메타데이터가 필요하며(필수는 아님), 역직렬 변환기는 이해를 시도합니다.

다음 코드는 `Preserve` 설정을 사용하는 방법을 보여 줍니다.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

이 기능은 값 형식 또는 변경 불가능한 형식을 유지하는 데 사용할 수 없습니다. 역직렬화 시 변경 불가능한 형식의 인스턴스는 전체 페이로드를 읽은 후에 생성됩니다. 따라서 JSON 페이로드 내에 해당 참조가 표시되는 경우 동일한 인스턴스를 역직렬화할 수 없습니다.

값 형식, 변경 불가능한 형식, 배열의 경우 참조 메타데이터가 직렬화되지 않습니다. 역직렬화 시 `$ref` 또는 `$id`가 발견되면 예외가 throw됩니다. 하지만 Newtonsoft.Json을 사용하여 직렬화된 페이로드를 역직렬화할 수 있도록 값 형식은 `$id`(및 컬렉션의 경우에는 `$values`)를 무시합니다.  Newtonsoft.Json은 이러한 형식의 메타데이터를 직렬화합니다.

개체가 같은지 확인하기 위해 System.Text.Json은 두 개체 인스턴스를 비교할 때 값 같음(<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>) 대신 참조 같음(<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>)을 사용하는 <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>을 사용합니다.

참조가 직렬화 및 역직렬화되는 방법에 대한 자세한 내용은 <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>을 참조하세요.

<xref:System.Text.Json.Serialization.ReferenceResolver> 클래스는 직렬화 및 역직렬화 시 참조를 보존하는 동작을 정의합니다. 파생 클래스를 만들어 사용자 지정 동작을 지정합니다. 예제는 [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs)를 참조하세요.

::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1의 System.Text.Json은 값을 사용하는 직렬화만 지원하며 순환 참조에 대한 예외를 throw합니다.
::: zone-end

## <a name="see-also"></a>참고 항목

* [System.Text.Json 개요](system-text-json-overview.md)
* [JsonSerializerOptions 인스턴스화](system-text-json-configure-options.md)
* [대/소문자를 구분하지 않는 일치를 사용하도록 설정](system-text-json-character-casing.md)
* [속성 이름 및 값 사용자 지정](system-text-json-customize-properties.md)
* [속성 무시](system-text-json-ignore-properties.md)
* [잘못된 JSON 허용](system-text-json-invalid-json.md)
* [오버플로 JSON 처리](system-text-json-handle-overflow.md)
* [변경할 수 없는 형식 및 public이 아닌 접근자](system-text-json-immutability.md)
* [다형 직렬화](system-text-json-polymorphism.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
