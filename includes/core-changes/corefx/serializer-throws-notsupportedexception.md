---
ms.openlocfilehash: 39d1b2dba8077bf9bf998775f8967d455f36b549
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119085"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="0a3e3-101">Json 직렬 변환기 예외 형식을 `JsonException`에서 `NotSupportedException`으로 변경</span><span class="sxs-lookup"><span data-stu-id="0a3e3-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="0a3e3-102">.Net Core 3.0 미리 보기 6~8에서는 지원되지 않는 파생 컬렉션 형식이 발견되면 직렬 변환기가 <xref:System.Text.Json.JsonException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3e3-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="0a3e3-103">.Net Core 3.0 미리 보기 9부터 직렬 변환기가 대신 <xref:System.NotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3e3-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0a3e3-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="0a3e3-104">Change description</span></span>

<span data-ttu-id="0a3e3-105">.Net Core 3.0 미리 보기 6~8에서는 지원되지 않는 파생 컬렉션 형식이 발견되면 직렬 변환기가 <xref:System.Text.Json.JsonException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3e3-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="0a3e3-106">*지원되지 않는 파생 컬렉션 형식*은 다음 형식 중 하나에 할당할 수 없는 컬렉션 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0a3e3-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

 - <xref:System.Collections.IList>
 - <xref:System.Collections.Generic.ICollection%601>
 - <xref:System.Collections.Generic.Stack%601>
 - <xref:System.Collections.Generic.Queue%601>`
 - <xref:System.Collections.IDictionary>
 - [<span data-ttu-id="0a3e3-107">IDictionary\<String,T></span><span class="sxs-lookup"><span data-stu-id="0a3e3-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="0a3e3-108">.Net Core 3.0 미리 보기 9부터 직렬 변환기는 지원되지 않는 컬렉션 형식이 발생하면 <xref:System.NotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3e3-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="0a3e3-109">새 예외 형식이 역직렬화 작업이 실패하는 이유를 더 잘 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3e3-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0a3e3-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0a3e3-110">Version introduced</span></span>

<span data-ttu-id="0a3e3-111">3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="0a3e3-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0a3e3-112">권장 작업</span><span class="sxs-lookup"><span data-stu-id="0a3e3-112">Recommended action</span></span>

<span data-ttu-id="0a3e3-113">역직렬화할 때 <xref:System.Text.Json.JsonException>을 확인하는 경우 <xref:System.NotSupportedException>도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0a3e3-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="0a3e3-114">범주</span><span class="sxs-lookup"><span data-stu-id="0a3e3-114">Category</span></span>

<span data-ttu-id="0a3e3-115">CoreFx</span><span class="sxs-lookup"><span data-stu-id="0a3e3-115">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0a3e3-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0a3e3-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
