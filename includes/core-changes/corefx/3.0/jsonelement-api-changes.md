---
ms.openlocfilehash: 79901d0b57816915ca7ea73cfe7fa3d40820434e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568108"
---
### <a name="jsonelement-api-changes"></a><span data-ttu-id="91ff9-101">JsonElement API 변경 내용</span><span class="sxs-lookup"><span data-stu-id="91ff9-101">JsonElement API changes</span></span>

<span data-ttu-id="91ff9-102">.Net Core 3.0 미리 보기 7부터 일부 <xref:System.Text.Json.JsonElement> API가 검색성 및 사용성을 향상하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-102">Starting with .NET Core 3.0 Preview 7, some <xref:System.Text.Json.JsonElement> APIs have changed to allow for easier discovery and greater usability.</span></span>

#### <a name="change-description"></a><span data-ttu-id="91ff9-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="91ff9-103">Change description</span></span>

<span data-ttu-id="91ff9-104">.Net Core 3.0 미리 보기 7에서 <xref:System.Text.Json.JsonElement> API가 다음과 같이 검색 및 유용성을 향상하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-104">In .NET Core 3.0 Preview 7, <xref:System.Text.Json.JsonElement> APIs have changed as follows to allow for easier discovery and greater usability.</span></span>

1. <span data-ttu-id="91ff9-105">모든 `WriteProperty` 메서드 오버로드가 <xref:System.Text.Json.JsonElement>에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-105">All `WriteProperty` method overloads were removed from <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="91ff9-106">이는 다음과 같은 코드에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-106">This affects code such as the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
      JsonElement root = doc.RootElement;
      root.WriteProperty(propertyNameString, writer);
      // ..
      root.WriteProperty(propertyNameSpan, writer);
      // ..
      root.WriteProperty(propertyNameJsonEncoded, writer);
      // ..
      root.WriteProperty(utf8PropertyName, writer);
      //..
   }
   ```

1. <span data-ttu-id="91ff9-107">`WriteValue`의 이름이 <xref:System.Text.Json.JsonElement.WriteTo%2A>로 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-107">`WriteValue` was renamed as <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span></span> <span data-ttu-id="91ff9-108">이는 다음과 같은 코드에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-108">This affects code such as the following:</span></span>

   ```csharp
    using (JsonDocument doc = JsonDocument.Parse(jsonString))
    {
        JsonElement root = doc.RootElement;
        root.WriteValue(writer);
    }
    ```

1. <span data-ttu-id="91ff9-109">이제 <xref:System.Text.Json.JsonElement.WriteTo%2A>는 메서드 매개 변수가 `null`인 경우 <xref:System.ArgumentNullException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> now throws an <xref:System.ArgumentNullException> when its method parameter is `null`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="91ff9-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="91ff9-110">Version introduced</span></span>

<span data-ttu-id="91ff9-111">3.0 미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="91ff9-111">3.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="91ff9-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="91ff9-112">Recommended action</span></span>

<span data-ttu-id="91ff9-113">코드가 이러한 변경의 영향을 받는 경우 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-113">If your code is affected by these changes, you can do the following:</span></span>

- <span data-ttu-id="91ff9-114"><xref:System.Text.Json.JsonElement>에서 `WriteProperty` 오버로드에 대한 대체 API는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-114">There is no replacement API for the `WriteProperty` overloads in <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="91ff9-115">대신, <xref:System.Text.Json.JsonElement.WriteTo%2A> 메서드와 함께 <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> 오버로드 중 하나를 호출하여 동일한 결과를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-115">Instead, you can call one of the <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> overloads along with the <xref:System.Text.Json.JsonElement.WriteTo%2A> method to achieve the same result.</span></span> <span data-ttu-id="91ff9-116">예들 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-116">For example:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="91ff9-117">`WriteValue` 메서드의 이름을 <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-117">Rename the `WriteValue` method to <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span></span> <span data-ttu-id="91ff9-118">메서드 매개 변수는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-118">The method parameter remains unchanged.</span></span> <span data-ttu-id="91ff9-119">예를 들어 이전 코드는 다음과 같이 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-119">For example, the previous code should be changed to the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="91ff9-120"><xref:System.Text.Json.JsonElement.WriteTo%2A> 메서드에 대한 호출에서 <xref:System.ArgumentNullException>을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="91ff9-120">Handle the <xref:System.ArgumentNullException> in calls to the <xref:System.Text.Json.JsonElement.WriteTo%2A> method.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="91ff9-121">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="91ff9-121">Affected APIs</span></span>

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
