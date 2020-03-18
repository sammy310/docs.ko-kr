---
ms.openlocfilehash: 3bce796191e0ebe6dbe4650457abe5a20c383f02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147564"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a><span data-ttu-id="a00a2-101">JsonFactoryConverter.CreateConverter 서명이 변경되었습니다</span><span class="sxs-lookup"><span data-stu-id="a00a2-101">JsonFactoryConverter.CreateConverter signature changed</span></span>

<span data-ttu-id="a00a2-102"><xref:System.Text.Json.Serialization.JsonConverterFactory> 클래스의 구성을 용이하게 하기 위해 <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> 메서드가 공개되었고 형식이 <xref:System.Text.Json.JsonSerializerOptions>인 두 번째 인수가 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a00a2-102">To facilitate the composition of <xref:System.Text.Json.Serialization.JsonConverterFactory> classes, the <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> method has been made public and given a second argument of type <xref:System.Text.Json.JsonSerializerOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a00a2-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="a00a2-103">Change description</span></span>

<span data-ttu-id="a00a2-104">버전 3.0 미리 보기 8 이전에 .NET Core에서 `CreateConverter` 메서드의 서명은 다음과 같았습니다.</span><span class="sxs-lookup"><span data-stu-id="a00a2-104">The signature of the `CreateConverter` method in .NET Core prior to version 3.0 Preview 8 was:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

<span data-ttu-id="a00a2-105">.NET Core 3.0 미리 보기 8 이상 버전에서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a00a2-105">In .NET Core 3.0 Preview 8 and later versions, it is:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

<span data-ttu-id="a00a2-106">이 변경 전에는 <xref:System.Text.Json.Serialization.JsonConverter%601>을 가져올 쉬운 방법이 없었으므로 봉인된 팩터리 변환기를 구성하기가 어려웠습니다.</span><span class="sxs-lookup"><span data-stu-id="a00a2-106">Before this change, it was difficult to compose sealed factory converters, since there was no easy way to get the <xref:System.Text.Json.Serialization.JsonConverter%601> from it.</span></span> <span data-ttu-id="a00a2-107">팩터리 메서드를 공개하고 현재 <xref:System.Text.Json.JsonSerializerOptions>도 전달하면 훨씬 유연한 구성이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="a00a2-107">Making the factory method public and also passing the current <xref:System.Text.Json.JsonSerializerOptions> allow for much more flexible composition.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a00a2-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="a00a2-108">Version introduced</span></span>

<span data-ttu-id="a00a2-109">3.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="a00a2-109">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a00a2-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="a00a2-110">Recommended action</span></span>

<span data-ttu-id="a00a2-111">파생 클래스를 업데이트하고 다시 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00a2-111">Derived classes need to be updated and recompiled.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a00a2-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a00a2-112">Affected APIs</span></span>

- <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
