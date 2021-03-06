---
title: ASP.NET MVC와 ASP.NET Core 간의 호스팅 차이점
description: ASP.NET MVC 앱을 호스트 하는 방법 및 ASP.NET Core 앱 간의 차이점에 대 한 개요입니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 402dd5782cb215545ff2ef13f97ec269b8a2540b
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401766"
---
# <a name="hosting-differences-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="28696-103">ASP.NET MVC와 ASP.NET Core 간의 호스팅 차이점</span><span class="sxs-lookup"><span data-stu-id="28696-103">Hosting differences between ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="28696-104">ASP.NET MVC 앱은 IIS에서 호스팅되며 IIS 구성을 사용 하 여 해당 동작을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28696-104">ASP.NET MVC apps are hosted in IIS, and may rely on IIS configuration for their behavior.</span></span> <span data-ttu-id="28696-105">여기에는 종종 [IIS 모듈이](/iis/get-started/introduction-to-iis/iis-modules-overview)포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28696-105">This often includes [IIS modules](/iis/get-started/introduction-to-iis/iis-modules-overview).</span></span> <span data-ttu-id="28696-106">앱을 검토 하 여 ASP.NET MVC에서 ASP.NET Core로 이식할 수 있도록 준비 하는 과정에서 팀은 해당 서버에 설치 된 IIS 모듈 목록에서 사용 중인 모듈 (있는 경우)을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28696-106">As part of reviewing an app to prepare to port it from ASP.NET MVC to ASP.NET Core, teams should identify which modules, if any, they're using from the list of IIS Modules installed on their server.</span></span>

<span data-ttu-id="28696-107">[ASP.NET Core 앱은 다양 한 서버에서 실행할 수 있습니다](/aspnet/core/fundamentals/servers/).</span><span class="sxs-lookup"><span data-stu-id="28696-107">[ASP.NET Core apps can run on a number of different servers](/aspnet/core/fundamentals/servers/).</span></span> <span data-ttu-id="28696-108">기본 플랫폼 간 서버 Kestrel을 선택 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="28696-108">The default cross platform server, Kestrel, is a good default choice.</span></span> <span data-ttu-id="28696-109">Kestrel에서 실행 되는 앱은 별도의 프로세스로 실행 되는 IIS에서 호스팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28696-109">Apps running in Kestrel can be hosted by IIS, running in a separate process.</span></span> <span data-ttu-id="28696-110">Windows에서 응용 프로그램은 IIS에서 또는 HTTP.sys를 사용 하 여 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28696-110">On Windows, apps can also run in process on IIS or using HTTP.sys.</span></span> <span data-ttu-id="28696-111">최상의 성능을 위해 일반적으로 Kestrel을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="28696-111">Kestrel is generally recommended for best performance.</span></span> <span data-ttu-id="28696-112">앱이 인터넷에 노출되고 필수 기능이 Kestrel이 아닌 HTTP.sys에서 지원되는 시나리오에서 HTTP.sys를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28696-112">HTTP.sys can be used in scenarios where the app is exposed to the Internet and required capabilities are supported by HTTP.sys but not Kestrel.</span></span>

<span data-ttu-id="28696-113">Kestrel에는 iis 모듈에 해당 하는 기능이 없습니다. IIS에서 호스팅되는 앱은 IIS 모듈을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28696-113">Kestrel does not have an equivalent to IIS modules (though apps hosted in IIS can still take advantage of IIS modules).</span></span> <span data-ttu-id="28696-114">동일한 동작을 수행 하기 위해 ASP.NET Core 앱 자체에서 구성 된 미들웨어가 일반적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28696-114">To achieve equivalent behavior, middleware configured in the ASP.NET Core app itself is typically used.</span></span>

## <a name="references"></a><span data-ttu-id="28696-115">참조</span><span class="sxs-lookup"><span data-stu-id="28696-115">References</span></span>

- [<span data-ttu-id="28696-116">IIS 모듈</span><span class="sxs-lookup"><span data-stu-id="28696-116">IIS Modules</span></span>](/iis/get-started/introduction-to-iis/iis-modules-overview)
- [<span data-ttu-id="28696-117">ASP.NET Core 서버</span><span class="sxs-lookup"><span data-stu-id="28696-117">ASP.NET Core Servers</span></span>](/aspnet/core/fundamentals/servers/)

>[!div class="step-by-step"]
><span data-ttu-id="28696-118">[이전](app-startup-differences.md)
>[다음](serving-static-files.md)</span><span class="sxs-lookup"><span data-stu-id="28696-118">[Previous](app-startup-differences.md)
[Next](serving-static-files.md)</span></span>
