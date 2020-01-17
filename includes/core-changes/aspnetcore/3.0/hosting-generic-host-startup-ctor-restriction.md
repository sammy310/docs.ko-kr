---
ms.openlocfilehash: d1ddba72ce25c5e01025d916d52f785b5a1a9e71
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901661"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a><span data-ttu-id="6ec38-101">호스팅: 제네릭 호스트는 시작 생성자 주입을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-101">Hosting: Generic host restricts Startup constructor injection</span></span>

<span data-ttu-id="6ec38-102">제네릭 호스트가 `Startup` 클래스 생성자 주입을 지원하는 형식은 `IHostEnvironment`, `IWebHostEnvironment` 및 `IConfiguration`뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-102">The only types the generic host supports for `Startup` class constructor injection are `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration`.</span></span> <span data-ttu-id="6ec38-103">`WebHost`를 사용하는 앱은 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-103">Apps using `WebHost` are unaffected.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6ec38-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="6ec38-104">Change description</span></span>

<span data-ttu-id="6ec38-105">ASP.NET Core 3.0 이전에는 `Startup` 클래스의 생성자에 있는 임의 형식에 생성자 주입을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-105">Prior to ASP.NET Core 3.0, constructor injection could be used for arbitrary types in the `Startup` class's constructor.</span></span> <span data-ttu-id="6ec38-106">ASP.NET Core 3.0에서는 웹 스택이 제네릭 호스트 라이브러리로 다시 플랫폼화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-106">In ASP.NET Core 3.0, the web stack was replatformed onto the generic host library.</span></span> <span data-ttu-id="6ec38-107">템플릿의 *Program.cs* 파일에서 변경 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-107">You can see the change in the *Program.cs* file of the templates:</span></span>

<span data-ttu-id="6ec38-108">**ASP.NET Core 2.x:**</span><span class="sxs-lookup"><span data-stu-id="6ec38-108">**ASP.NET Core 2.x:**</span></span>

<https://github.com/dotnet/aspnetcore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

<span data-ttu-id="6ec38-109">**ASP.NET Core 3.0:**</span><span class="sxs-lookup"><span data-stu-id="6ec38-109">**ASP.NET Core 3.0:**</span></span>

<https://github.com/dotnet/aspnetcore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

<span data-ttu-id="6ec38-110">`Host`는 하나의 DI(종속성 주입) 컨테이너를 사용하여 앱을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-110">`Host` uses one dependency injection (DI) container to build the app.</span></span> <span data-ttu-id="6ec38-111">`WebHost`는 두 개의 컨테이너(호스트용과 앱용)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-111">`WebHost` uses two containers: one for the host and one for the app.</span></span> <span data-ttu-id="6ec38-112">따라서 `Startup` 생성자는 더 이상 사용자 지정 서비스 주입을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-112">As a result, the `Startup` constructor no longer supports custom service injection.</span></span> <span data-ttu-id="6ec38-113">`IHostEnvironment`, `IWebHostEnvironment` 및 `IConfiguration`만 주입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-113">Only `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration` can be injected.</span></span> <span data-ttu-id="6ec38-114">이 변경으로 인해 싱글톤 서비스의 중복 만들기와 같은 DI 문제가 방지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-114">This change prevents DI issues such as the duplicate creation of a singleton service.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6ec38-115">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="6ec38-115">Version introduced</span></span>

<span data-ttu-id="6ec38-116">3.0</span><span class="sxs-lookup"><span data-stu-id="6ec38-116">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6ec38-117">변경 이유</span><span class="sxs-lookup"><span data-stu-id="6ec38-117">Reason for change</span></span>

<span data-ttu-id="6ec38-118">이 변경 내용은 웹 스택을 제네릭 호스트 라이브러리로 다시 플랫폼화한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-118">This change is a consequence of replatforming the web stack onto the generic host library.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6ec38-119">권장 조치</span><span class="sxs-lookup"><span data-stu-id="6ec38-119">Recommended action</span></span>

<span data-ttu-id="6ec38-120">`Startup.Configure` 메서드 서명에 서비스를 주입합니다.</span><span class="sxs-lookup"><span data-stu-id="6ec38-120">Inject services into the `Startup.Configure` method signature.</span></span> <span data-ttu-id="6ec38-121">예:</span><span class="sxs-lookup"><span data-stu-id="6ec38-121">For example:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a><span data-ttu-id="6ec38-122">범주</span><span class="sxs-lookup"><span data-stu-id="6ec38-122">Category</span></span>

<span data-ttu-id="6ec38-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6ec38-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6ec38-124">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6ec38-124">Affected APIs</span></span>

<span data-ttu-id="6ec38-125">없음</span><span class="sxs-lookup"><span data-stu-id="6ec38-125">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
