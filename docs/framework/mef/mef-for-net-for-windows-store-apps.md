---
title: Windows 스토어 앱용 .NET을 위한 MEF
description: 확장 가능한 Windows 8.x 스토어 앱을 개발하기 위한 형식을 포함하는 MEF(Managed Extensibility Framework) 네임스페이스에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
ms.openlocfilehash: 1bd62ad0b405f84952aca9d527c5f8a8e9f744f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276596"
---
# <a name="mef-for-net-for-windows-store-apps"></a><span data-ttu-id="5f8d7-103">Windows 스토어 앱용 .NET을 위한 MEF</span><span class="sxs-lookup"><span data-stu-id="5f8d7-103">MEF for .NET for Windows Store Apps</span></span>

<span data-ttu-id="5f8d7-104"><xref:System.Composition?displayProperty=nameWithType> 및 자식 네임스페이스에는 MEF(Managed Extensibility Framework)를 사용하여 확장 가능한 Windows 8.x 스토어 앱을 개발하기 위한 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d7-104"><xref:System.Composition?displayProperty=nameWithType> and its child namespaces contain types for developing extensible Windows 8.x Store apps with Managed Extensibility Framework (MEF).</span></span> <span data-ttu-id="5f8d7-105">이러한 네임스페이스는 Windows 8 운영 체제의 Windows 8.x 스토어 앱용 .NET 하위 집합의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d7-105">These namespaces are part of the .NET for Windows 8.x Store apps subset for the Windows 8 operating system.</span></span>  
  
 <span data-ttu-id="5f8d7-106">이 네임스페이스는 .NET Framework와 함께 배포되는 핵심 클래스 라이브러리의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d7-106">These namespaces are not part of the core class library distributed with the .NET Framework.</span></span> <span data-ttu-id="5f8d7-107">이 네임스페이스를 설치하려면 Visual Studio에서 프로젝트를 열고 **프로젝트** 메뉴에서 **NuGet 패키지 관리** 를 선택한 다음, Microsoft.Composition 패키지를 온라인으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d7-107">To install these namespaces, open your project in Visual Studio, choose **Manage NuGet Packages** from the **Project** menu, and search online for the Microsoft.Composition package.</span></span>  
  
- <span data-ttu-id="5f8d7-108"><xref:System.Composition?displayProperty=nameWithType>은 Windows 8.x 스토어 앱용 핵심 MEF를 구성하는 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d7-108"><xref:System.Composition?displayProperty=nameWithType> provides classes that constitute the core MEF for Windows 8.x Store apps.</span></span>  
  
- <span data-ttu-id="5f8d7-109"><xref:System.Composition.Convention?displayProperty=nameWithType>은 규칙 기반 구성 모델에서 MEF 사용을 지원하는 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d7-109"><xref:System.Composition.Convention?displayProperty=nameWithType> provides types that support using MEF with a convention-based configuration model.</span></span>  
  
- <span data-ttu-id="5f8d7-110"><xref:System.Composition.Hosting?displayProperty=nameWithType>은 호스트 애플리케이션 개발자에게 유용한 MEF 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d7-110"><xref:System.Composition.Hosting?displayProperty=nameWithType> provides MEF types that are useful to developers of host applications.</span></span>  
  
- <span data-ttu-id="5f8d7-111"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType>은 컴포지션 엔진에서 내부적으로 사용되는 MEF 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f8d7-111"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> provides MEF types used internally by the composition engine.</span></span>  
  
 <span data-ttu-id="5f8d7-112">Windows 8.x 스토어 앱용.NET 및 여기에 포함된 네임스페이스 및 형식 목록에 대한 자세한 내용은 [Windows 스토어 앱용 .NET 개요](/previous-versions/br230302(v=vs.110))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f8d7-112">For more information about .NET for Windows 8.x Store apps and a list of namespaces and types that it contains, see [.NET for Windows Store apps overview](/previous-versions/br230302(v=vs.110)).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5f8d7-113">참조</span><span class="sxs-lookup"><span data-stu-id="5f8d7-113">See also</span></span>

- <span data-ttu-id="5f8d7-114">[Windows 스토어 앱용 .NET 개요](/previous-versions/br230302(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="5f8d7-114">[.NET for Windows Store apps overview](/previous-versions/br230302(v=vs.110))</span></span>
- <span data-ttu-id="5f8d7-115">[Windows 스토어 앱용 .NET – 지원되는 API](/previous-versions/br230232(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="5f8d7-115">[.NET for Windows Store apps – supported APIs](/previous-versions/br230232(v=vs.110))</span></span>
- [<span data-ttu-id="5f8d7-116">MEF(Managed Extensibility Framework)</span><span class="sxs-lookup"><span data-stu-id="5f8d7-116">Managed Extensibility Framework (MEF)</span></span>](index.md)
