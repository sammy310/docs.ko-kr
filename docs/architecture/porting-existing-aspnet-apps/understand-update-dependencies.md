---
title: 종속성 이해 및 업데이트
description: .NET Framework 프로젝트를 .NET Core로 마이그레이션하려면 .NET Core를 사용 하도록 해당 종속성을 업데이트 해야 합니다. 이 섹션에서는 많은 앱에 대 한 마이그레이션을 계획 하는 데 사용할 수 있는 도구 및 접근 방식을 검사 합니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: afad77860099e4737b5270dc32fc20c2025e63dd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401687"
---
# <a name="understand-and-update-dependencies"></a>종속성 이해 및 업데이트

앱의 개별 프로젝트를 마이그레이션해야 하는 순서를 확인 한 후 다음 단계는 각 프로젝트의 종속성을 이해 하 고 필요한 경우 업데이트 하는 것입니다. 플랫폼 종속성의 경우에는 문제의 어셈블리에서 [.Net 이식성 분석기](../../standard/analyzers/portability-analyzer.md) 를 실행 한 다음 생성 된 자세한 결과를 확인 하는 것이 가장 좋은 방법입니다. 하나 이상의 대상 플랫폼 (예: .NET Core 3.1 또는 .NET Standard 2.0)을 지정 하도록 도구를 구성 합니다. 결과는 대상으로 지정 된 각 플랫폼에 대 한 세부 정보와 함께 제공 됩니다. 그림 3-4에서는 도구의 출력 예를 보여 줍니다.

![.NET 이식성 분석기 보고서 세부 정보](./media/Figure3-4.png)

**그림 3-4.** .NET 이식성 분석기 보고서 세부 정보입니다.

## <a name="update-class-library-dependencies"></a>클래스 라이브러리 종속성 업데이트

일반적으로 큰 앱에는 여러 프로젝트가 포함 되며, ASP.NET MVC 웹 프로젝트 이외의 대부분의 프로젝트는 클래스 라이브러리 일 수 있습니다. 클래스 라이브러리는 .NET 플랫폼 사이에서 특히 가장 어려운 (그리고 일반적으로 다시 만들어야 하는 ASP.NET 프로젝트)와 비교 하 여 가장 쉽게 이식할 수 있는 경향이 있습니다.

