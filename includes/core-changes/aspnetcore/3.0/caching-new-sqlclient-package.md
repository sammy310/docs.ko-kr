---
ms.openlocfilehash: 771238c53dc97f4cf4068968f3c68500ba9f87da
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032480"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a><span data-ttu-id="0b152-101">캐싱: Microsoft.Extensions.Caching.SqlServer는 새 SqlClient 패키지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b152-101">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>

<span data-ttu-id="0b152-102">`Microsoft.Extensions.Caching.SqlServer` 패키지는 `System.Data.SqlClient` 패키지 대신 새 `Microsoft.Data.SqlClient` 패키지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b152-102">The `Microsoft.Extensions.Caching.SqlServer` package will use the new `Microsoft.Data.SqlClient` package instead of `System.Data.SqlClient` package.</span></span> <span data-ttu-id="0b152-103">이 변경으로 인해 약간의 동작이 크게 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b152-103">This change could cause slight behavioral breaking changes.</span></span> <span data-ttu-id="0b152-104">자세한 내용은 [새 Microsoft.Data.SqlClient 소개](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b152-104">For more information, see [Introducing the new Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0b152-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0b152-105">Version introduced</span></span>

<span data-ttu-id="0b152-106">3.0</span><span class="sxs-lookup"><span data-stu-id="0b152-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="0b152-107">이전 동작</span><span class="sxs-lookup"><span data-stu-id="0b152-107">Old behavior</span></span>

<span data-ttu-id="0b152-108">`Microsoft.Extensions.Caching.SqlServer` 패키지는 `System.Data.SqlClient` 패키지를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b152-108">The `Microsoft.Extensions.Caching.SqlServer` package used the `System.Data.SqlClient` package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="0b152-109">새 동작</span><span class="sxs-lookup"><span data-stu-id="0b152-109">New behavior</span></span>

<span data-ttu-id="0b152-110">`Microsoft.Extensions.Caching.SqlServer`가 현재 `Microsoft.Data.SqlClient` 패키지를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b152-110">`Microsoft.Extensions.Caching.SqlServer` is now using the `Microsoft.Data.SqlClient` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0b152-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="0b152-111">Reason for change</span></span>

<span data-ttu-id="0b152-112">`Microsoft.Data.SqlClient`는 `System.Data.SqlClient`에서 빌드된 새 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="0b152-112">`Microsoft.Data.SqlClient` is a new package that is built off of `System.Data.SqlClient`.</span></span> <span data-ttu-id="0b152-113">이제부터 모든 새 기능 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b152-113">It's where all new feature work will be done from now on.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0b152-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="0b152-114">Recommended action</span></span>

<span data-ttu-id="0b152-115">고객은 `Microsoft.Extensions.Caching.SqlServer` 패키지에서 반환된 형식을 사용하고 `System.Data.SqlClient` 형식으로 캐스팅하지 않는 한 이러한 호환성이 손상되는 변경에 대해 걱정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b152-115">Customers shouldn't need to worry about this breaking change unless they were using types returned by the `Microsoft.Extensions.Caching.SqlServer` package and casting them to `System.Data.SqlClient` types.</span></span> <span data-ttu-id="0b152-116">예를 들어 다른 사용자가 `DbConnection`을 [이전 SqlConnection 형식](xref:System.Data.SqlClient.SqlConnection)으로 캐스팅하는 경우 캐스팅을 새 `Microsoft.Data.SqlClient.SqlConnection` 형식으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b152-116">For example, if someone was casting a `DbConnection` to the [old SqlConnection type](xref:System.Data.SqlClient.SqlConnection), they would need to change the cast to the new `Microsoft.Data.SqlClient.SqlConnection` type.</span></span>

#### <a name="category"></a><span data-ttu-id="0b152-117">범주</span><span class="sxs-lookup"><span data-stu-id="0b152-117">Category</span></span>

<span data-ttu-id="0b152-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0b152-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0b152-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0b152-119">Affected APIs</span></span>

<span data-ttu-id="0b152-120">없음</span><span class="sxs-lookup"><span data-stu-id="0b152-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
