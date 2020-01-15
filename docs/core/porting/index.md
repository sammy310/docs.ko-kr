---
title: .NET Framework에서 .NET Core로 이식
description: 이식 프로세스를 이해하고 .NET Framework 프로젝트를 .NET Core로 이식할 때 유용한 도구에 관해 알아보세요.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: e483bb6e48dad6c3bf71bfa81e704a137fc02094
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937329"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a><span data-ttu-id="1acf4-103">.NET Framework에서 .NET Core로의 이식 개요</span><span class="sxs-lookup"><span data-stu-id="1acf4-103">Overview of porting from .NET Framework to .NET Core</span></span>

<span data-ttu-id="1acf4-104">현재 .NET Framework에서 실행되는 코드를 .NET Core로 이식해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-104">You might have code that currently runs on the .NET Framework that you're interested in porting to .NET Core.</span></span> <span data-ttu-id="1acf4-105">이 문서에서는 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-105">This article provides:</span></span>

* <span data-ttu-id="1acf4-106">이식 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="1acf4-106">An overview of the porting process.</span></span>
* <span data-ttu-id="1acf4-107">코드를 .NET Core로 이식할 때 유용하게 사용할 수 있는 도구 목록</span><span class="sxs-lookup"><span data-stu-id="1acf4-107">A list of tools that you may find helpful when you're porting your code to .NET Core.</span></span>

## <a name="overview-of-the-porting-process"></a><span data-ttu-id="1acf4-108">포팅 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="1acf4-108">Overview of the porting process</span></span>

<span data-ttu-id="1acf4-109">다음은 프로젝트를 .NET Core로 이식할 때 사용 권장되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-109">We recommend you use the following process when porting your project to .NET Core:</span></span>

1. <span data-ttu-id="1acf4-110">이식하려는 모든 프로젝트의 대상을 .NET Framework 4.7.2 이상으로 다시 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-110">Retarget all projects you wish to port to target .NET Framework 4.7.2 or higher.</span></span>

   <span data-ttu-id="1acf4-111">이 단계에서는 .NET Core에서 특정 API를 지원하지 않는 경우 .NET Framework 특정 대상에 대한 API 대안을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-111">This step ensures that you can use API alternatives for .NET Framework-specific targets when .NET Core doesn't support a particular API.</span></span>

2. <span data-ttu-id="1acf4-112">[.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)로 어셈블리를 분석하여 .NET Core로 이식 가능한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-112">Use the [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) to analyze your assemblies and see if they're portable to .NET Core.</span></span>

   <span data-ttu-id="1acf4-113">API 이식성 분석기 도구는 컴파일된 어셈블리를 분석하여 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-113">The API Portability Analyzer tool analyzes your compiled assemblies and generates a report.</span></span> <span data-ttu-id="1acf4-114">이 보고서에서는 개괄적인 이식성 요약과 현재 사용 중인 API 중에서 .NET Core에서 사용할 수 없는 API 각각의 내역을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-114">This report shows a high-level portability summary and a breakdown of each API you're using that isn't available on NET Core.</span></span>

3. <span data-ttu-id="1acf4-115">[.NET API 분석기](../../standard/analyzers/api-analyzer.md)를 프로젝트에 설치하여 일부 플랫폼에서 <xref:System.PlatformNotSupportedException>을 throw하는 API와 그 밖의 잠재적인 호환성 문제를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-115">Install the [.NET API analyzer](../../standard/analyzers/api-analyzer.md) into your projects to identify APIs that throw <xref:System.PlatformNotSupportedException> on some platforms and some other potential compatibility issues.</span></span>

   <span data-ttu-id="1acf4-116">이 도구는 이식성 분석기와 비슷하나, .NET Core에서 빌드가 가능한지를 분석하는 대신 런타임에 <xref:System.PlatformNotSupportedException>을 throw하는 방식으로 API를 사용하고 있는지 여부를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-116">This tool is similar to the portability analyzer, but instead of analyzing if code can build on .NET Core, it analyzes whether you're using an API in a way that will throw a <xref:System.PlatformNotSupportedException> at run time.</span></span> <span data-ttu-id="1acf4-117">.NET Framework 4.7.2 이상에서 이식할 때 이 예외가 throw되는 경우는 드물긴 하지만 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-117">Although this isn't common if you're moving from .NET Framework 4.7.2 or higher, it's good to check.</span></span> <span data-ttu-id="1acf4-118">.NET Core에서 예외를 throw하는 API에 대한 자세한 내용은 [.NET Core에서 항상 예외를 throw하는 API](../compatibility/unsupported-apis.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1acf4-118">For more information about APIs that throw exceptions on .NET Core, see [APIs that always throw exceptions on .NET Core](../compatibility/unsupported-apis.md).</span></span>

