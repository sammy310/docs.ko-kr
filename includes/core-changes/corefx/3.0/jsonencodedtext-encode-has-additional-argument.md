---
ms.openlocfilehash: d90996ae1b87cdea815daf979bece094d8602f70
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721344"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a><span data-ttu-id="64592-101">JsonEncodedText.Encode 메서드에 JavaScriptEncoder 인수 추가</span><span class="sxs-lookup"><span data-stu-id="64592-101">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>

<span data-ttu-id="64592-102">.Net Core 3.0 미리 보기 8부터 <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> 메서드는 선택적 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 인수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="64592-102">Starting with .NET Core 3.0 Preview 8, the <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> methods contain an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> argument.</span></span>

#### <a name="change-description"></a><span data-ttu-id="64592-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="64592-103">Change description</span></span>

<span data-ttu-id="64592-104">.NET Core 3.0에는 새 형식인 xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>가 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64592-104">.NET Core 3.0 includes a new type, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="64592-105">.Net Core 3.0 미리 보기 8부터 모든 <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> 메서드 오버로드의 서명이 선택적 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 매개 변수를 포함하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="64592-105">Starting with .NET Core 3.0 Preview 8, the signature of all <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> method overloads has changed to include an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> parameter.</span></span> <span data-ttu-id="64592-106">이 변경은 다른 또는 사용자 지정 인코더를 허용하기 위해 실시된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="64592-106">This change was made to allow for a different or custom encoder.</span></span>

<span data-ttu-id="64592-107">.Net Core 3.0 미리 보기 7에서 `Encode` 메서드의 서명은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="64592-107">The signature of the `Encode` methods in .NET Core 3.0 Preview 7 is:</span></span>

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value);
        public static JsonEncodedText Encode(string value);
    }
}
```

<span data-ttu-id="64592-108">.Net Core 3.0 미리 보기 8 버전 이상에서 동일한 `Encode` 메서드의 서명은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="64592-108">The signature of the same `Encode` methods in .NET Core 3.0 Preview 8 and later versions is:</span></span>

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(string value, JavaScriptEncoder encoder = null);
    }
}
```

#### <a name="version-introduced"></a><span data-ttu-id="64592-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="64592-109">Version introduced</span></span>

<span data-ttu-id="64592-110">.NET Core 3.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="64592-110">.NET Core 3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="64592-111">권장 조치</span><span class="sxs-lookup"><span data-stu-id="64592-111">Recommended action</span></span>

<span data-ttu-id="64592-112">이는 이진 주요 변경 내용일 뿐입니다. .NET Core 3.0 미리 보기 8 버전 이상에 대해 다시 컴파일하면 런타임 문제가 모두 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="64592-112">This is a binary breaking change only; a recompile against .NET Core 3.0 Preview 8 or a later version will fix any runtime issues.</span></span>

#### <a name="category"></a><span data-ttu-id="64592-113">범주</span><span class="sxs-lookup"><span data-stu-id="64592-113">Category</span></span>

<span data-ttu-id="64592-114">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="64592-114">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="64592-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="64592-115">Affected APIs</span></span>

- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
