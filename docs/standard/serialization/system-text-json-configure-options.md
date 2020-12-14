---
title: System.Text.Json을 사용하여 JsonSerializerOptions를 인스턴스화하는 방법
description: 성능 문제를 방지하는 방법과 JsonSerializerOptions 인스턴스에 대해 사용 가능한 생성자를 사용하는 방법을 알아봅니다.
ms.date: 12/02/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 5f32e1369e58dd9550f28abc822f187dee46c022
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009835"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a>System.Text.Json을 사용하여 JsonSerializerOptions 인스턴스를 인스턴스화하는 방법

이 문서에서는 <xref:System.Text.Json.JsonSerializerOptions>를 사용하는 경우 성능 문제를 방지하는 방법을 설명합니다. 또한 사용할 수 있는 매개 변수가 있는 생성자를 사용하는 방법을 보여 줍니다.

## <a name="reuse-jsonserializeroptions-instances"></a>JsonSerializerOptions 인스턴스 다시 사용

동일한 옵션으로 `JsonSerializerOptions`를 반복적으로 사용하는 경우 사용할 때마다 새 `JsonSerializerOptions` 인스턴스를 만들지 마세요. 모든 호출에 대해 동일한 인스턴스를 다시 사용하세요. 이 지침은 사용자 지정 변환기에 대해 작성하는 코드와 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 또는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>을 호출할 때 적용됩니다.

다음 코드에서는 새 옵션 인스턴스를 사용하는 경우의 성능 저하를 보여 줍니다.

:::code language="csharp" source="snippets/system-text-json-configure-options/csharp/ReuseOptionsInstances.cs":::

위의 코드는 동일한 옵션 인스턴스를 사용하여 작은 개체를 100,000번 직렬화합니다. 그런 다음, 동일한 개체를 동일한 횟수만큼 직렬화하고 매번 새 옵션 인스턴스를 만듭니다. 일반적인 런타임 차이는 40,140밀리초와 비교할 때 190입니다. 반복 횟수를 늘리면 차이가 훨씬 커집니다.

직렬 변환기는 새 옵션 인스턴스가 전달될 때 개체 그래프의 각 형식의 첫 번째 serialization 동안 준비 단계를 수행합니다. 이 준비에는 serialization에 필요한 메타데이터의 캐시를 만드는 작업이 포함됩니다. 메타데이터에는 getter 및 setter 속성, 생성자 인수, 지정된 특성 등에 대한 대리자가 포함됩니다. 이 메타데이터 캐시는 옵션 인스턴스에 저장됩니다. 동일한 준비 프로세스 및 캐시가 deserialization에 적용됩니다.

`JsonSerializerOptions` 인스턴스의 메타데이터 캐시 크기는 직렬화되는 형식 수에 따라 달라집니다. 여러 형식(예: 동적으로 생성된 형식)을 직렬 변환기에 전달하는 경우 캐시 크기가 계속 커지고 결국 `OutOfMemoryException`이 발생할 수 있습니다.

## <a name="copy-jsonserializeroptions"></a>JsonSerializerOptions 복사

::: zone pivot="dotnet-5-0"
다음 예제와 같이 기존 인스턴스와 동일한 옵션으로 새 인스턴스를 만들 수 있는 [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions))이 있습니다.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
기존 인스턴스를 사용하는 `JsonSerializerOptions` 생성자는 .NET Core 3.1에서 사용할 수 없습니다.
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a>JsonSerializerOptions의 웹 기본값

::: zone pivot="dotnet-5-0"
서로 다른 웹앱 기본값을 갖는 옵션은 다음과 같습니다.

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

다음 예제와 같이 ASP.NET Core가 웹앱에 사용하는 기본 옵션으로 새 인스턴스를 만들 수 있는 [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true)이 있습니다.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
서로 다른 웹앱 기본값을 갖는 옵션은 다음과 같습니다.

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

기본값 집합을 지정하는 `JsonSerializerOptions` 생성자는 .NET Core 3.1에서 사용할 수 없습니다.
::: zone-end

## <a name="see-also"></a>참고 항목

* [System.Text.Json 개요](system-text-json-overview.md)
* [JSON 직렬화 및 역직렬화 방법](system-text-json-how-to.md)
* [대/소문자를 구분하지 않는 일치를 사용하도록 설정](system-text-json-character-casing.md)
* [속성 이름 및 값 사용자 지정](system-text-json-customize-properties.md)
* [속성 무시](system-text-json-ignore-properties.md)
* [잘못된 JSON 허용](system-text-json-invalid-json.md)
* [오버플로 JSON 처리](system-text-json-handle-overflow.md)
* [참조 유지](system-text-json-preserve-references.md)
* [변경할 수 없는 형식 및 public이 아닌 접근자](system-text-json-immutability.md)
* [다형 직렬화](system-text-json-polymorphism.md)
* [Newtonsoft.Json에서 System.Text.Json으로 마이그레이션](system-text-json-migrate-from-newtonsoft-how-to.md)
* [문자 인코딩 사용자 지정](system-text-json-character-encoding.md)
* [사용자 지정 직렬 변환기 및 역직렬 변환기 작성](write-custom-serializer-deserializer.md)
* [JSON serialization용 사용자 지정 변환기 작성](system-text-json-converters-how-to.md)
* [DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
* [System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)
