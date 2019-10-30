---
title: Windows 스토어 앱용 .NET을 위한 MEF
ms.date: 03/30/2017
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
ms.openlocfilehash: dafa6ddcd55940ea9bab61b79b6ab77896a1916f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126356"
---
# <a name="mef-for-net-for-windows-store-apps"></a><span data-ttu-id="213da-102">Windows 스토어 앱용 .NET을 위한 MEF</span><span class="sxs-lookup"><span data-stu-id="213da-102">MEF for .NET for Windows Store Apps</span></span>
<span data-ttu-id="213da-103"><xref:System.Composition?displayProperty=nameWithType> 및 자식 네임스페이스에는 MEF(Managed Extensibility Framework)를 사용하여 확장 가능한 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱을 개발하기 위한 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="213da-103"><xref:System.Composition?displayProperty=nameWithType> and its child namespaces contain types for developing extensible [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps with Managed Extensibility Framework (MEF).</span></span> <span data-ttu-id="213da-104">이러한 네임스페이스는 [!INCLUDE[win8](../../../includes/win8-md.md)] 운영 체제에 대한 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] 하위 집합의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="213da-104">These namespaces are part of the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] subset for the [!INCLUDE[win8](../../../includes/win8-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="213da-105">이 네임스페이스는 .NET Framework와 함께 배포되는 핵심 클래스 라이브러리의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="213da-105">These namespaces are not part of the core class library distributed with the .NET Framework.</span></span> <span data-ttu-id="213da-106">이 네임스페이스를 설치하려면 Visual Studio에서 프로젝트를 열고 **프로젝트** 메뉴에서 **NuGet 패키지 관리**를 선택한 다음, Microsoft.Composition 패키지를 온라인으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="213da-106">To install these namespaces, open your project in Visual Studio, choose **Manage NuGet Packages** from the **Project** menu, and search online for the Microsoft.Composition package.</span></span>  
  
- <span data-ttu-id="213da-107"><xref:System.Composition?displayProperty=nameWithType>은 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 앱용 핵심 MEF를 구성하는 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="213da-107"><xref:System.Composition?displayProperty=nameWithType> provides classes that constitute the core MEF for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
- <span data-ttu-id="213da-108"><xref:System.Composition.Convention?displayProperty=nameWithType>은 규칙 기반 구성 모델에서 MEF 사용을 지원하는 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="213da-108"><xref:System.Composition.Convention?displayProperty=nameWithType> provides types that support using MEF with a convention-based configuration model.</span></span>  
  
- <span data-ttu-id="213da-109"><xref:System.Composition.Hosting?displayProperty=nameWithType>은 호스트 애플리케이션 개발자에게 유용한 MEF 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="213da-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> provides MEF types that are useful to developers of host applications.</span></span>  
  
- <span data-ttu-id="213da-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType>은 컴포지션 엔진에서 내부적으로 사용되는 MEF 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="213da-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> provides MEF types used internally by the composition engine.</span></span>  
  
 <span data-ttu-id="213da-111">[!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] 및 여기에 포함된 네임스페이스 및 형식 목록에 대한 자세한 내용은 Windows 개발자 센터의 [Windows 스토어 앱용 .NET 개요](https://go.microsoft.com/fwlink/p/?LinkID=238312)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="213da-111">For more information about [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] and a list of namespaces and types that it contains, see [.NET for Windows Store apps overview](https://go.microsoft.com/fwlink/p/?LinkID=238312) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="213da-112">참조</span><span class="sxs-lookup"><span data-stu-id="213da-112">See also</span></span>

- [<span data-ttu-id="213da-113">Windows 스토어 앱용 .NET 개요</span><span class="sxs-lookup"><span data-stu-id="213da-113">.NET for Windows Store apps overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=238312)
- [<span data-ttu-id="213da-114">Windows 스토어 앱용 .NET – 지원되는 API</span><span class="sxs-lookup"><span data-stu-id="213da-114">.NET for Windows Store apps – supported APIs</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=247912)
- [<span data-ttu-id="213da-115">MEF(Managed Extensibility Framework)</span><span class="sxs-lookup"><span data-stu-id="213da-115">Managed Extensibility Framework (MEF)</span></span>](index.md)
