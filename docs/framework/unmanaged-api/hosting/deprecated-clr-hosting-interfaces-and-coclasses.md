---
title: 사용되지 않는 CLR 호스팅 인터페이스 및 Coclass
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 1
- .NET Framework 1.1, hosting interfaces
- hosting interfaces [.NET Framework], version 1
- .NET Framework 1.0, hosting interfaces
ms.assetid: 7b3d2755-cbab-4160-bc69-eb85791e38c7
ms.openlocfilehash: 8b90a33e2a0e6780a2ce908ff7ab251e94fbce90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673100"
---
# <a name="deprecated-clr-hosting-interfaces-and-coclasses"></a><span data-ttu-id="e6180-102">사용되지 않는 CLR 호스팅 인터페이스 및 Coclass</span><span class="sxs-lookup"><span data-stu-id="e6180-102">Deprecated CLR Hosting Interfaces and Coclasses</span></span>

<span data-ttu-id="e6180-103">이 섹션에서는 관리 되지 않는 호스트가 .NET Framework 버전 1.0 및 1.1의 CLR (공용 언어 런타임)을 해당 응용 프로그램에 통합 하는 데 사용할 수 있는 인터페이스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6180-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework versions 1.0 and 1.1 into their applications.</span></span> <span data-ttu-id="e6180-104">이러한 인터페이스는 호스트에서 런타임을 구성 하 고 프로세스로 로드 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6180-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e6180-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e6180-105">In This Section</span></span>  

 <span data-ttu-id="e6180-106">IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="e6180-106">IAppDomainSetup</span></span>  
 <span data-ttu-id="e6180-107">호스트가를 구성 하는 데 사용할 수 있는 메서드를 제공 합니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="e6180-107">Provides methods for the host to configure an <xref:System.AppDomain>.</span></span>  
  
 [<span data-ttu-id="e6180-108">ICeeFileGen 클래스</span><span class="sxs-lookup"><span data-stu-id="e6180-108">ICeeFileGen Class</span></span>](iceefilegen-class.md)  
 <span data-ttu-id="e6180-109">Mapi 네이티브 PE (이식 가능한 실행) 파일을 만드는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6180-109">(Deprecated) Provides functionality for creating a native portable executable (PE) file.</span></span>  
  
 [<span data-ttu-id="e6180-110">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6180-110">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)  
 <span data-ttu-id="e6180-111">호스트가 CLR 설정을 구성 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6180-111">Provides methods for the host to configure CLR settings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e6180-112">관련 단원</span><span class="sxs-lookup"><span data-stu-id="e6180-112">Related Sections</span></span>  

 [<span data-ttu-id="e6180-113">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6180-113">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)  
 <span data-ttu-id="e6180-114">.NET Framework 버전 2.0 이상 버전에서 제공 되는 호스팅 인터페이스에 대해 설명 하는 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6180-114">Contains topics that describe the hosting interfaces provided with the .NET Framework version 2.0 and later versions.</span></span>
