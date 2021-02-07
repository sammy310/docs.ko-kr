---
description: '자세한 정보: 시작 설정 스키마'
title: 시작 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
- startup settings schema
- schema startup settings
- configuration schema [.NET Framework], startup settings
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
ms.openlocfilehash: 268b8d8dc2598add61435dd6b07031aa06831737
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726093"
---
# <a name="startup-settings-schema"></a><span data-ttu-id="2b3e8-103">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="2b3e8-103">Startup settings schema</span></span>

<span data-ttu-id="2b3e8-104">시작 설정은 애플리케이션을 실행해야 하는 공용 언어 런타임의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3e8-104">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="2b3e8-105">요소</span><span class="sxs-lookup"><span data-stu-id="2b3e8-105">Element</span></span>|<span data-ttu-id="2b3e8-106">설명</span><span class="sxs-lookup"><span data-stu-id="2b3e8-106">Description</span></span>|  
|-------------|-----------------|  
|[\<requiredRuntime>](requiredruntime-element.md)|<span data-ttu-id="2b3e8-107">애플리케이션에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3e8-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="2b3e8-108">런타임 버전 1.1로 빌드된 응용 프로그램은 요소를 사용 해야 합니다 **\<supportedRuntime>** .</span><span class="sxs-lookup"><span data-stu-id="2b3e8-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[\<supportedRuntime>](supportedruntime-element.md)|<span data-ttu-id="2b3e8-109">애플리케이션이 지원하는 공용 언어 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3e8-109">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[\<startup>](startup-element.md)|<span data-ttu-id="2b3e8-110">**\<requiredRuntime>** 및 요소를 포함 **\<supportedRuntime>** 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3e8-110">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b3e8-111">참조</span><span class="sxs-lookup"><span data-stu-id="2b3e8-111">See also</span></span>

- [<span data-ttu-id="2b3e8-112">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="2b3e8-112">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2b3e8-113">방법: .NET Framework 4 이상 버전을 지원하도록 앱 구성</span><span class="sxs-lookup"><span data-stu-id="2b3e8-113">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
