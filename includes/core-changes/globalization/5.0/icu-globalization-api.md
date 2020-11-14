---
ms.openlocfilehash: 02b5dc181abe384c1a5f47c042e475f67a0afe1c
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400807"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a><span data-ttu-id="0db01-101">Windows에서 세계화 API가 ICU 라이브러리를 사용</span><span class="sxs-lookup"><span data-stu-id="0db01-101">Globalization APIs use ICU libraries on Windows</span></span>

<span data-ttu-id="0db01-102">.NET 5.0 이상 버전에서는 Windows 10 2019년 5월 업데이트 이상에서 실행되는 경우 세계화 기능에 [ICU(International Components for Unicode)](http://site.icu-project.org/home) 라이브러리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-102">.NET 5.0 and later versions use [International Components for Unicode (ICU)](http://site.icu-project.org/home) libraries for globalization functionality when running on Windows 10 May 2019 Update or later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0db01-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="0db01-103">Change description</span></span>

<span data-ttu-id="0db01-104">.NET Core 1.0~3.1 및 .NET Framework 4 이상에서 .NET 라이브러리는 Windows의 세계화 기능에 [국가별 언어 지원(NLS)](/windows/win32/intl/national-language-support) API를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-104">In .NET Core 1.0 - 3.1 and .NET Framework 4 and later, .NET libraries use [National Language Support (NLS)](/windows/win32/intl/national-language-support) APIs for globalization functionality on Windows.</span></span> <span data-ttu-id="0db01-105">예를 들어 NLS 함수는 문자열 비교, 문화권 정보 가져오기, 해당 문화권에서 문자열 대/소문자 구분 수행에 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-105">For example, NLS functions were used to compare strings, get culture information, and perform string casing in the appropriate culture.</span></span>

<span data-ttu-id="0db01-106">.NET 5.0부터 앱이 Windows 10 2019년 5월 업데이트 이상에서 실행되는 경우 .NET 라이브러리는 기본적으로 [ICU](http://site.icu-project.org/home) 세계화 API를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-106">Starting in .NET 5.0, if an app is running on Windows 10 May 2019 Update or later, .NET libraries use [ICU](http://site.icu-project.org/home) globalization APIs, by default.</span></span>

> [!NOTE]
> <span data-ttu-id="0db01-107">Windows 10 2019년 5월 업데이트 이상 버전에는 ICU 네이티브 라이브러리가 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-107">Windows 10 May 2019 Update and later versions ship with the ICU native library.</span></span> <span data-ttu-id="0db01-108">.NET 런타임에서 ICU를 로드할 수 없는 경우 대신 NLS를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-108">If the .NET runtime can't load ICU, it uses NLS instead.</span></span>

#### <a name="behavioral-differences"></a><span data-ttu-id="0db01-109">동작의 차이</span><span class="sxs-lookup"><span data-stu-id="0db01-109">Behavioral differences</span></span>

<span data-ttu-id="0db01-110">세계화 기능을 사용 중임을 인식하지 못하는 경우에도 앱에 변경 내용이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-110">You might see changes in your app even if you don't realize you're using globalization facilities.</span></span> <span data-ttu-id="0db01-111">이 섹션에는 표시될 수 있는 몇 가지 동작 변경이 나와 있지만 다른 내용도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-111">This section lists a couple of the behavioral changes you might see, but there are others too.</span></span>

##### <a name="stringindexof"></a><span data-ttu-id="0db01-112">String.IndexOf</span><span class="sxs-lookup"><span data-stu-id="0db01-112">String.IndexOf</span></span>

<span data-ttu-id="0db01-113"><xref:System.String.IndexOf(System.String)?displayProperty=nameWithType>을 호출하여 문자열에서 줄 바꿈 문자의 인덱스를 찾는 다음 코드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-113">Consider the following code that calls <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> to find the index of the newline character in a string.</span></span>

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- <span data-ttu-id="0db01-114">Windows의 .NET 이전 버전에서는 코드 조각이 `6`을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-114">In previous versions of .NET on Windows, the snippet prints `6`.</span></span>
- <span data-ttu-id="0db01-115">Windows 19H1 이상 버전의 .NET 5.0 이상 버전에서는 코드 조각이 `-1`을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-115">In .NET 5.0 and later versions on Windows 19H1 and later versions, the snippet prints `-1`.</span></span>

<span data-ttu-id="0db01-116">문화권을 구분하는 검색 대신 서수 검색을 수행하여 이 코드를 수정하려면 <xref:System.String.IndexOf(System.String,System.StringComparison)> 오버로드를 호출하고 <xref:System.StringComparison.Ordinal?displayProperty=nameWithType>을 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-116">To fix this code by conducting an ordinal search instead of a culture-sensitive search, call the <xref:System.String.IndexOf(System.String,System.StringComparison)> overload and pass in <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> as an argument.</span></span>

<span data-ttu-id="0db01-117">코드 분석 규칙 [CA1307: 명확성을 위해 StringComparison 지정](../../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) 및 [CA1309: 서수 StringComparison 사용](../../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md)을 실행하여 코드에서 이러한 호출 사이트를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-117">You can run code analysis rules [CA1307: Specify StringComparison for clarity](../../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) and [CA1309: Use ordinal StringComparison](../../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md) to find these call sites in your code.</span></span>

<span data-ttu-id="0db01-118">자세한 내용은 [.NET 5+에서 문자열 비교 시 동작 변경](../../../../docs/standard/base-types/string-comparison-net-5-plus.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0db01-118">For more information, see [Behavior changes when comparing strings on .NET 5+](../../../../docs/standard/base-types/string-comparison-net-5-plus.md).</span></span>

##### <a name="currency-symbol"></a><span data-ttu-id="0db01-119">통화 기호</span><span class="sxs-lookup"><span data-stu-id="0db01-119">Currency symbol</span></span>

<span data-ttu-id="0db01-120">통화 형식 지정자 `C`를 사용하여 문자열의 형식을 지정하는 다음 코드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-120">Consider the following code that formats a string using the currency format specifier `C`.</span></span> <span data-ttu-id="0db01-121">현재 스레드의 문화권은 국가가 아니라 언어만 포함하는 문화권으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-121">The current thread's culture is set to a culture that includes only the language and not the country.</span></span>

```csharp
System.Threading.Thread.CurrentThread.CurrentCulture = new System.Globalization.CultureInfo("de");
string text = string.Format("{0:C}", 100);
```

- <span data-ttu-id="0db01-122">Windows의 .NET 이전 버전에서 텍스트의 값은 `"100,00 €"`입니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-122">In previous versions of .NET on Windows, the value of text is `"100,00 €"`.</span></span>
- <span data-ttu-id="0db01-123">Windows 19H1 이상 버전의 .NET 5.0 이상 버전에서 텍스트의 값은 유로 대신 국제 통화 기호를 사용하는 `"100,00 ¤"`입니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-123">In .NET 5.0 and later versions on Windows 19H1 and later versions, the value of text is `"100,00 ¤"`, which uses the international currency symbol instead of the euro.</span></span> <span data-ttu-id="0db01-124">ICU의 의도는 통화가 언어가 아닌 국가 또는 지역의 속성이라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-124">In ICU, the design is that a currency is a property of a country or region, not a language.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0db01-125">변경 이유</span><span class="sxs-lookup"><span data-stu-id="0db01-125">Reason for change</span></span>

<span data-ttu-id="0db01-126">이 변경은 지원되는 모든 운영 체제에서 .NET의 세계화 동작을 통일하기 위해 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-126">This change was introduced to unify .NET's globalization behavior across all supported operating systems.</span></span> <span data-ttu-id="0db01-127">또한 애플리케이션이 운영 체제의 기본 제공 라이브러리에 의존하지 않고 자체 세계화 라이브러리를 묶을 수 있는 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-127">It also provides the ability for applications to bundle their own globalization libraries rather than depend on the operating system's built-in libraries.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0db01-128">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0db01-128">Version introduced</span></span>

<span data-ttu-id="0db01-129">.NET 5.0 미리 보기 4</span><span class="sxs-lookup"><span data-stu-id="0db01-129">.NET 5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0db01-130">권장 조치</span><span class="sxs-lookup"><span data-stu-id="0db01-130">Recommended action</span></span>

<span data-ttu-id="0db01-131">개발자는 아무 작업도 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-131">No action is required on the part of the developer.</span></span> <span data-ttu-id="0db01-132">하지만 NLS 세계화 API를 계속 사용하려는 경우 [런타임 스위치](../../../../docs/core/run-time-config/globalization.md#nls)를 설정하여 해당 동작으로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db01-132">However, if you wish to continue using NLS globalization APIs, you can set a [run-time switch](../../../../docs/core/run-time-config/globalization.md#nls) to revert to that behavior.</span></span> <span data-ttu-id="0db01-133">사용 가능한 스위치에 대한 자세한 내용은 [.NET 세계화 및 ICU](../../../../docs/standard/globalization-localization/globalization-icu.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0db01-133">For more information about the available switches, see the [.NET globalization and ICU](../../../../docs/standard/globalization-localization/globalization-icu.md) article.</span></span>

#### <a name="category"></a><span data-ttu-id="0db01-134">범주</span><span class="sxs-lookup"><span data-stu-id="0db01-134">Category</span></span>

- <span data-ttu-id="0db01-135">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="0db01-135">Core .NET libraries</span></span>
- <span data-ttu-id="0db01-136">전역화</span><span class="sxs-lookup"><span data-stu-id="0db01-136">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0db01-137">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0db01-137">Affected APIs</span></span>

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <span data-ttu-id="0db01-138"><xref:System.Globalization?displayProperty=fullName> 네임스페이스의 대부분의 형식</span><span class="sxs-lookup"><span data-stu-id="0db01-138">Most types in the <xref:System.Globalization?displayProperty=fullName> namespace</span></span>
- <span data-ttu-id="0db01-139"><xref:System.Array.Sort%2A?displayProperty=fullName>(문자열 배열을 정렬하는 경우)</span><span class="sxs-lookup"><span data-stu-id="0db01-139"><xref:System.Array.Sort%2A?displayProperty=fullName> (when sorting an array of strings)</span></span>
- <span data-ttu-id="0db01-140"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName>(목록 요소가 문자열인 경우)</span><span class="sxs-lookup"><span data-stu-id="0db01-140"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (when the list elements are strings)</span></span>
- <span data-ttu-id="0db01-141"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName>(키가 문자열인 경우)</span><span class="sxs-lookup"><span data-stu-id="0db01-141"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="0db01-142"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>(키가 문자열인 경우)</span><span class="sxs-lookup"><span data-stu-id="0db01-142"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="0db01-143"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName>(집합에 문자열이 포함된 경우)</span><span class="sxs-lookup"><span data-stu-id="0db01-143"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (when the set contains strings)</span></span>

<!--

#### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`
- `Overload:System.Array.Sort`
- ``M:System.Collections.Generic.List`1.Sort``
- ``T:System.Collections.Generic.SortedDictionary`2``
- ``T:System.Collections.Generic.SortedList`2``
- ``T:System.Collections.Generic.SortedSet`1``

-->