4. <span data-ttu-id="1acf4-119">[Visual Studio의 변환 도구](/nuget/consume-packages/migrate-packages-config-to-package-reference)를 사용하여 `packages.config` 종속성을 모두 [PackageReference](/nuget/consume-packages/package-references-in-project-files) 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-119">Convert all of your `packages.config` dependencies to the [PackageReference](/nuget/consume-packages/package-references-in-project-files) format with the [conversion tool in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span></span>

   <span data-ttu-id="1acf4-120">이 단계에서는 종속성을 레거시 `packages.config` 형식에서 변환하는 작업이 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-120">This step involves converting your dependencies from the legacy `packages.config` format.</span></span> <span data-ttu-id="1acf4-121">`packages.config`는 .NET Core에서 작동하지 않으므로 패키지 종속성이 있는 경우 이 변환이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-121">`packages.config` doesn't work on .NET Core, so this conversion is required if you have package dependencies.</span></span>

5. <span data-ttu-id="1acf4-122">.NET Core를 위한 새 프로젝트를 만들고 소스 파일을 복사하거나 도구를 사용하여 기존 프로젝트의 변환을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-122">Create new projects for .NET Core and copy over source files, or attempt to convert your existing project file with a tool.</span></span>

   <span data-ttu-id="1acf4-123">.NET Core는 .NET Framework와 다른 단순화된 [프로젝트 파일 형식](../tools/csproj.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-123">.NET Core uses a simplified (and different) [project file format](../tools/csproj.md) than .NET Framework.</span></span> <span data-ttu-id="1acf4-124">계속하려면 프로젝트 파일을 이 형식으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-124">You'll need to convert your project files into this format to continue.</span></span>

6. <span data-ttu-id="1acf4-125">테스트 코드를 이식합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-125">Port your test code.</span></span>

   <span data-ttu-id="1acf4-126">.NET Core로 이식하면 코드베이스가 많이 변경되기 때문에 코드를 이식할 때 테스트를 실행할 수 있도록 테스트를 이식하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-126">Because porting to .NET Core is such a significant change to your codebase, it's highly recommended to port your test projects so that you can run tests as you port your code over.</span></span> <span data-ttu-id="1acf4-127">MSTest, xUnit 및 NUnit은 모두 .NET Core에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-127">MSTest, xUnit, and NUnit all work on .NET Core.</span></span>

<span data-ttu-id="1acf4-128">이에 더해, [dotnet try-convert](https://github.com/dotnet/try-convert) 도구를 사용하여 한 번에 보다 작은 솔루션 또는 개별 프로젝트를 .NET Core 프로젝트 파일 형식으로 이식해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-128">Additionally, you can attempt to port smaller solutions or individual projects in one operation to the .NET Core project file format with the [dotnet try-convert](https://github.com/dotnet/try-convert) tool.</span></span> <span data-ttu-id="1acf4-129">`dotnet try-convert`가 모든 프로젝트에서 작동한다는 보장은 없으며, 종속성의 대상이 되는 동작이 미묘하게 변경될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-129">`dotnet try-convert` is not guaranteed to work for all your projects, and it may cause subtle changes in behavior that you depended on.</span></span> <span data-ttu-id="1acf4-130">이 도구는 자동화가 가능한 기본 항목들을 자동화하기 위한 _‘시작점’_ 으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-130">Use it as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="1acf4-131">프로젝트를 마이그레이션하기 위한 보장되는 솔루션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1acf4-131">It isn't a guaranteed solution to migrating a project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1acf4-132">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1acf4-132">Next steps</span></span>

>[!div class="nextstepaction"]
>[<span data-ttu-id="1acf4-133">종속성 분석</span><span class="sxs-lookup"><span data-stu-id="1acf4-133">Analyze dependencies</span></span>](third-party-deps.md)
