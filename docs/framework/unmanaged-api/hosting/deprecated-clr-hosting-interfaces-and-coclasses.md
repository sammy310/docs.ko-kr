---
title: 사용되지 않는 CLR 호스팅 인터페이스 및 Coclass
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 1
- .NET Framework 1.1, hosting interfaces
- hosting interfaces [.NET Framework], version 1
- .NET Framework 1.0, hosting interfaces
ms.assetid: 7b3d2755-cbab-4160-bc69-eb85791e38c7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f6c20a69894c95086dbd813601ac8811ab4f337
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985701"
---
# <a name="deprecated-clr-hosting-interfaces-and-coclasses"></a><span data-ttu-id="4fb27-102">사용되지 않는 CLR 호스팅 인터페이스 및 Coclass</span><span class="sxs-lookup"><span data-stu-id="4fb27-102">Deprecated CLR Hosting Interfaces and Coclasses</span></span>
<span data-ttu-id="4fb27-103">이 섹션에서는 관리 되지 않는 인터페이스를 설명 합니다. 호스트 응용 프로그램에.NET Framework 버전 1.0 및 1.1에에서는 CLR (공용 언어 런타임) 통합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb27-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework versions 1.0 and 1.1 into their applications.</span></span> <span data-ttu-id="4fb27-104">이러한 인터페이스는 구성 프로세스에 런타임을 로드 하는 호스트에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb27-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4fb27-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4fb27-105">In This Section</span></span>  
 <span data-ttu-id="4fb27-106">IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="4fb27-106">IAppDomainSetup</span></span>  
 <span data-ttu-id="4fb27-107">호스트를 구성 하는 데는 메서드를 제공는 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb27-107">Provides methods for the host to configure an <xref:System.AppDomain>.</span></span>  
  
 [<span data-ttu-id="4fb27-108">ICeeFileGen 클래스</span><span class="sxs-lookup"><span data-stu-id="4fb27-108">ICeeFileGen Class</span></span>](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)  
 <span data-ttu-id="4fb27-109">(사용 되지 않음) 기본 이식 가능한 실행 파일 (PE) 파일을 만들기 위한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb27-109">(Deprecated) Provides functionality for creating a native portable executable (PE) file.</span></span>  
  
 [<span data-ttu-id="4fb27-110">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fb27-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 <span data-ttu-id="4fb27-111">CLR 설정을 구성 하려면 호스트에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb27-111">Provides methods for the host to configure CLR settings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4fb27-112">관련 단원</span><span class="sxs-lookup"><span data-stu-id="4fb27-112">Related Sections</span></span>  
 [<span data-ttu-id="4fb27-113">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4fb27-113">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="4fb27-114">.NET Framework 버전 2.0 및 이후 버전을 사용 하 여 제공 하는 호스팅 인터페이스를 설명 하는 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb27-114">Contains topics that describe the hosting interfaces provided with the .NET Framework version 2.0 and later versions.</span></span>
