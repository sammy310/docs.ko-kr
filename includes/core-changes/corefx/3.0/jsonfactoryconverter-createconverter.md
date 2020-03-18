---
ms.openlocfilehash: 3bce796191e0ebe6dbe4650457abe5a20c383f02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147564"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a>JsonFactoryConverter.CreateConverter 서명이 변경되었습니다

<xref:System.Text.Json.Serialization.JsonConverterFactory> 클래스의 구성을 용이하게 하기 위해 <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> 메서드가 공개되었고 형식이 <xref:System.Text.Json.JsonSerializerOptions>인 두 번째 인수가 지정되었습니다.

#### <a name="change-description"></a>변경 내용 설명

버전 3.0 미리 보기 8 이전에 .NET Core에서 `CreateConverter` 메서드의 서명은 다음과 같았습니다.

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

.NET Core 3.0 미리 보기 8 이상 버전에서는 다음과 같습니다.

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

이 변경 전에는 <xref:System.Text.Json.Serialization.JsonConverter%601>을 가져올 쉬운 방법이 없었으므로 봉인된 팩터리 변환기를 구성하기가 어려웠습니다. 팩터리 메서드를 공개하고 현재 <xref:System.Text.Json.JsonSerializerOptions>도 전달하면 훨씬 유연한 구성이 가능합니다.

#### <a name="version-introduced"></a>도입된 버전

3.0 미리 보기 8

#### <a name="recommended-action"></a>권장 조치

파생 클래스를 업데이트하고 다시 컴파일해야 합니다.

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
