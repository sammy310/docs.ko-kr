---
ms.openlocfilehash: 43da6233b70927e7320874772976b9e93a0bd69f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720979"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a><span data-ttu-id="e826c-101">JsonFactoryConverter.CreateConverter 서명이 변경되었습니다</span><span class="sxs-lookup"><span data-stu-id="e826c-101">JsonFactoryConverter.CreateConverter signature changed</span></span>

<span data-ttu-id="e826c-102"><xref:System.Text.Json.Serialization.JsonConverterFactory> 클래스의 구성을 용이하게 하기 위해 <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> 메서드가 공개되었고 형식이 <xref:System.Text.Json.JsonSerializerOptions>인 두 번째 인수가 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e826c-102">To facilitate the composition of <xref:System.Text.Json.Serialization.JsonConverterFactory> classes, the <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> method has been made public and given a second argument of type <xref:System.Text.Json.JsonSerializerOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e826c-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="e826c-103">Change description</span></span>

<span data-ttu-id="e826c-104">버전 3.0 미리 보기 8 이전에 .NET Core에서 `CreateConverter` 메서드의 서명은 다음과 같았습니다.</span><span class="sxs-lookup"><span data-stu-id="e826c-104">The signature of the `CreateConverter` method in .NET Core prior to version 3.0 Preview 8 was:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

<span data-ttu-id="e826c-105">.NET Core 3.0 미리 보기 8 이상 버전에서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e826c-105">In .NET Core 3.0 Preview 8 and later versions, it is:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

<span data-ttu-id="e826c-106">이 변경 전에는 <xref:System.Text.Json.Serialization.JsonConverter%601>을 가져올 쉬운 방법이 없었으므로 봉인된 팩터리 변환기를 구성하기가 어려웠습니다.</span><span class="sxs-lookup"><span data-stu-id="e826c-106">Before this change, it was difficult to compose sealed factory converters, since there was no easy way to get the <xref:System.Text.Json.Serialization.JsonConverter%601> from it.</span></span> <span data-ttu-id="e826c-107">팩터리 메서드를 공개하고 현재 <xref:System.Text.Json.JsonSerializerOptions>도 전달하면 훨씬 유연한 구성이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="e826c-107">Making the factory method public and also passing the current <xref:System.Text.Json.JsonSerializerOptions> allow for much more flexible composition.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e826c-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e826c-108">Version introduced</span></span>

<span data-ttu-id="e826c-109">3.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="e826c-109">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e826c-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="e826c-110">Recommended action</span></span>

<span data-ttu-id="e826c-111">파생 클래스를 업데이트하고 다시 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e826c-111">Derived classes need to be updated and recompiled.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e826c-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e826c-112">Affected APIs</span></span>

- <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>

<!-- For tool use only

#### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
