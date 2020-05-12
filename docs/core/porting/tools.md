---
title: .NET Core로 이식하는 작업을 위한 도구
description: .NET Core로 이식하는 데 사용할 수 있는 도구 중 일부에 대해 알아보기
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: d0cf0abf206950beb34556ca3ba7243d8cad241e
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795588"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="98b76-103">.NET Core로 이식하는 작업에 도움이 되는 도구</span><span class="sxs-lookup"><span data-stu-id="98b76-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="98b76-104">이 문서에 나와 있는 도구가 이식할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b76-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="98b76-105">[.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md) - .NET Framework와 .NET Core 간에 코드를 얼마나 이식 가능한지에 대한 보고서를 생성할 수 있는 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="98b76-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="98b76-106">[명령줄 도구](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="98b76-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="98b76-107">[Visual Studio 확장](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span><span class="sxs-lookup"><span data-stu-id="98b76-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="98b76-108">[.NET API 분석기](../../standard/analyzers/api-analyzer.md) - 여러 플랫폼에서 C# API에 대한 잠재적 호환성 위험을 검색하고 사용되지 않는 API 호출을 탐지하는 Roslyn 분석기입니다.</span><span class="sxs-lookup"><span data-stu-id="98b76-108">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>
- <span data-ttu-id="98b76-109">[try-convert](https://www.nuget.org/packages/try-convert/) - 데스크톱 앱을 .NET Core로 이동하는 것을 포함하여 프로젝트나 전체 솔루션을 .NET SDK로 변환할 수 있는 .NET Core 전역 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="98b76-109">[try-convert](https://www.nuget.org/packages/try-convert/) - A .NET Core global tool that can convert a project or entire solution to the .NET SDK, including moving desktop apps to .NET Core.</span></span> <span data-ttu-id="98b76-110">더 복잡한 빌드(예: 사용자 지정 작업, 대상 또는 가져오기)를 설정하고 .NET Core와 호환되지 않는 많은 프로젝트 형식을 거부하는 경우에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98b76-110">It is not recommended if you have a more complicated build established (such as custom tasks, targets, or imports), and it rejects many project types that are incompatible with .NET Core.</span></span>
