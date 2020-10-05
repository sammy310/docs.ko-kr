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
# <a name="tools-to-help-with-porting-to-net-core"></a>.NET Core로 이식하는 작업에 도움이 되는 도구

이 문서에 나와 있는 도구가 이식할 때 유용할 수 있습니다.

- [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md) - .NET Framework와 .NET Core 간에 코드를 얼마나 이식 가능한지에 대한 보고서를 생성할 수 있는 도구 체인입니다.
  - [명령줄 도구](https://github.com/Microsoft/dotnet-apiport/releases)
  - [Visual Studio 확장](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [플랫폼 호환성 분석기](../../standard/analyzers/platform-compat-analyzer.md) - API를 사용하지 못할 수 있는 호출 사이트에서 플랫폼별 API를 사용할 경우 개발자에게 알리는 Roslyn 분석기입니다.
- [.NET API 분석기](../../standard/analyzers/api-analyzer.md) - 플랫폼 간 앱 및 라이브러리에서 플랫폼 호환성 문제를 감지하는 데 도움이 되는 Roslyn 분석기입니다.
- [try-convert](https://www.nuget.org/packages/try-convert/) - 데스크톱 앱을 .NET Core로 이동하는 것을 포함하여 프로젝트나 전체 솔루션을 .NET SDK로 변환할 수 있는 .NET Core 전역 도구입니다. 더 복잡한 빌드(예: 사용자 지정 작업, 대상 또는 가져오기)를 설정하고 .NET Core와 호환되지 않는 많은 프로젝트 형식을 거부하는 경우에는 권장되지 않습니다.
