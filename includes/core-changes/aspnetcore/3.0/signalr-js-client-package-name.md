---
ms.openlocfilehash: f202b39f1a45f740625827be25e72df0e403d605
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901968"
---
### <a name="signalr-javascript-client-package-name-changed"></a><span data-ttu-id="77ed7-101">SignalR: JavaScript 클라이언트 패키지 이름이 변경됨</span><span class="sxs-lookup"><span data-stu-id="77ed7-101">SignalR: JavaScript client package name changed</span></span>

<span data-ttu-id="77ed7-102">ASP.NET Core 3.0 Preview 7에서 SignalR JavaScript 클라이언트 패키지 이름이 `@aspnet/signalr`에서 `@microsoft/signalr`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="77ed7-102">In ASP.NET Core 3.0 Preview 7, the SignalR JavaScript client package name changed from `@aspnet/signalr` to `@microsoft/signalr`.</span></span> <span data-ttu-id="77ed7-103">이름 변경은 Azure SignalR Service 덕분에 SignalR은 ASP.NET Core 앱 이상에서만 유용하다는 사실을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="77ed7-103">The name change reflects the fact that SignalR is useful in more than just ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

<span data-ttu-id="77ed7-104">이 변경에 대응하려면 *package.json* 파일, `require` 문 및 ECMAScript `import` 문에서 참조를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="77ed7-104">To react to this change, change references in your *package.json* files, `require` statements, and ECMAScript `import` statements.</span></span> <span data-ttu-id="77ed7-105">이 이름 바꾸기의 일부로 API가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77ed7-105">No API will change as part of this rename.</span></span>

<span data-ttu-id="77ed7-106">토론은 [dotnet/aspnetcore#11637](https://github.com/dotnet/aspnetcore/issues/11637)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77ed7-106">For discussion, see [dotnet/aspnetcore#11637](https://github.com/dotnet/aspnetcore/issues/11637).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="77ed7-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="77ed7-107">Version introduced</span></span>

<span data-ttu-id="77ed7-108">3.0</span><span class="sxs-lookup"><span data-stu-id="77ed7-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="77ed7-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="77ed7-109">Old behavior</span></span>

<span data-ttu-id="77ed7-110">클라이언트 패키지의 이름은 `@aspnet/signalr`이었습니다.</span><span class="sxs-lookup"><span data-stu-id="77ed7-110">The client package was named `@aspnet/signalr`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="77ed7-111">새 동작</span><span class="sxs-lookup"><span data-stu-id="77ed7-111">New behavior</span></span>

<span data-ttu-id="77ed7-112">클라이언트 패키지의 이름은 `@microsoft/signalr`입니다.</span><span class="sxs-lookup"><span data-stu-id="77ed7-112">The client package is named `@microsoft/signalr`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="77ed7-113">변경 이유</span><span class="sxs-lookup"><span data-stu-id="77ed7-113">Reason for change</span></span>

<span data-ttu-id="77ed7-114">이름 변경은 Azure SignalR Service 덕분에 SignalR은 ASP.NET Core 앱 이외에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="77ed7-114">The name change clarifies that SignalR is useful beyond ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="77ed7-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="77ed7-115">Recommended action</span></span>

<span data-ttu-id="77ed7-116">새 패키지 `@microsoft/signalr`로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="77ed7-116">Switch to the new package `@microsoft/signalr`.</span></span>

#### <a name="category"></a><span data-ttu-id="77ed7-117">범주</span><span class="sxs-lookup"><span data-stu-id="77ed7-117">Category</span></span>

<span data-ttu-id="77ed7-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="77ed7-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="77ed7-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="77ed7-119">Affected APIs</span></span>

<span data-ttu-id="77ed7-120">없음</span><span class="sxs-lookup"><span data-stu-id="77ed7-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
