---
ms.openlocfilehash: 9052f509ec6df4e4b911e2f33b5c8197adb9a2c3
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568129"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a><span data-ttu-id="51081-101">JsonFactoryConverter.CreateConverter 서명이 변경되었습니다</span><span class="sxs-lookup"><span data-stu-id="51081-101">JsonFactoryConverter.CreateConverter signature changed</span></span>

<span data-ttu-id="51081-102"><xref:System.Text.Json.Serialization.JsonConverterFactory> 클래스의 구성을 용이하게 하기 위해 <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> 메서드가 공개되었고 형식이 <xref:System.Text.Json.JsonSerializerOptions>인 두 번째 인수가 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="51081-102">To facilitate the composition of <xref:System.Text.Json.Serialization.JsonConverterFactory> classes, the <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> method has been made public and given a second argument of type <xref:System.Text.Json.JsonSerializerOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="51081-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="51081-103">Change description</span></span>

<span data-ttu-id="51081-104">버전 3.0 미리 보기 8 이전에 .NET Core에서 `CreateConverter` 메서드의 서명은 다음과 같았습니다.</span><span class="sxs-lookup"><span data-stu-id="51081-104">The signature of the `CreateConverter` method in .NET Core prior to version 3.0 Preview 8 was:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

<span data-ttu-id="51081-105">.NET Core 3.0 미리 보기 8 이상 버전에서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="51081-105">In .NET Core 3.0 Preview 8 and later versions, it is:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

<span data-ttu-id="51081-106">이 변경 전에는 <xref:System.Text.Json.Serialization.JsonConverter%601>을 가져올 쉬운 방법이 없었으므로 봉인된 팩터리 변환기를 구성하기가 어려웠습니다.</span><span class="sxs-lookup"><span data-stu-id="51081-106">Before this change, it was difficult to compose sealed factory converters, since there was no easy way to get the <xref:System.Text.Json.Serialization.JsonConverter%601> from it.</span></span> <span data-ttu-id="51081-107">팩터리 메서드를 공개하고 현재 <xref:System.Text.Json.JsonSerializerOptions>도 전달하면 훨씬 유연한 구성이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="51081-107">Making the factory method public and also passing the current <xref:System.Text.Json.JsonSerializerOptions> allow for much more flexible composition.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="51081-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="51081-108">Version introduced</span></span>

<span data-ttu-id="51081-109">3.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="51081-109">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="51081-110">권장 작업</span><span class="sxs-lookup"><span data-stu-id="51081-110">Recommended action</span></span>

<span data-ttu-id="51081-111">파생 클래스를 업데이트하고 다시 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51081-111">Derived classes need to be updated and recompiled.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="51081-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="51081-112">Affected APIs</span></span>

<span data-ttu-id="51081-113"><xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="51081-113"><xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>.</span></span>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
