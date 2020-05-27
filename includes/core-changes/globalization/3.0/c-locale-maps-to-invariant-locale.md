---
ms.openlocfilehash: c0551fa086644497c631cd9b6d7058398ff9ccfa
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702315"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a><span data-ttu-id="55929-101">"C" 로캘이 고정 로캘에 매핑됩니다</span><span class="sxs-lookup"><span data-stu-id="55929-101">"C" locale maps to the invariant locale</span></span>

<span data-ttu-id="55929-102">.NET Core 2.2 및 이전 버전은 "C" 로캘을 en_US_POSIX 로캘에 매핑하는 기본 ICU 동작에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="55929-102">.NET Core 2.2 and earlier versions depend on the default ICU behavior, which maps the "C" locale to the en_US_POSIX locale.</span></span> <span data-ttu-id="55929-103">en_US_POSIX 로캘은 대/소문자를 구분하지 않는 문자열 비교를 지원하지 않으므로 원치 않는 데이터 정렬 동작이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55929-103">The en_US_POSIX locale has an undesirable collation behavior, because it doesn't support case-insensitive string comparisons.</span></span> <span data-ttu-id="55929-104">일부 Linux 배포판에서는 "C" 로캘을 기본 로캘로 설정하므로 사용자가 예기치 않은 동작을 경험했습니다.</span><span class="sxs-lookup"><span data-stu-id="55929-104">Because some Linux distributions set the "C" locale as the default locale, users were experiencing unexpected behavior.</span></span>

#### <a name="change-description"></a><span data-ttu-id="55929-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="55929-105">Change description</span></span>

<span data-ttu-id="55929-106">.NET Core 3.0부터 "C" 로캘 매핑이 en_US_POSIX 대신 고정 로캘을 사용하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55929-106">Starting with .NET Core 3.0, the "C" locale mapping has changed to use the Invariant locale instead of en_US_POSIX.</span></span> <span data-ttu-id="55929-107">"C" 로캘의 고정 로캘 매핑은 일관성을 위해 Windows에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55929-107">The "C" locale to Invariant mapping is also applied to Windows for consistency.</span></span>

<span data-ttu-id="55929-108">en_US_POSIX는 대/소문자를 구분하지 않는 정렬/검색 문자열 작업을 지원하지 않기 때문에 "C"를 en_US_POSIX 문화권에 매핑 시 고객의 혼란이 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="55929-108">Mapping "C" to en_US_POSIX culture caused customer confusion, because en_US_POSIX doesn't support case insensitive sorting/searching string operations.</span></span> <span data-ttu-id="55929-109">"C" 로캘이 일부 Linux 배포판에서 기본 로캘로 사용되므로 고객이 이러한 운영 체제에서 이 원치 않는 동작을 경험했습니다.</span><span class="sxs-lookup"><span data-stu-id="55929-109">Because the "C" locale is used as a default locale in some of the Linux distros, customers experienced this undesired behavior on these operating systems.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="55929-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="55929-110">Version introduced</span></span>

<span data-ttu-id="55929-111">3.0</span><span class="sxs-lookup"><span data-stu-id="55929-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="55929-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="55929-112">Recommended action</span></span>

<span data-ttu-id="55929-113">이 변경 내용을 아는 것 외에 특별히 다른 것은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55929-113">Nothing specific more than the awareness of this change.</span></span> <span data-ttu-id="55929-114">이러한 변경 내용은 “C” 로캘을 사용하는 애플리케이션에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55929-114">This change affects only applications that use the "C" locale mapping.</span></span>

#### <a name="category"></a><span data-ttu-id="55929-115">범주</span><span class="sxs-lookup"><span data-stu-id="55929-115">Category</span></span>

<span data-ttu-id="55929-116">전역화</span><span class="sxs-lookup"><span data-stu-id="55929-116">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="55929-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="55929-117">Affected APIs</span></span>

<span data-ttu-id="55929-118">모든 데이터 정렬 및 문화권 API는 이 변경 내용의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="55929-118">All collation and culture APIs are affected by this change.</span></span>

<!--

#### Affected APIs

-->
