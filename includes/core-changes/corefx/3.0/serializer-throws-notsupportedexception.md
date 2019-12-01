---
ms.openlocfilehash: e6e10b2ec451c07bf397cbdcac51ef57c29dab47
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568188"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="e513f-101">Json 직렬 변환기 예외 형식을 `JsonException`에서 `NotSupportedException`으로 변경</span><span class="sxs-lookup"><span data-stu-id="e513f-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="e513f-102">.Net Core 3.0 미리 보기 6~8에서는 지원되지 않는 파생 컬렉션 형식이 발견되면 직렬 변환기가 <xref:System.Text.Json.JsonException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e513f-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="e513f-103">.Net Core 3.0 미리 보기 9부터 직렬 변환기가 대신 <xref:System.NotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e513f-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e513f-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="e513f-104">Change description</span></span>

<span data-ttu-id="e513f-105">.Net Core 3.0 미리 보기 6~8에서는 지원되지 않는 파생 컬렉션 형식이 발견되면 직렬 변환기가 <xref:System.Text.Json.JsonException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e513f-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="e513f-106">*지원되지 않는 파생 컬렉션 형식*은 다음 형식 중 하나에 할당할 수 없는 컬렉션 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e513f-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [<span data-ttu-id="e513f-107">IDictionary\<String,T></span><span class="sxs-lookup"><span data-stu-id="e513f-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="e513f-108">.Net Core 3.0 미리 보기 9부터 직렬 변환기는 지원되지 않는 컬렉션 형식이 발생하면 <xref:System.NotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e513f-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="e513f-109">새 예외 형식이 역직렬화 작업이 실패하는 이유를 더 잘 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="e513f-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e513f-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e513f-110">Version introduced</span></span>

<span data-ttu-id="e513f-111">3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="e513f-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e513f-112">권장 작업</span><span class="sxs-lookup"><span data-stu-id="e513f-112">Recommended action</span></span>

<span data-ttu-id="e513f-113">역직렬화할 때 <xref:System.Text.Json.JsonException>을 확인하는 경우 <xref:System.NotSupportedException>도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e513f-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="e513f-114">범주</span><span class="sxs-lookup"><span data-stu-id="e513f-114">Category</span></span>

<span data-ttu-id="e513f-115">CoreFx</span><span class="sxs-lookup"><span data-stu-id="e513f-115">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e513f-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e513f-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
