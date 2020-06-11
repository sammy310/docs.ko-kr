---
title: 종속성 로딩 - .NET Core
description: .NET Core에서 관리 및 관리되지 않는 종속성 로드 개요
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.topic: overview
ms.openlocfilehash: 34deb802183f20cc92449c21eb7e149cc002850f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284224"
---
# <a name="dependency-loading-in-net-core"></a><span data-ttu-id="4617a-103">.NET Core에서 종속성 로딩</span><span class="sxs-lookup"><span data-stu-id="4617a-103">Dependency loading in .NET Core</span></span>

<span data-ttu-id="4617a-104">모든 .NET Core 애플리케이션에는 종속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-104">Every .NET Core application has dependencies.</span></span> <span data-ttu-id="4617a-105">간단한 `hello world` 앱에도 .NET Core 클래스 라이브러리의 일부에 대한 종속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-105">Even the simple `hello world` app has dependencies on portions of the .NET Core class libraries.</span></span>

<span data-ttu-id="4617a-106">.NET Core 기본 어셈블리 로드 논리를 이해하면 일반적인 배포 문제를 이해하고 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-106">Understanding .NET Core default assembly loading logic can help understanding and debugging typical deployment issues.</span></span>

<span data-ttu-id="4617a-107">일부 애플리케이션에서 종속성은 런타임에 동적으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-107">In some applications, dependencies are dynamically determined at run time.</span></span> <span data-ttu-id="4617a-108">이러한 경우 관리 어셈블리 및 관리되지 않는 종속성이 로드되는 방식을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-108">In these situations, it's critical to understand how managed assemblies and unmanaged dependencies are loaded.</span></span>

## <a name="understanding-assemblyloadcontext"></a><span data-ttu-id="4617a-109">AssemblyLoadContext 이해</span><span class="sxs-lookup"><span data-stu-id="4617a-109">Understanding AssemblyLoadContext</span></span>

<span data-ttu-id="4617a-110"><xref:System.Runtime.Loader.AssemblyLoadContext> API는 .NET Core 로딩 디자인의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-110">The <xref:System.Runtime.Loader.AssemblyLoadContext> API is central to the .NET Core loading design.</span></span> <span data-ttu-id="4617a-111">[AssemblyLoadContext 이해](understanding-assemblyloadcontext.md) 문서는 디자인에 대한 개념적 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-111">The [Understanding AssemblyLoadContext](understanding-assemblyloadcontext.md) article provides a conceptual overview to the design.</span></span>

## <a name="loading-details"></a><span data-ttu-id="4617a-112">세부 정보를 로드하는 중</span><span class="sxs-lookup"><span data-stu-id="4617a-112">Loading details</span></span>

<span data-ttu-id="4617a-113">로드 알고리즘 세부 정보는 다음과 같은 여러 문서에서 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-113">The loading algorithm details are covered briefly in several articles:</span></span>

- [<span data-ttu-id="4617a-114">관리 어셈블리 로드 알고리즘</span><span class="sxs-lookup"><span data-stu-id="4617a-114">Managed assembly loading algorithm</span></span>](loading-managed.md)
- [<span data-ttu-id="4617a-115">위성 어셈블리 로드 알고리즘</span><span class="sxs-lookup"><span data-stu-id="4617a-115">Satellite assembly loading algorithm</span></span>](loading-resources.md)
- [<span data-ttu-id="4617a-116">관리되지 않는(네이티브) 라이브러리 로드 알고리즘</span><span class="sxs-lookup"><span data-stu-id="4617a-116">Unmanaged (native) library loading algorithm</span></span>](loading-unmanaged.md)
- [<span data-ttu-id="4617a-117">기본 검색</span><span class="sxs-lookup"><span data-stu-id="4617a-117">Default probing</span></span>](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="4617a-118">플러그 인을 사용하여 .NET Core 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="4617a-118">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="4617a-119">자습서 [플러그 인을 사용하여 .NET Core 애플리케이션 만들기](../tutorials/creating-app-with-plugin-support.md)에서는 사용자 지정 AssemblyLoadContext를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-119">The tutorial [Create a .NET Core application with plugins](../tutorials/creating-app-with-plugin-support.md) describes how to create a custom AssemblyLoadContext.</span></span> <span data-ttu-id="4617a-120"><xref:System.Runtime.Loader.AssemblyDependencyResolver>를 사용하여 플러그 인의 종속성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-120">It uses an <xref:System.Runtime.Loader.AssemblyDependencyResolver> to resolve the dependencies of the plugin.</span></span> <span data-ttu-id="4617a-121">이 자습서에서는 플러그 인의 종속성을 호스팅 애플리케이션에서 올바르게 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-121">The tutorial correctly isolates the plugin's dependencies from the hosting application.</span></span>

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="4617a-122">.NET Core에서 어셈블리 언로드 기능을 사용하고 디버그하는 방법</span><span class="sxs-lookup"><span data-stu-id="4617a-122">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="4617a-123">[.NET Core에서 어셈블리 언로드 기능을 사용하고 디버그하는 방법](../../standard/assembly/unloadability.md) 문서는 단계별 자습서입니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-123">The [How to use and debug assembly unloadability in .NET Core](../../standard/assembly/unloadability.md) article is a step-by-step tutorial.</span></span> <span data-ttu-id="4617a-124">.NET Core 애플리케이션을 로드하고 실행한 다음, 언로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-124">It shows how to load a .NET Core application, execute, and then unload it.</span></span> <span data-ttu-id="4617a-125">이 문서는 디버깅 팁도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4617a-125">The article also provides debugging tips.</span></span>
