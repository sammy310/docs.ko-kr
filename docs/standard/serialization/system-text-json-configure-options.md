---
title: System.Text.Json을 사용하여 JsonSerializerOptions를 인스턴스화하는 방법
description: 기존 인스턴스를 복사하거나 웹 기본값을 사용하여 JsonSerializerOptions 인스턴스를 인스턴스화하는 방법을 알아봅니다.
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
ms.openlocfilehash: 0febfe15f36856f10699fd327fb17c146277eb9b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439870"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a>System.Text.Json을 사용하여 JsonSerializerOptions 인스턴스를 인스턴스화하는 방법

이 문서에서는 기존 인스턴스를 복사하거나 웹 기본값을 사용하여 <xref:System.Text.Json.JsonSerializerOptions> 인스턴스를 인스턴스화하는 방법을 알아봅니다.

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
* [대/소문자를 구분하지 않는 일치를 사용하도록 설정](system-text-json-character-casing.md)
* [속성 이름 및 값 사용자 지정](system-text-json-customize-properties.md)
* [속성 무시](system-text-json-ignore-properties.md)
* [잘못된 JSON 허용](system-text-json-invalid-json.md)
* [오버플로 JSON 처리](system-text-json-handle-overflow.md)
* [순환 참조 보존](system-text-json-preserve-references.md)
* [변경할 수 없는 형식 및 public이 아닌 접근자](system-text-json-immutability.md)
* [다형 직렬화](system-text-json-polymorphism.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
