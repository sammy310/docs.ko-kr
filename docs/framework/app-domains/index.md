---
title: 애플리케이션 도메인 및 어셈블리를 사용한 프로그래밍
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
ms.openlocfilehash: 2c849d27c70971d17bf4359ee7ae1081ee976a5f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119813"
---
# <a name="programming-with-application-domains-and-assemblies"></a><span data-ttu-id="00eab-102">애플리케이션 도메인 및 어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="00eab-102">Programming with Application Domains and Assemblies</span></span>

<span data-ttu-id="00eab-103">Microsoft Internet Explorer, ASP.NET 및 Windows 셸과 같은 호스트는 프로세스에 공용 언어 런타임을 로드하고, 해당 프로세스에서 [애플리케이션 도메인](application-domains.md)을 만든 다음 .NET Framework 애플리케이션을 실행할 때 해당 애플리케이션 도메인에서 사용자 코드를 로드한 후 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="00eab-103">Hosts such as Microsoft Internet Explorer, ASP.NET, and the Windows shell load the common language runtime into a process, create an [application domain](application-domains.md) in that process, and then load and execute user code in that application domain when running a .NET Framework application.</span></span> <span data-ttu-id="00eab-104">대부분의 경우 런타임 호스트가 알아서 작업을 진행하므로 애플리케이션 도메인 만들기 및 어셈블리 로드에 대해 걱정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00eab-104">In most cases, you do not have to worry about creating application domains and loading assemblies into them because the runtime host performs those tasks.</span></span>  
  
<span data-ttu-id="00eab-105">그러나 공용 언어 런타임을 호스트하는 애플리케이션 만들거나, 프로그래밍 방식으로 언로드하려는 도구 또는 코드를 만들거나, 즉석에서 언로드 및 다시 로드할 수 있는 플러그형 구성 요소를 만드는 경우 자체 애플리케이션 도메인을 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00eab-105">However, if you are creating an application that will host the common language runtime, creating tools or code you want to unload programmatically, or creating pluggable components that can be unloaded and reloaded on the fly, you will be creating your own application domains.</span></span> <span data-ttu-id="00eab-106">런타임 호스트를 만들지 않더라도 이 섹션을 통해 애플리케이션 도메인으로 작업하는 방법 및 이러한 애플리케이션 도메인에 로드되는 어셈블리에 대한 중요한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00eab-106">Even if you are not creating a runtime host, this section provides important information on how to work with application domains and assemblies loaded in these application domains.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="00eab-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="00eab-107">In This Section</span></span>  

[<span data-ttu-id="00eab-108">애플리케이션 도메인 및 어셈블리 방법 항목</span><span class="sxs-lookup"><span data-stu-id="00eab-108">Application Domains and Assemblies How-to Topics</span></span>](application-domains-and-assemblies-how-to-topics.md)  
<span data-ttu-id="00eab-109">애플리케이션 도메인 및 어셈블리를 사용한 프로그래밍에 대한 개념 설명서에 나오는 모든 방법 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00eab-109">Provides links to all How-to topics found in the conceptual documentation for programming with application domains and assemblies.</span></span>  
  
[<span data-ttu-id="00eab-110">애플리케이션 도메인 사용</span><span class="sxs-lookup"><span data-stu-id="00eab-110">Using Application Domains</span></span>](use.md)  
<span data-ttu-id="00eab-111">애플리케이션 도메인 만들기, 구성 및 사용에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00eab-111">Provides examples of creating, configuring, and using application domains.</span></span>  
  
[<span data-ttu-id="00eab-112">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="00eab-112">Programming with Assemblies</span></span>](../../standard/assembly/program.md)  
<span data-ttu-id="00eab-113">어셈블리를 만들고, 서명하고, 특성을 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00eab-113">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="00eab-114">관련 단원</span><span class="sxs-lookup"><span data-stu-id="00eab-114">Related Sections</span></span>  

[<span data-ttu-id="00eab-115">동적 메서드 및 어셈블리 내보내기</span><span class="sxs-lookup"><span data-stu-id="00eab-115">Emitting Dynamic Methods and Assemblies</span></span>](../reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
<span data-ttu-id="00eab-116">동적 어셈블리를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00eab-116">Describes how to create dynamic assemblies.</span></span>  
  
[<span data-ttu-id="00eab-117">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="00eab-117">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="00eab-118">어셈블리에 대해 개념적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00eab-118">Provides a conceptual overview of assemblies.</span></span>  
  
[<span data-ttu-id="00eab-119">애플리케이션 도메인</span><span class="sxs-lookup"><span data-stu-id="00eab-119">Application Domains</span></span>](application-domains.md)  
<span data-ttu-id="00eab-120">애플리케이션 도메인에 대해 개념적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00eab-120">Provides a conceptual overview of application domains.</span></span>  
  
[<span data-ttu-id="00eab-121">리플렉션 개요</span><span class="sxs-lookup"><span data-stu-id="00eab-121">Reflection Overview</span></span>](../reflection-and-codedom/reflection.md)  
<span data-ttu-id="00eab-122">**Reflection** 클래스를 사용하여 어셈블리에 대한 정보를 얻는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00eab-122">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
