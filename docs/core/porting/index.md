---
title: .NET Framework에서 .NET Core로 이식
description: 이식 프로세스를 이해하고 .NET Framework 프로젝트를 .NET Core로 이식할 때 유용한 도구에 관해 알아보세요.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: e483bb6e48dad6c3bf71bfa81e704a137fc02094
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "75937329"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a>.NET Framework에서 .NET Core로의 이식 개요

현재 .NET Framework에서 실행되는 코드를 .NET Core로 이식해야 하는 경우가 있습니다. 이 문서에서는 다음을 제공합니다.

* 이식 프로세스 개요
* 코드를 .NET Core로 이식할 때 유용하게 사용할 수 있는 도구 목록

## <a name="overview-of-the-porting-process"></a>포팅 프로세스 개요

다음은 프로젝트를 .NET Core로 이식할 때 사용 권장되는 프로세스입니다.

1. 이식하려는 모든 프로젝트의 대상을 .NET Framework 4.7.2 이상으로 다시 지정합니다.

   이 단계에서는 .NET Core에서 특정 API를 지원하지 않는 경우 .NET Framework 특정 대상에 대한 API 대안을 사용할 수 있도록 합니다.

2. [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)로 어셈블리를 분석하여 .NET Core로 이식 가능한지 확인합니다.

   API 이식성 분석기 도구는 컴파일된 어셈블리를 분석하여 보고서를 생성합니다. 이 보고서에서는 개괄적인 이식성 요약과 현재 사용 중인 API 중에서 .NET Core에서 사용할 수 없는 API 각각의 내역을 보여 줍니다.

3. [.NET API 분석기](../../standard/analyzers/api-analyzer.md)를 프로젝트에 설치하여 일부 플랫폼에서 <xref:System.PlatformNotSupportedException>을 throw하는 API와 그 밖의 잠재적인 호환성 문제를 식별합니다.

   이 도구는 이식성 분석기와 비슷하나, .NET Core에서 빌드가 가능한지를 분석하는 대신 런타임에 <xref:System.PlatformNotSupportedException>을 throw하는 방식으로 API를 사용하고 있는지 여부를 분석합니다. .NET Framework 4.7.2 이상에서 이식할 때 이 예외가 throw되는 경우는 드물긴 하지만 확인하는 것이 좋습니다. .NET Core에서 예외를 throw하는 API에 대한 자세한 내용은 [.NET Core에서 항상 예외를 throw하는 API](../compatibility/unsupported-apis.md)를 참조하세요.

4. `packages.config`Visual Studio의 변환 도구[를 사용하여 ](/nuget/consume-packages/package-references-in-project-files) 종속성을 모두 [PackageReference](/nuget/consume-packages/migrate-packages-config-to-package-reference) 형식으로 변환합니다.

   이 단계에서는 종속성을 레거시 `packages.config` 형식에서 변환하는 작업이 이루어집니다. `packages.config`는 .NET Core에서 작동하지 않으므로 패키지 종속성이 있는 경우 이 변환이 필요합니다.

5. .NET Core를 위한 새 프로젝트를 만들고 소스 파일을 복사하거나 도구를 사용하여 기존 프로젝트의 변환을 시도합니다.

   .NET Core는 .NET Framework와 다른 단순화된 [프로젝트 파일 형식](../tools/csproj.md)을 사용합니다. 계속하려면 프로젝트 파일을 이 형식으로 변환해야 합니다.

6. 테스트 코드를 이식합니다.

   .NET Core로 이식하면 코드베이스가 많이 변경되기 때문에 코드를 이식할 때 테스트를 실행할 수 있도록 테스트를 이식하는 것이 좋습니다. MSTest, xUnit 및 NUnit은 모두 .NET Core에서 작동합니다.

이에 더해, [dotnet try-convert](https://github.com/dotnet/try-convert) 도구를 사용하여 한 번에 보다 작은 솔루션 또는 개별 프로젝트를 .NET Core 프로젝트 파일 형식으로 이식해 볼 수 있습니다. `dotnet try-convert`가 모든 프로젝트에서 작동한다는 보장은 없으며, 종속성의 대상이 되는 동작이 미묘하게 변경될 수도 있습니다. 이 도구는 자동화가 가능한 기본 항목들을 자동화하기 위한 _‘시작점’_ 으로 사용됩니다. 프로젝트를 마이그레이션하기 위한 보장되는 솔루션이 아닙니다.

## <a name="next-steps"></a>다음 단계

>[!div class="nextstepaction"]
>[종속성 분석](third-party-deps.md)
