---
title: 애플리케이션 도메인 사용
ms.date: 03/30/2017
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
ms.openlocfilehash: d6bbc2648608e9542158e0f281984174447633a4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119731"
---
# <a name="using-application-domains"></a><span data-ttu-id="28d1a-102">애플리케이션 도메인 사용</span><span class="sxs-lookup"><span data-stu-id="28d1a-102">Using Application Domains</span></span>

<span data-ttu-id="28d1a-103">애플리케이션 도메인은 공용 언어 런타임에 대한 격리 단위를 제공하고</span><span class="sxs-lookup"><span data-stu-id="28d1a-103">Application domains provide a unit of isolation for the common language runtime.</span></span> <span data-ttu-id="28d1a-104">프로세스 내에서 생성되고 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-104">They are created and run inside a process.</span></span> <span data-ttu-id="28d1a-105">애플리케이션 도메인은 대개 런타임을 프로세스로 로드하고 애플리케이션 도메인 내에서 사용자 코드를 실행하는 애플리케이션인 런타임 호스트에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-105">Application domains are usually created by a runtime host, which is an application responsible for loading the runtime into a process and executing user code within an application domain.</span></span> <span data-ttu-id="28d1a-106">런타임 호스트는 프로세스와 기본 애플리케이션 도메인을 만들고 그 내부에서 관리 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-106">The runtime host creates a process and a default application domain, and runs managed code inside it.</span></span> <span data-ttu-id="28d1a-107">런타임 호스트에는 ASP.NET, Microsoft Internet Explorer 및 Windows 셸이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-107">Runtime hosts include ASP.NET, Microsoft Internet Explorer, and the Windows shell.</span></span>  
  
<span data-ttu-id="28d1a-108">대부분 애플리케이션의 경우 자체적인 애플리케이션 도메인을 만들 필요가 없습니다. 런타임 호스트에서 필요한 애플리케이션 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-108">For most applications, you do not need to create your own application domain; the runtime host creates any necessary application domains for you.</span></span> <span data-ttu-id="28d1a-109">그러나 애플리케이션이 코드를 분리하거나 DLL을 사용하고 언로드해야 할 경우 직접 추가적인 애플리케이션 도메인을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-109">However, you can create and configure additional application domains if your application needs to isolate code or to use and unload DLLs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="28d1a-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="28d1a-110">In This Section</span></span>  

[<span data-ttu-id="28d1a-111">방법: 애플리케이션 도메인 만들기</span><span class="sxs-lookup"><span data-stu-id="28d1a-111">How to: Create an Application Domain</span></span>](how-to-create-an-application-domain.md)  
<span data-ttu-id="28d1a-112">애플리케이션 도메인을 프로그래밍 방식으로 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-112">Describes how to programmatically create an application domain.</span></span>  
  
[<span data-ttu-id="28d1a-113">방법: 애플리케이션 도메인 언로드</span><span class="sxs-lookup"><span data-stu-id="28d1a-113">How to: Unload an Application Domain</span></span>](how-to-unload-an-application-domain.md)  
<span data-ttu-id="28d1a-114">애플리케이션 도메인을 프로그래밍 방식으로 언로드하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-114">Describes how to programmatically unload an application domain.</span></span>  
  
[<span data-ttu-id="28d1a-115">방법: 애플리케이션 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="28d1a-115">How to: Configure an Application Domain</span></span>](how-to-configure-an-application-domain.md)  
<span data-ttu-id="28d1a-116">애플리케이션 도메인을 구성하는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-116">Provides an introduction to configuring an application domain.</span></span>  
  
[<span data-ttu-id="28d1a-117">애플리케이션 도메인에서 설치 정보 검색</span><span class="sxs-lookup"><span data-stu-id="28d1a-117">Retrieving Setup Information from an Application Domain</span></span>](retrieve-setup-information.md)  
<span data-ttu-id="28d1a-118">애플리케이션 도메인에서 설정 정보를 검색하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-118">Describes how to retrieve setup information from an application domain.</span></span>  
  
[<span data-ttu-id="28d1a-119">방법: 애플리케이션 도메인에 어셈블리 로드</span><span class="sxs-lookup"><span data-stu-id="28d1a-119">How to: Load Assemblies into an Application Domain</span></span>](how-to-load-assemblies-into-an-application-domain.md)  
<span data-ttu-id="28d1a-120">어셈블리를 애플리케이션 도메인으로 로드하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-120">Describes how to load an assembly into an application domain.</span></span>  
  
