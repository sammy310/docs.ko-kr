---
title: System.Text.Json에서 변경 불가능한 형식 및 public이 아닌 접근자를 사용하는 방법
description: .NET에서 JSON으로 직렬화하고 JSON에서 역직렬화할 때 변경 불가능한 형식 및 public이 아닌 접근자를 사용하는 방법을 알아봅니다.
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
ms.openlocfilehash: ff8ecec0d70c877b7cbbd0297b85f0d9578ab828
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008827"
---
# <a name="how-to-use-immutable-types-and-non-public-accessors-with-no-locsystemtextjson"></a>System.Text.Json에서 변경 불가능한 형식 및 public이 아닌 접근자를 사용하는 방법

이 문서에서는 `System.Text.Json` 네임스페이스를 사용하여 레코드와 같이 변경 불가능한 형식을 사용하는 방법을 알아봅니다.

## <a name="immutable-types-and-records"></a>변경 불가능한 형식 및 레코드

::: zone pivot="dotnet-5-0"
`System.Text.Json`은 매개 변수가 있는 생성자를 사용할 수 있습니다. 이 생성자를 사용하면 변경 불가능한 클래스 또는 구조체를 역직렬화할 수 있습니다. 클래스의 경우 유일한 생성자가 매개 변수가 있는 생성자이면 해당 생성자가 사용됩니다. 구조체 또는 여러 생성자가 포함된 클래스의 경우 [JsonConstructor](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) 특성을 적용하여 사용할 생성자를 지정합니다. 특성을 사용하지 않는 경우 매개 변수가 없는 public 생성자가 있으면 항상 사용됩니다. 특성은 public 생성자에만 사용할 수 있습니다. 다음 예제는 `[JsonConstructor]` 특성을 사용합니다.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

다음 예제와 같이 C# 9의 레코드도 지원됩니다.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

모든 속성 setter가 public이 아니기 때문에 변경 불가능한 형식의 경우 [public이 아닌 속성 접근자](#non-public-property-accessors)에 대한 다음 섹션을 참조하세요.
::: zone-end

::: zone pivot="dotnet-core-3-1"
`JsonConstructorAttribute` 및 C# 9 레코드 지원은 .Net Core 3.1에서 사용할 수 없습니다.
::: zone-end

## <a name="non-public-property-accessors"></a>public이 아닌 속성 접근자

::: zone pivot="dotnet-5-0"
public이 아닌 속성 접근자를 사용하도록 설정하려면 다음 예제와 같이 [JsonInclude](xref:System.Text.Json.Serialization.JsonIncludeAttribute) 특성을 사용합니다.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
public이 아닌 속성 접근자는 .NET Core 3.1에서 지원되지 않습니다. 자세한 내용은 [Newtonsoft.Json에서 마이그레이션 문서](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters)를 참조하세요.
::: zone-end

## <a name="see-also"></a>참고 항목

* [System.Text.Json 개요](system-text-json-overview.md)
* [JSON 직렬화 및 역직렬화 방법](system-text-json-how-to.md)
* [JsonSerializerOptions 인스턴스 인스턴스화](system-text-json-configure-options.md)
* [대/소문자를 구분하지 않는 일치를 사용하도록 설정](system-text-json-character-casing.md)
* [속성 이름 및 값 사용자 지정](system-text-json-customize-properties.md)
* [속성 무시](system-text-json-ignore-properties.md)
* [잘못된 JSON 허용](system-text-json-invalid-json.md)
* [오버플로 JSON 처리](system-text-json-handle-overflow.md)
* [참조 유지](system-text-json-preserve-references.md)
* [다형 직렬화](system-text-json-polymorphism.md)
* [Newtonsoft.Json에서 System.Text.Json으로 마이그레이션](system-text-json-migrate-from-newtonsoft-how-to.md)
* [문자 인코딩 사용자 지정](system-text-json-character-encoding.md)
* [사용자 지정 직렬 변환기 및 역직렬 변환기 작성](write-custom-serializer-deserializer.md)
* [JSON serialization용 사용자 지정 변환기 작성](system-text-json-converters-how-to.md)
* [DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
* [System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)
