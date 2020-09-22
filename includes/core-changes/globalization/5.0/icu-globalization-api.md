---
ms.openlocfilehash: 18718ebc934e0175c20411055b8c0a90ef6b175f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539489"
---
### <a name="globalization-apis-use-icu-libraries-on-windows"></a><span data-ttu-id="f4160-101">Windows에서 세계화 API가 ICU 라이브러리를 사용</span><span class="sxs-lookup"><span data-stu-id="f4160-101">Globalization APIs use ICU libraries on Windows</span></span>

<span data-ttu-id="f4160-102">.NET 5.0 이상 버전에서는 Windows 10 2019년 5월 업데이트 이상에서 실행되는 경우 세계화 기능에 [ICU(International Components for Unicode)](http://site.icu-project.org/home) 라이브러리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4160-102">.NET 5.0 and later versions use [International Components for Unicode (ICU)](http://site.icu-project.org/home) libraries for globalization functionality when running on Windows 10 May 2019 Update or later.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f4160-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="f4160-103">Change description</span></span>

<span data-ttu-id="f4160-104">이전에는 .NET 라이브러리가 세계화 기능에 [NLS(국가별 언어 지원)](/windows/win32/intl/national-language-support) API를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="f4160-104">Previously, .NET libraries used [National Language Support (NLS)](/windows/win32/intl/national-language-support) APIs for globalization functionality.</span></span> <span data-ttu-id="f4160-105">예를 들어, NLS 함수는 날짜 및 시간 형식 패턴, 문자열 비교, 해당 문화권에서 문자열 대/소문자 구분 등의 문화권 데이터를 가져오는 데 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f4160-105">For example, NLS functions were used to get culture data, such as date and time format patterns, compare strings, and perform string casing in the appropriate culture.</span></span>

<span data-ttu-id="f4160-106">.NET 5.0부터 앱이 Windows 10 2019년 5월 업데이트 이상에서 실행되는 경우 .NET 라이브러리가 [ICU](http://site.icu-project.org/home) 세계화 API를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4160-106">Starting in .NET 5.0, if an app is running on Windows 10 May 2019 Update or later, .NET libraries use [ICU](http://site.icu-project.org/home) globalization APIs.</span></span> <span data-ttu-id="f4160-107">Windows 10 2019년 5월 업데이트 이상 버전에는 ICU 네이티브 라이브러리가 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4160-107">Windows 10 May 2019 Update and later versions ship with the ICU native library.</span></span> <span data-ttu-id="f4160-108">.NET 런타임에서 ICU를 로드할 수 없는 경우 대신 NLS를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4160-108">If the .NET runtime can't load ICU, it uses NLS instead.</span></span>

<span data-ttu-id="f4160-109">이러한 변경 내용은 다음 두 가지 이유로 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f4160-109">This change was introduced for two reasons:</span></span>

- <span data-ttu-id="f4160-110">앱은 Linux, macOS 및 Windows를 비롯한 여러 플랫폼에서 동일한 세계화 동작을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f4160-110">Apps have the same globalization behavior across platforms, including Linux, macOS, and Windows.</span></span>
- <span data-ttu-id="f4160-111">앱은 사용자 지정 ICU 라이브러리를 사용하여 세계화 동작을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4160-111">Apps can control globalization behavior by using custom ICU libraries.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f4160-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="f4160-112">Version introduced</span></span>

<span data-ttu-id="f4160-113">.NET 5.0 미리 보기 4</span><span class="sxs-lookup"><span data-stu-id="f4160-113">.NET 5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f4160-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="f4160-114">Recommended action</span></span>

<span data-ttu-id="f4160-115">개발자는 아무 작업도 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4160-115">No action is required on the part of the developer.</span></span> <span data-ttu-id="f4160-116">하지만 NLS 세계화 API를 계속 사용하려는 경우 [런타임 스위치](../../../../docs/core/run-time-config/globalization.md#nls)를 설정하여 해당 동작으로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4160-116">However, if you wish to continue using NLS globalization APIs, you can set a [run-time switch](../../../../docs/core/run-time-config/globalization.md#nls) to revert to that behavior.</span></span> <span data-ttu-id="f4160-117">사용 가능한 스위치에 대한 자세한 내용은 [.NET 세계화 및 ICU](../../../../docs/standard/globalization-localization/globalization-icu.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4160-117">For more information about the available switches, see the [.NET globalization and ICU](../../../../docs/standard/globalization-localization/globalization-icu.md) article.</span></span>

#### <a name="category"></a><span data-ttu-id="f4160-118">범주</span><span class="sxs-lookup"><span data-stu-id="f4160-118">Category</span></span>

<span data-ttu-id="f4160-119">전역화</span><span class="sxs-lookup"><span data-stu-id="f4160-119">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f4160-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f4160-120">Affected APIs</span></span>

- <xref:System.Span%601?displayProperty=fullName>
- <xref:System.String?displayProperty=fullName>
- <span data-ttu-id="f4160-121"><xref:System.Globalization?displayProperty=fullName> 네임스페이스의 대부분의 형식</span><span class="sxs-lookup"><span data-stu-id="f4160-121">Most types in the <xref:System.Globalization?displayProperty=fullName> namespace</span></span>

<!--

#### Affected APIs

- ``T:System.Span`1``
- `T:System.String`
- `N:System.Globalization`

-->
