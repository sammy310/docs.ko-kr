---
title: 웹 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- ASP.NET configuration system, Web settings schema
- schema Web settings
- Web settings, schema [ASP.NET]
- configuration files [ASP.NET]
- configuration schema [.NET Framework], Web settings
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
ms.openlocfilehash: 1f0241b65c915dd5703ceea97dd5b07f88832003
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113063"
---
# <a name="web-settings-schema"></a><span data-ttu-id="ef9c0-102">웹 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ef9c0-102">Web Settings Schema</span></span>
<span data-ttu-id="ef9c0-103">웹 설정은 CPU와 ASP.NET 호스팅 계층에서 관리하는 프로세스 전반 동작에 적용되는 실행 수준 ASP.NET 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9c0-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="ef9c0-104">이러한 설정은 ASP.NET 애플리케이션의 Web.config 파일에서 지정된 애플리케이션 도메인 유형 설정과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ef9c0-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
 <span data-ttu-id="ef9c0-105">웹 설정은 .NET Framework의 버전 설치 폴더에 위치한 Aspnet.config 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef9c0-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="ef9c0-106">예를 들어 [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)]에 대한 Aspnet.config 파일은 다음 폴더에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9c0-106">For example, the Aspnet.config file for [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] is in the following folder:</span></span>  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 <span data-ttu-id="ef9c0-107">웹 설정은 machine.config 파일, 루트 Web.config 또는 애플리케이션 수준 Web.config 파일과 같은 다른 구성 파일에는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef9c0-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
 [<span data-ttu-id="ef9c0-108">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="ef9c0-108">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="ef9c0-109">\<system.web > 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="ef9c0-109">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [<span data-ttu-id="ef9c0-110">\<응용 프로그램 풀 > 요소 (웹 설정)</span><span class="sxs-lookup"><span data-stu-id="ef9c0-110">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|<span data-ttu-id="ef9c0-111">요소</span><span class="sxs-lookup"><span data-stu-id="ef9c0-111">Element</span></span>|<span data-ttu-id="ef9c0-112">설명</span><span class="sxs-lookup"><span data-stu-id="ef9c0-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef9c0-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="ef9c0-113">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="ef9c0-114">ASP.NET 호스팅 계층에서 사용하는 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef9c0-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="ef9c0-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="ef9c0-115">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="ef9c0-116">CPU와 ASP.NET 호스팅 계층에서 관리하는 프로세스 전반 동작에 적용되는 실행 수준 ASP.NET 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ef9c0-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef9c0-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="ef9c0-117">See also</span></span>

- [<span data-ttu-id="ef9c0-118">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ef9c0-118">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
