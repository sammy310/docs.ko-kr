---
title: .NET Core로 이식하는 작업을 위한 도구
description: .NET Core로 이식하는 데 사용할 수 있는 도구 중 일부에 대해 알아보기
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: b8678ec72fe5d910d5f8cff4768106e7496f9276
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406130"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="4dae7-103">.NET Core로 이식하는 작업에 도움이 되는 도구</span><span class="sxs-lookup"><span data-stu-id="4dae7-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="4dae7-104">이 문서에 나와 있는 도구가 이식할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dae7-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="4dae7-105">[.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md) - .NET Framework와 .NET Core 간에 코드를 얼마나 이식 가능한지에 대한 보고서를 생성할 수 있는 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="4dae7-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="4dae7-106">[명령줄 도구](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="4dae7-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="4dae7-107">[Visual Studio 확장](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span><span class="sxs-lookup"><span data-stu-id="4dae7-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="4dae7-108">[플랫폼 호환성 분석기](../../standard/analyzers/platform-compat-analyzer.md) - API를 사용하지 못할 수 있는 호출 사이트에서 플랫폼별 API를 사용할 경우 개발자에게 알리는 Roslyn 분석기입니다.</span><span class="sxs-lookup"><span data-stu-id="4dae7-108">[Platform compatibility analyzer](../../standard/analyzers/platform-compat-analyzer.md) - A Roslyn analyzer that informs developers when they use platform-specific APIs from call sites where the API might not be available.</span></span>
- <span data-ttu-id="4dae7-109">[.NET API 분석기](../../standard/analyzers/api-analyzer.md) - 플랫폼 간 앱 및 라이브러리에서 플랫폼 호환성 문제를 감지하는 데 도움이 되는 Roslyn 분석기입니다.</span><span class="sxs-lookup"><span data-stu-id="4dae7-109">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that can help detect platform compatibility issues in cross-platform apps and libraries.</span></span>
- <span data-ttu-id="4dae7-110">[try-convert](https://www.nuget.org/packages/try-convert/) - 데스크톱 앱을 .NET Core로 이동하는 것을 포함하여 프로젝트나 전체 솔루션을 .NET SDK로 변환할 수 있는 .NET Core 전역 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="4dae7-110">[try-convert](https://www.nuget.org/packages/try-convert/) - A .NET Core global tool that can convert a project or entire solution to the .NET SDK, including moving desktop apps to .NET Core.</span></span> <span data-ttu-id="4dae7-111">더 복잡한 빌드(예: 사용자 지정 작업, 대상 또는 가져오기)를 설정하고 .NET Core와 호환되지 않는 많은 프로젝트 형식을 거부하는 경우에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4dae7-111">It is not recommended if you have a more complicated build established (such as custom tasks, targets, or imports), and it rejects many project types that are incompatible with .NET Core.</span></span>
