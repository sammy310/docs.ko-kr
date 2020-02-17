---
title: .NET Core로 이식하는 작업을 위한 도구
description: .NET Core로 이식하는 데 사용할 수 있는 도구 중 일부에 대해 알아보기
author: cartermp
ms.date: 12/07/2018
ms.openlocfilehash: 3b71c31b4f26b278b2bd1088adc8e9f64d28ab7b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215189"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="3ec39-103">.NET Core로 이식하는 작업에 도움이 되는 도구</span><span class="sxs-lookup"><span data-stu-id="3ec39-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="3ec39-104">이 문서에 나와 있는 도구가 이식할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec39-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="3ec39-105">[.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md) - .NET Framework와 .NET Core 간에 코드를 얼마나 이식 가능한지에 대한 보고서를 생성할 수 있는 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="3ec39-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="3ec39-106">[명령줄 도구](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="3ec39-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="3ec39-107">[Visual Studio 확장](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)</span><span class="sxs-lookup"><span data-stu-id="3ec39-107">As a [Visual Studio extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)</span></span>
- <span data-ttu-id="3ec39-108">[.NET API 분석기](../../standard/analyzers/api-analyzer.md) - 여러 플랫폼에서 C# API에 대한 잠재적 호환성 위험을 검색하고 사용되지 않는 API 호출을 탐지하는 Roslyn 분석기입니다.</span><span class="sxs-lookup"><span data-stu-id="3ec39-108">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>

<span data-ttu-id="3ec39-109">또한 [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) 도구를 사용하여 작은 솔루션 또는 개별 프로젝트를 .NET Core 프로젝트 파일 형식으로 포팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec39-109">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) tool.</span></span>

> [!WARNING] 
> <span data-ttu-id="3ec39-110">CsprojToVs2017은 타사 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="3ec39-110">CsprojToVs2017 is a third-party tool.</span></span> <span data-ttu-id="3ec39-111">모든 프로젝트에서 작동한다는 보장은 없으며, 사용하는 동작이 미묘하게 변경될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ec39-111">There is no guarantee that it will work for all of your projects, and it may cause subtle changes in behavior that you depend on.</span></span> <span data-ttu-id="3ec39-112">CsprojToVs2017은 자동화할 수 있는 기본 사항을 자동화하는 _시작점_으로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ec39-112">CsprojToVs2017 should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="3ec39-113">프로젝트 파일 형식을 마이그레이션하는 보장된 솔루션은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3ec39-113">It is not a guaranteed solution to migrating project file formats.</span></span>
