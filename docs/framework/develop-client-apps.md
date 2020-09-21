---
title: .NET Framework로 Windows 기반 클라이언트 애플리케이션 개발
description: .NET으로 Windows 기반 애플리케이션을 개발합니다. UWP(유니버설 Windows 플랫폼), WPF(Windows Presentation Foundation) 또는 Windows Forms를 사용할 수 있습니다.
ms.date: 01/09/2018
helpviewer_keywords:
- client application services
- applications [Windows Forms]
- Windows Presentation Foundation, in Visual Studio
- WPF, in Visual Studio
- Windows applications
- rich client applications
- .NET applications, Windows applications
- Visual Basic code, creating applications
- Visual C#, creating applications
- client/server applications, Windows applications
ms.assetid: 2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68
ms.openlocfilehash: 33d0ca2918e4e3b00e2b09f7a47c538bbe903dba
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547911"
---
# <a name="develop-client-applications-with-net-framework"></a><span data-ttu-id="ae0de-104">.NET Framework로 클라이언트 애플리케이션 개발</span><span class="sxs-lookup"><span data-stu-id="ae0de-104">Develop client applications with .NET Framework</span></span>

<span data-ttu-id="ae0de-105">.NET Framework를 사용하여 Windows 기반 애플리케이션을 개발하는 데는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0de-105">There are several ways to develop Windows-based applications with .NET Framework.</span></span> <span data-ttu-id="ae0de-106">이러한 도구 및 프레임워크 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0de-106">You can use any of these tools and frameworks:</span></span>

- [<span data-ttu-id="ae0de-107">UWP(유니버설 Windows 플랫폼)</span><span class="sxs-lookup"><span data-stu-id="ae0de-107">Universal Windows Platform (UWP)</span></span>](/windows/uwp/)
- [<span data-ttu-id="ae0de-108">WPF(Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="ae0de-108">Windows Presentation Foundation (WPF)</span></span>](/dotnet/desktop/wpf/)
- [<span data-ttu-id="ae0de-109">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae0de-109">Windows Forms</span></span>](/dotnet/desktop/winforms/)

<span data-ttu-id="ae0de-110">이 섹션에는 Windows Presentation Foundation 또는 Windows Forms를 사용하여 Windows 기반 애플리케이션을 만드는 방법을 설명하는 문서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0de-110">This section contains articles that describe how to create Windows-based applications by using Windows Presentation Foundation or Windows Forms.</span></span> <span data-ttu-id="ae0de-111">그러나 .NET Framework를 사용하여 웹 애플리케이션을 만들고 Microsoft Store를 통해 사용할 수 있는 컴퓨터 또는 디바이스용 클라이언트 애플리케이션(UWP 앱)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0de-111">However, you can also create web applications using .NET Framework and client applications for computers or devices that you make available through Microsoft Store (UWP apps).</span></span>

## <a name="related-sections"></a><span data-ttu-id="ae0de-112">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ae0de-112">Related sections</span></span>

<span data-ttu-id="ae0de-113">[유니버설 Windows 플랫폼](/windows/uwp/)</span><span class="sxs-lookup"><span data-stu-id="ae0de-113">[Universal Windows Platform](/windows/uwp/)</span></span>\
<span data-ttu-id="ae0de-114">Microsoft Store를 통해 사용자에게 제공할 수 있는 UWP 애플리케이션을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0de-114">Describes how to create UWP applications that you can make available to users through Microsoft Store.</span></span>

<span data-ttu-id="ae0de-115">[UWP 앱용 .NET API](../../api/index.md?view=dotnet-uwp-10.0)</span><span class="sxs-lookup"><span data-stu-id="ae0de-115">[.NET API for UWP apps](../../api/index.md?view=dotnet-uwp-10.0)</span></span>\
<span data-ttu-id="ae0de-116">UWP 앱을 지원하는 .NET 형식에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0de-116">Reference for .NET types that support UWP apps.</span></span>
  
<span data-ttu-id="ae0de-117">[여러 플랫폼용으로 개발](../standard/cross-platform/index.md)</span><span class="sxs-lookup"><span data-stu-id="ae0de-117">[Develop for Multiple Platforms](../standard/cross-platform/index.md)</span></span>\
<span data-ttu-id="ae0de-118">.NET Framework를 사용하여 여러 클라이언트 앱 형식을 대상으로 지정할 수 있는 다양한 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0de-118">Describes the different methods you can use .NET Framework to target multiple client app types.</span></span>

<span data-ttu-id="ae0de-119">[ASP.NET 웹 사이트 시작](https://dotnet.microsoft.com/apps/aspnet/web-apps)</span><span class="sxs-lookup"><span data-stu-id="ae0de-119">[Get Started with ASP.NET Web Sites](https://dotnet.microsoft.com/apps/aspnet/web-apps)</span></span>\
<span data-ttu-id="ae0de-120">ASP.NET을 사용하여 웹앱을 개발할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0de-120">Describes the ways you can develop web apps using ASP.NET.</span></span>

<span data-ttu-id="ae0de-121">[Windows Phone Silverlight용 .NET API](/previous-versions/windows/apps/jj207211\(v=vs.105\))</span><span class="sxs-lookup"><span data-stu-id="ae0de-121">[.NET API for Windows Phone Silverlight](/previous-versions/windows/apps/jj207211\(v=vs.105\))</span></span>\
<span data-ttu-id="ae0de-122">Windows Phone Silverlight로 앱을 빌드하는 데 사용할 수 있는 .NET Framework API를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0de-122">Lists .NET Framework APIs you can use for building apps with Windows Phone Silverlight.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae0de-123">참조</span><span class="sxs-lookup"><span data-stu-id="ae0de-123">See also</span></span>

- [<span data-ttu-id="ae0de-124">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="ae0de-124">.NET Standard</span></span>](../standard/net-standard.md)
- [<span data-ttu-id="ae0de-125">개요</span><span class="sxs-lookup"><span data-stu-id="ae0de-125">Overview</span></span>](./get-started/overview.md)
- [<span data-ttu-id="ae0de-126">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="ae0de-126">Development Guide</span></span>](./development-guide.md)
- [<span data-ttu-id="ae0de-127">Windows 서비스 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="ae0de-127">Windows Service Applications</span></span>](./windows-services/index.md)
