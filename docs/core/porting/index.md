---
title: .NET Framework에서 .NET Core로 코드 포팅
description: 이식 프로세스를 이해하고 .NET Framework 프로젝트를 .NET Core로 이식할 때 유용한 도구에 관해 알아보세요.
author: cartermp
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 870320c8467237e87a2675ec5cfb57647026d8ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663234"
---
# <a name="port-your-code-from-net-framework-to-net-core"></a>.NET Framework에서 .NET Core로 코드 포팅

.NET Framework에서 실행되는 코드를 사용한 적이 있다면 .NET Core에서 코드를 실행하는 것에도 관심이 있을 수 있습니다. 여기서는 포팅 프로세스 및 코드를 .NET Core로 포팅할 때 유용할 수 있는 도구 목록을 간략하게 설명합니다.

## <a name="overview-of-the-porting-process"></a>포팅 프로세스 개요

프로젝트를 .NET Core로 포팅할 때 권장되는 프로세스입니다. 프로세스의 각 단계는 향후 문서에서 자세히 설명합니다.

1. 타사 종속성을 식별하고 확인합니다.

   이 단계에서는 타사 종속성의 개념, 사용 방법, .NET Core에서도 실행되는지 확인하는 방법 및 실행되지 않을 경우 수행할 수 있는 단계를 파악해야 합니다. .NET Core에 사용되는 [PackageReference](/nuget/consume-packages/package-references-in-project-files) 형식으로 종속성을 마이그레이션하는 방법에 대해서도 설명합니다.

2. 포팅하려는 모든 프로젝트의 대상을 .NET Framework 4.7.2 이상으로 다시 지정합니다.

   이 단계에서는 .NET Core에서 특정 API를 지원하지 않는 경우 .NET Framework 특정 대상에 대한 API 대안을 사용할 수 있도록 합니다.

3. [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md)를 사용하여 어셈블리를 분석하고 결과에 따라 이식 계획을 수립합니다.

   API 이식성 분석기 도구는 컴파일된 어셈블리를 분석하고 개괄적인 이식성 요약 및 .NET Core에서 사용할 수 없는 사용 중인 각 API에 대한 분석 결과를 보여 주는 보고서를 생성합니다. 코드베이스에 대한 분석과 함께 이 보고서를 사용하여 코드를 이식할 방법에 대한 계획을 개발할 수 있습니다.

4. 테스트 코드를 이식합니다.

   .NET Core로 포팅하면 코드베이스가 많이 변경되기 때문에 코드를 포팅할 때 테스트를 실행할 수 있도록 테스트를 포팅하는 것이 좋습니다. MSTest, xUnit 및 NUnit는 모두 .NET Core를 지원합니다.

5. 이식에 대한 계획을 실행합니다.

다음 목록은 포팅 프로세스 중에 사용하면 도움이 되는 도구를 보여 줍니다.

* .NET 이식성 분석기 - [명령줄 도구](https://github.com/Microsoft/dotnet-apiport/releases) 또는 [Visual Studio 확장](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)으로, 문제에 대한 어셈블리 단위 분석 결과를 사용하여 .NET Framework와 .NET Core 간에 코드를 포팅할 수 있는 정도에 대한 보고서를 생성할 수 있는 도구 체인입니다. 자세한 내용은 [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)를 참조하세요.
* .NET API 분석기 - 여러 플랫폼에서 C# API에 대한 잠재적 호환성 위험을 검색하고 사용되지 않는 API 호출을 탐지하는 Roslyn 분석기입니다. 자세한 내용은 [.NET API 분석기](../../standard/analyzers/api-analyzer.md)를 참조하세요.
* 역방향 패키지 검색 - 형식을 검색하고 해당 형식을 포함하는 패키지를 찾을 수 있는 [유용한 웹 서비스](https://packagesearch.azurewebsites.net)입니다.

또한 [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) 도구를 사용하여 작은 솔루션 또는 개별 프로젝트를 .NET Core 프로젝트 파일 형식으로 포팅할 수 있습니다.

> [!WARNING] 
> CsprojToVs2017은 타사 도구입니다. 모든 프로젝트에서 작동한다는 보장은 없으며, 사용하는 동작이 미묘하게 변경될 수도 있습니다. CsprojToVs2017은 자동화할 수 있는 기본 사항을 자동화하는 _시작점_으로 사용해야 합니다. 프로젝트 파일 형식을 마이그레이션하는 보장된 솔루션은 아닙니다.

>[!div class="step-by-step"]
>[다음](net-framework-tech-unavailable.md)
