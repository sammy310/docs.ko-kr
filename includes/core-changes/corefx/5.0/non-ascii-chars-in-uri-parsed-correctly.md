---
ms.openlocfilehash: faf9459ab9002e6149560e2a3452265fa246bf6b
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720204"
---
### <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a><span data-ttu-id="587b7-101">Unix에서 비ASCII 문자를 포함하는 URI 경로가 올바르게 구문 분석됨</span><span class="sxs-lookup"><span data-stu-id="587b7-101">URI paths with non-ASCII characters parse correctly on Unix</span></span>

<span data-ttu-id="587b7-102">비ASCII 문자를 포함하는 절대 URI 경로가 이제 Unix 플랫폼에서 올바르게 구문 분석되도록 <xref:System.Uri?displayProperty=fullName> 클래스의 버그가 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="587b7-102">A bug was fixed in the <xref:System.Uri?displayProperty=fullName> class such that absolute URI paths that contain non-ASCII characters now parse correctly on Unix platforms.</span></span>

#### <a name="change-description"></a><span data-ttu-id="587b7-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="587b7-103">Change description</span></span>

<span data-ttu-id="587b7-104">이전 버전의 .NET에서는 비ASCII 문자를 포함하는 절대 URI 경로가 Unix 플랫폼에서 잘못 구문 분석되고 경로 세그먼트가 중복됩니다.</span><span class="sxs-lookup"><span data-stu-id="587b7-104">In previous versions of .NET, absolute URI paths that contain non-ASCII characters are parsed incorrectly on Unix platforms, and segments of the path are duplicated.</span></span> <span data-ttu-id="587b7-105">절대 경로는 “/”로 시작하는 경로입니다. .NET 5.0에서는 구문 분석 문제가 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="587b7-105">(Absolute paths are those that start with "/".) The parsing issue has been fixed for .NET 5.0.</span></span> <span data-ttu-id="587b7-106">이전 버전의 .NET에서 .NET 5.0 이상으로 이동하는 경우 <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType>, 기타 <xref:System.Uri> 멤버에서 다른 값이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="587b7-106">If you move from a previous version of .NET to .NET 5.0 or later, you'll get different values produced by <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType>, and other <xref:System.Uri> members.</span></span>

<span data-ttu-id="587b7-107">Unix에서 실행할 때 다음 코드의 출력을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="587b7-107">Consider the output of the following code when run on Unix.</span></span>

```csharp
var myUri = new Uri("/üri");

Console.WriteLine($"AbsoluteUri: {myUri.AbsoluteUri}");
Console.WriteLine($"ToString: {myUri.ToString()}");
```

<span data-ttu-id="587b7-108">이전 .NET 버전에서의 출력:</span><span class="sxs-lookup"><span data-stu-id="587b7-108">Output on previous .NET version:</span></span>

```text
AbsoluteUri: /%C3%BCri/%C3%BCri
ToString: /üri/üri
```

<span data-ttu-id="587b7-109">.NET 5.0 이상 버전에서의 출력:</span><span class="sxs-lookup"><span data-stu-id="587b7-109">Output on .NET 5.0 or later version:</span></span>

```text
AbsoluteUri: /%C3%BCri
ToString: /üri
```

#### <a name="version-introduced"></a><span data-ttu-id="587b7-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="587b7-110">Version introduced</span></span>

<span data-ttu-id="587b7-111">5.0</span><span class="sxs-lookup"><span data-stu-id="587b7-111">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="587b7-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="587b7-112">Recommended action</span></span>

<span data-ttu-id="587b7-113">중복된 경로 세그먼트를 예상해서 고려하는 코드가 있을 경우 해당 코드를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="587b7-113">If you have code that expects and accounts for the duplicated path segments, you can remove that code.</span></span>

#### <a name="category"></a><span data-ttu-id="587b7-114">범주</span><span class="sxs-lookup"><span data-stu-id="587b7-114">Category</span></span>

<span data-ttu-id="587b7-115">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="587b7-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="587b7-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="587b7-116">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
