---
ms.openlocfilehash: 6f8e6d2786d20e055c9bef63891db4d6f88bc64b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901890"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a><span data-ttu-id="4c625-101">ID: SignInManager 생성자는 새 매개 변수를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c625-101">Identity: SignInManager constructor accepts new parameter</span></span>

<span data-ttu-id="4c625-102">ASP.NET Core 3.0부터 새 `IUserConfirmation<TUser>` 매개 변수가 `SignInManager` 생성자에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4c625-102">Starting with ASP.NET Core 3.0, a new `IUserConfirmation<TUser>` parameter was added to the `SignInManager` constructor.</span></span> <span data-ttu-id="4c625-103">자세한 내용은 [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c625-103">For more information, see [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4c625-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="4c625-104">Version introduced</span></span>

<span data-ttu-id="4c625-105">3.0</span><span class="sxs-lookup"><span data-stu-id="4c625-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="4c625-106">변경 이유</span><span class="sxs-lookup"><span data-stu-id="4c625-106">Reason for change</span></span>

<span data-ttu-id="4c625-107">변경에 대한 동기는 ID에 새 이메일/확인 흐름에 대한 지원을 추가하는 것이었습니다.</span><span class="sxs-lookup"><span data-stu-id="4c625-107">The motivation for the change was to add support for new email / confirmation flows in Identity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4c625-108">권장 조치</span><span class="sxs-lookup"><span data-stu-id="4c625-108">Recommended action</span></span>

<span data-ttu-id="4c625-109">`SignInManager`를 수동으로 구성하는 경우 `IUserConfirmation`의 구현을 제공하거나 종속성 주입에서 하나를 가져와 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c625-109">If manually constructing a `SignInManager`, provide an implementation of `IUserConfirmation` or grab one from dependency injection to provide.</span></span>

#### <a name="category"></a><span data-ttu-id="4c625-110">범주</span><span class="sxs-lookup"><span data-stu-id="4c625-110">Category</span></span>

<span data-ttu-id="4c625-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4c625-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4c625-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="4c625-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