팀에서는 클래스 라이브러리를 .NET Core로 마이그레이션하기 위한 [변환 도구](https://github.com/dotnet/try-convert) 또는 [.net 업그레이드 도우미 도구](https://aka.ms/dotnet-upgrade-assistant) 를 고려할 수 있습니다. 이러한 도구는 .NET Framework 프로젝트 파일을 분석 하 고 .NET Core 프로젝트 파일 형식으로 마이그레이션하여 프로세스에서 안전 하 게 수행할 수 있도록 합니다. 도구에는 ASP.NET 프로젝트를 사용 하기 위한 몇 가지 수동 지원이 필요할 수 있지만 일반적으로 클래스 라이브러리를 마이그레이션하는 과정의 속도를 높일 수 있습니다.

변환 및 업그레이드 도우미 도구는 .NET Core 명령줄 도구로 배포 됩니다. .NET Framework 앱에서 작동 하도록 설계 되었으므로 Windows 에서만 실행 됩니다. 명령 프롬프트에서 다음 명령을 실행 하 여 try-convert를 설치할 수 있습니다.

```dotnetcli
dotnet tool install -g try-convert
```

도구를 성공적으로 설치 하면 `try-convert` 클래스 라이브러리의 프로젝트 파일이 있는 폴더에서를 실행할 수 있습니다.

다음 명령을 사용 하 여 .NET 업그레이드 도우미를 설치 합니다 (try-convert 설치 후).

```dotnetcli
dotnet tool install -g upgrade-assistant
```

프로젝트 파일이 있는 폴더의 명령을 사용 하 여 도구를 실행 합니다 `upgrade-assistant <project>` .

## <a name="update-nuget-package-dependencies"></a>NuGet 패키지 종속성 업데이트

타사 NuGet 패키지의 사용을 분석 하 고 아직 .NET Standard 지원 하지 않는 (또는 새 버전 에서만 지원) 지원 하는지 확인 합니다. [ `<PackageReference>` Visual Studio의 변환기 도구를 사용 하 여 구문을 사용 하도록 NuGet 패키지를 업데이트](/nuget/consume-packages/migrate-packages-config-to-package-reference)하는 것이 유용할 수 있으므로 최상위 종속성이 표시 됩니다. 다음으로 이러한 패키지의 현재 버전 이상에서 .NET Core를 지원 하는지 또는 .NET Standard을 지원 하는지 확인 합니다. 이 정보는 [nuget.org] 또는 각 패키지에 대 한 Visual Studio 내에서 찾을 수 있습니다.

현재 앱이 사용 하는 패키지의 버전을 사용 하 여 지원이 있는 경우 유용 합니다! 그렇지 않은 경우 최신 버전의 패키지가 지원 되는지 여부를 확인 하 고 업그레이드에 관련 된 내용을 조사 합니다. 특히 패키지의 주 버전이 현재 사용 된 버전과 업그레이드 중인 버전 간에 변경 되는 경우 패키지의 주요 변경 내용이 있을 수 있습니다.

경우에 따라 지정 된 패키지의 버전은 .NET Core에서 작동 하지 않습니다. 이 경우 팀에는 몇 가지 옵션이 있습니다. 이러한 작업은 .NET Framework 버전에 따라 계속할 수 있지만 여기에는 제한이 있습니다. 앱은 Windows 에서만 실행 되며, 팀은 패키지의 이진 파일에 대해 이식성 분석기를 실행 하 여 문제가 발생할 가능성이 있는지 확인 하는 것이 좋습니다. 팀이 철저히 테스트 하려고 합니다. 다른 옵션은 다른 패키지를 찾거나 필요한 패키지가 오픈 소스인 경우 .NET Standard 또는 .NET Core 자체로 업그레이드 하는 것입니다.

## <a name="migrate-aspnet-mvc-projects"></a>ASP.NET MVC 프로젝트 마이그레이션

`System.Web`네임 스페이스 및 형식은 .Net Core에 존재 하지 않습니다. 종속성을 분석 하 고와 같은 도구를 사용 하 `try-convert` 는 경우 ASP.NET MVC 프로젝트의 자동 마이그레이션과를 참조 하는 모든 코드에 대 한 많은 제안을 제공 하지 않습니다 `System.Web` . 이러한 프로젝트의 경우 새 ASP.NET Core 웹 프로젝트로 시작 하 고이 프로젝트에 파일을 수동으로 마이그레이션해야 합니다.

일반적으로 앱의 비즈니스 논리가 사용자 인터페이스 계층에 얼마나 많은 지를 최소화 하는 것이 좋습니다. 컨트롤러와 뷰를 작게 유지 하는 것도 좋습니다. 이 지침을 따르는 앱은 ASP.NET 웹 프로젝트에서 상당한 양의 논리를 포함 하는 것 보다 더 쉽게 이식할 수 있습니다. 포팅 하는 앱이 있지만 아직 프로세스를 시작 하지 않은 경우 유지 관리 하는 것을 염두에 두어야 합니다. ASP.NET MVC 또는 Web API 프로젝트에 포함 되는 코드의 양을 최소화 하기 위해 수행 하는 모든 작업은 앱을 이식할 때 시간이 소요 될 때 작업을 줄일 수 있습니다.

다음 장은 ASP.NET MVC 및 Web API 프로젝트에서 ASP.NET Core 프로젝트로 마이그레이션하는 방법에 대 한 세부 정보입니다. 이전 챕터는 앱 간의 가장 큰 차이를 호출 했습니다. 기본 프로젝트 구조가 준비 되 면 일반적으로 개별 컨트롤러와 뷰를 쉽게 마이그레이션할 수 있습니다. 특히 주로 웹 업무에 중점을 두는 것입니다.

## <a name="references"></a>참조

- [.NET 업그레이드 도우미 도구](https://aka.ms/dotnet-upgrade-assistant)
- [시도 변환 도구](https://github.com/dotnet/try-convert)
- [apiport 도구](https://github.com/microsoft/dotnet-apiport)

>[!div class="step-by-step"]
>[이전](identify-migration-sequence.md)
>[다음](strategies-migrating-in-production.md)