[<span data-ttu-id="28d1a-121">방법: 어셈블리에서 형식 및 멤버 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="28d1a-121">How to: Obtain Type and Member Information from an Assembly</span></span>](../reflection-and-codedom/get-type-member-information.md)  
<span data-ttu-id="28d1a-122">어셈블리에 대한 정보를 검색하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-122">Describes how to retrieve information about an assembly.</span></span>  
  
[<span data-ttu-id="28d1a-123">어셈블리 섀도 복사</span><span class="sxs-lookup"><span data-stu-id="28d1a-123">Shadow Copying Assemblies</span></span>](shadow-copy-assemblies.md)  
<span data-ttu-id="28d1a-124">어셈블리가 사용되는 동안 섀도 복사를 통해 어셈블리 업데이트를 허용하는 방법과 섀도 복사를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-124">Describes how shadow copying allows updates to assemblies while they are in use, and how to configure shadow copying.</span></span>  
  
[<span data-ttu-id="28d1a-125">방법: 첫째 예외 알림 받기</span><span class="sxs-lookup"><span data-stu-id="28d1a-125">How to: Receive First-Chance Exception Notifications</span></span>](how-to-receive-first-chance-exception-notifications.md)  
<span data-ttu-id="28d1a-126">공용 언어 런타임이 예외 처리기 검색을 시작하기 전에 예외가 throw되었다는 알림을 받을 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-126">Explains how you can receive a notification that an exception has been thrown, before the common language runtime has begun searching for exception handlers.</span></span>  
  
[<span data-ttu-id="28d1a-127">어셈블리 로드 해결</span><span class="sxs-lookup"><span data-stu-id="28d1a-127">Resolving Assembly Loads</span></span>](../../standard/assembly/resolve-loads.md)  
<span data-ttu-id="28d1a-128"><xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트를 사용하여 어셈블리 로드 실패를 해결하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-128">Provides guidance on using the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event to resolve assembly load failures.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="28d1a-129">참조</span><span class="sxs-lookup"><span data-stu-id="28d1a-129">Reference</span></span>  

<xref:System.AppDomain>  
<span data-ttu-id="28d1a-130">애플리케이션 도메인을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-130">Represents an application domain.</span></span> <span data-ttu-id="28d1a-131">애플리케이션 도메인을 만들고 제어하기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-131">Provides methods for creating and controlling application domains.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="28d1a-132">관련 단원</span><span class="sxs-lookup"><span data-stu-id="28d1a-132">Related Sections</span></span>  
[<span data-ttu-id="28d1a-133">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="28d1a-133">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="28d1a-134">어셈블리가 실행하는 함수의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-134">Provides an overview of the functions performed by assemblies.</span></span>  
  
[<span data-ttu-id="28d1a-135">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="28d1a-135">Programming with Assemblies</span></span>](../../standard/assembly/program.md)  
<span data-ttu-id="28d1a-136">어셈블리를 만들고, 서명하고, 특성을 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-136">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
[<span data-ttu-id="28d1a-137">동적 메서드 및 어셈블리 내보내기</span><span class="sxs-lookup"><span data-stu-id="28d1a-137">Emitting Dynamic Methods and Assemblies</span></span>](../reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
<span data-ttu-id="28d1a-138">동적 어셈블리를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-138">Describes how to create dynamic assemblies.</span></span>  
  
[<span data-ttu-id="28d1a-139">애플리케이션 도메인</span><span class="sxs-lookup"><span data-stu-id="28d1a-139">Application Domains</span></span>](application-domains.md)  
<span data-ttu-id="28d1a-140">애플리케이션 도메인에 대해 개념적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-140">Provides a conceptual overview of application domains.</span></span>  
  
[<span data-ttu-id="28d1a-141">리플렉션 개요</span><span class="sxs-lookup"><span data-stu-id="28d1a-141">Reflection Overview</span></span>](../reflection-and-codedom/reflection.md)  
<span data-ttu-id="28d1a-142">**Reflection** 클래스를 사용하여 어셈블리에 대한 정보를 얻는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28d1a-142">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
