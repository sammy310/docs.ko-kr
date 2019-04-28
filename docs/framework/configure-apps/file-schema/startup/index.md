---
title: 시작 설정 스키마
ms.date: 03/30/2017
helpviewer_keywords:
  - startup settings schema
  - schema startup settings
  - 'configuration schema [.NET Framework], startup settings'
ms.assetid: 03de6972-442a-4648-9f3e-efa654e3b949
---
# <a name="startup-settings-schema"></a><span data-ttu-id="a58f8-102">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="a58f8-102">Startup settings schema</span></span>

<span data-ttu-id="a58f8-103">시작 설정은 애플리케이션을 실행해야 하는 공용 언어 런타임의 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f8-103">Startup settings specify the version of the common language runtime that should run the application.</span></span>  
  
|<span data-ttu-id="a58f8-104">요소</span><span class="sxs-lookup"><span data-stu-id="a58f8-104">Element</span></span>|<span data-ttu-id="a58f8-105">설명</span><span class="sxs-lookup"><span data-stu-id="a58f8-105">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a58f8-106">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="a58f8-106">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="a58f8-107">애플리케이션에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f8-107">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="a58f8-108">런타임 버전 1.1로 빌드된 응용 프로그램은 **\<supportedRuntime>** 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f8-108">Applications built with runtime version 1.1 should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="a58f8-109">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="a58f8-109">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="a58f8-110">응용 프로그램이 지원하는 공용 언어 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f8-110">Specifies which versions of the common language runtime the application supports.</span></span>|  
|[<span data-ttu-id="a58f8-111">\<startup></span><span class="sxs-lookup"><span data-stu-id="a58f8-111">\<startup></span></span>](startup-element.md)|<span data-ttu-id="a58f8-112">**\<requiredRuntime>** 및 **\<supportedRuntime>** 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a58f8-112">Contains the **\<requiredRuntime>** and **\<supportedRuntime>** elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a58f8-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="a58f8-113">See also</span></span>

- [<span data-ttu-id="a58f8-114">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a58f8-114">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a58f8-115">방법: .NET Framework 4 이상 버전을 지원하도록 앱 구성</span><span class="sxs-lookup"><span data-stu-id="a58f8-115">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
