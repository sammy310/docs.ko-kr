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
ms.openlocfilehash: 71b9e46a8c2d60c853af63ee78e2ed5dbe6e98f4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699142"
---
# <a name="web-settings-schema"></a><span data-ttu-id="6f2db-102">웹 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="6f2db-102">Web Settings Schema</span></span>
<span data-ttu-id="6f2db-103">웹 설정은 CPU와 ASP.NET 호스팅 계층에서 관리하는 프로세스 전반 동작에 적용되는 실행 수준 ASP.NET 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2db-103">Web settings specify CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span> <span data-ttu-id="6f2db-104">이러한 설정은 ASP.NET 애플리케이션의 Web.config 파일에서 지정된 애플리케이션 도메인 유형 설정과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6f2db-104">These settings differ from application domain-type settings that are specified in the Web.config file of an ASP.NET application.</span></span>  
  
<span data-ttu-id="6f2db-105">웹 설정은 .NET Framework의 버전 설치 폴더에 위치한 Aspnet.config 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f2db-105">Web settings are contained in Aspnet.config files, which are located in the installation folders for versions of the .NET Framework.</span></span> <span data-ttu-id="6f2db-106">예를 들어 .NET Framework 2.0에 대 한 Aspnet .config 파일은 다음 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2db-106">For example, the Aspnet.config file for .NET Framework 2.0 is in the following folder:</span></span>  
  
`C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
<span data-ttu-id="6f2db-107">웹 설정은 machine.config 파일, 루트 Web.config 또는 애플리케이션 수준 Web.config 파일과 같은 다른 구성 파일에는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2db-107">Web settings are not used in any other configuration files such as the machine.config file, the root Web.config, or application-level Web.config files.</span></span>  
  
[<span data-ttu-id="6f2db-108"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="6f2db-108">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="6f2db-109">&nbsp; @ no__t-1[ **@no__t >** ](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6f2db-109">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="6f2db-110">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<applicationPool >** ](applicationpool-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6f2db-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<applicationPool>**](applicationpool-element-web-settings.md)</span></span>  
  
|<span data-ttu-id="6f2db-111">요소</span><span class="sxs-lookup"><span data-stu-id="6f2db-111">Element</span></span>|<span data-ttu-id="6f2db-112">설명</span><span class="sxs-lookup"><span data-stu-id="6f2db-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f2db-113">\<system.web></span><span class="sxs-lookup"><span data-stu-id="6f2db-113">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="6f2db-114">ASP.NET 호스팅 계층에서 사용하는 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f2db-114">Contains information that the ASP.NET hosting layer uses.</span></span>|  
|[<span data-ttu-id="6f2db-115">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="6f2db-115">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="6f2db-116">CPU와 ASP.NET 호스팅 계층에서 관리하는 프로세스 전반 동작에 적용되는 실행 수준 ASP.NET 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2db-116">Specifies CPU and execution-level ASP.NET settings that apply to process-wide behavior managed by the ASP.NET hosting layer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f2db-117">참조</span><span class="sxs-lookup"><span data-stu-id="6f2db-117">See also</span></span>

- [<span data-ttu-id="6f2db-118">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="6f2db-118">Configuration File Schema</span></span>](../index.md)
