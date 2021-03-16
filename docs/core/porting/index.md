---
title: .NET Framework에서 .NET 5로 이식
description: 이식 프로세스를 이해하고 .NET Framework 프로젝트를 .NET 5(및 .NET Core 3.1)로 이식할 때 유용한 도구에 관해 알아보세요.
author: adegeo
ms.date: 03/03/2020
no-loc:
- package.config
- PackageReference
ms.openlocfilehash: 8515689cf4a1be917f12bb8f3315cda89988d773
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605050"
---
# <a name="overview-of-porting-from-net-framework-to-net"></a>.NET Framework에서 .NET로의 이식 개요

이 문서에서는 .NET Framework에서 .NET(이전 이름은 .NET Core)으로 코드를 이식할 때 고려해야 할 사항의 개요를 제공합니다. 프로젝트가 여러 개일 때 .NET Framework에서 .NET으로 이식하는 작업은 비교적 간단합니다. 프로젝트의 복잡도에 따라 프로젝트 파일의 초기 마이그레이션 후에 수행할 작업의 양이 결정됩니다.

.NET에서 앱 모델을 사용할 수 있는 프로젝트(라이브러리, 콘솔 앱, 데스크톱 앱 등)에는 보통 적은 수의 변경만 필요합니다. ASP.NET에서 ASP.NET Core로 이동하는 것처럼 새 앱 모델이 필요한 프로젝트에는 더 많은 작업이 필요합니다. 이전 앱 모델의 여러 패턴과 동등한 패턴을 변환 중에 사용할 수 있습니다.

## <a name="unavailable-technologies"></a>사용할 수 없는 기술

.NET Framework에는 .NET에 없는 기술이 몇 가지 있습니다.

- [애플리케이션 도메인](net-framework-tech-unavailable.md#application-domains)

  추가 애플리케이션 도메인 만들기는 지원되지 않습니다. 코드 격리의 경우 별도의 프로세스 또는 컨테이너를 대신 사용하세요.

- [원격 통신](net-framework-tech-unavailable.md#remoting)

  원격 통신은 더 이상 지원되지 않는 애플리케이션 도메인 간의 통신에 사용됩니다. 프로세스 간 통신을 위해 <xref:System.IO.Pipes> 클래스 또는 <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> 클래스 같은 IPC(Inter-process communication) 메커니즘을 원격 대신 사용할 수 있습니다.

- [CAS(코드 액세스 보안)](net-framework-tech-unavailable.md#code-access-security-cas)

  CAS는 .NET Framework에서 지원하는 샌드박싱 기술이지만 .NET Framework 4.0에서는 사용되지 않습니다. CAS는 보안 투명도로 대체되었으며 .NET에서는 지원되지 않습니다. 대신 가상화, 컨테이너 또는 사용자 계정과 같이 운영 체제에서 제공하는 보안 경계를 사용하세요.

- [보안 투명도](net-framework-tech-unavailable.md#security-transparency)

  CAS와 마찬가지로 이 샌드박싱 기술은 .NET Framework 애플리케이션에 더 이상 권장되지 않으며 .NET에서 지원되지 않습니다. 대신 가상화, 컨테이너 또는 사용자 계정과 같이 운영 체제에서 제공하는 보안 경계를 사용하세요.
  
- <xref:System.EnterpriseServices?displayProperty=fullName>

  <xref:System.EnterpriseServices?displayProperty=fullName> (COM+)는 .NET에서 지원되지 않습니다.

- Windows Workflow Foundation(WF) 및 Windows Communication Foundation(WCF)

  WF와 WCF는 .NET Core를 포함하여 .NET 5 이상에서 지원되지 않습니다. 대체 방법은 [CoreWF](https://github.com/UiPath/corewf) 및 [CoreWCF](https://github.com/CoreWCF/CoreWCF)를 참조하세요.

지원되지 않는 이러한 기술에 대한 자세한 내용은 [.NET Core와 .NET 5 이상에서 사용할 수 없는 .NET Framework 기술](net-framework-tech-unavailable.md)을 참조하세요.

## <a name="windows-desktop-technologies"></a>Windows 데스크톱 기술

.NET Framework용으로 만든 많은 애플리케이션이 Windows Forms 또는 WPF(Windows Presentation Foundation)와 같은 데스크톱 기술을 사용합니다. Windows Forms와 WPF 모두 .NET으로 이식되었지만 여전히 Windows 전용 기술입니다.

Windows Forms 또는 WPF 애플리케이션을 마이그레이션하기 전에 다음 종속성을 고려하세요.

01. .NET용 프로젝트 파일은 .NET Framework와는 다른 형식을 사용합니다.
01. .NET에서 사용할 수 없는 API가 프로젝트에서 사용될 수 있습니다.
01. 타사 컨트롤 및 라이브러리가 .NET으로 이식되지 않아 .NET Framework에만 사용할 수 있습니다.
01. .NET에서 [더 이상 사용할 수 없는 기술](net-framework-tech-unavailable.md)이 프로젝트에서 사용됩니다.

.NET은 Windows Forms 및 WPF의 오픈 소스 버전을 사용하며 .NET Framework보다 향상된 기능을 포함합니다.

데스크톱 애플리케이션을 .NET 5로 마이그레이션하는 방법에 대한 자습서는 다음 문서 중 하나를 참조하세요.

- [.NET Framework WPF 앱을 .NET으로 마이그레이션](/dotnet/desktop/wpf/migration/convert-project-from-net-framework?view=netdesktop-5.0&preserve-view=true)
- [.NET Framework Windows Forms 앱을 .NET으로 마이그레이션](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)

## <a name="windows-specific-apis"></a>Windows 특정 API

애플리케이션은 .NET이 지원하는 플랫폼에서 네이티브 라이브러리를 여전히 P/Invoke할 수 있습니다. 이 기술은 Windows로 제한되지 않습니다. 그러나 참조하는 라이브러리가 _user32.dll_ 또는 _kernel32.dll_ 과 같은 Windows 특정 라이브러리인 경우 코드는 Windows에서만 작동합니다. 앱을 실행하려는 각 플랫폼마다 플랫폼별 버전을 찾거나 모든 플랫폼에서 실행할 수 있도록 코드를 충분히 제네릭하게 만들어야 합니다.

애플리케이션을 .NET Framework에서 .NET으로 이식하는 경우 애플리케이션은 .NET Framework와 함께 배포된 라이브러리를 사용했을 수 있습니다. .NET Framework에서 사용할 수 있는 여러 API는 Windows 레지스트리 또는 GDI+ 그리기 모델과 같은 Windows 특정 기술에 의존하기 때문에 .NET으로 이식되지 않았습니다.

**Windows 호환성 팩** 은 .NET Framework API 표면의 많은 부분을 .NET에 제공하며, [Microsoft.Windows.Compatibility NuGet 패키지](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)를 통해 제공됩니다.

자세한 내용은 [Windows 호환성 팩을 사용하여 코드를 .NET Core로 이식](windows-compat-pack.md)을 참조하세요.

## <a name="net-framework-compatibility-mode"></a>.NET Framework 호환 모드

.NET Framework 호환 모드는 .NET Standard 2.0에서 도입되었습니다. 이 호환 모드를 통해 .NET Standard 및 .NET 5 이상(및 .NET Core 3.1) 프로젝트가 Windows 전용 .NET Framework 라이브러리를 참조할 수 있습니다. .NET Framework 라이브러리 참조는 라이브러리가 WPF(Windows Presentation Foundation) API를 사용하는 것처럼 모든 프로젝트에 대해 작동하지 않지만 많은 이식 시나리오를 차단 해제합니다. 자세한 내용은 [.NET Framework에서 .NET으로 코드를 이식하기 위한 종속성 분석](third-party-deps.md#net-framework-compatibility-mode)을 참조하세요.

## <a name="cross-platform"></a>플랫폼 간 사용 가능

.NET(이전 이름은 .NET Core)은 플랫폼 간에 사용 가능하도록 설계되었습니다. Windows 특정 기술에 의존하지 않는 코드는 macOS, Linux, Android 등의 다른 플랫폼에서 실행될 수 있습니다. 여기에는 다음과 같은 프로젝트 형식이 포함됩니다.

- 라이브러리
- 콘솔 기반 도구
- Automation
- ASP.NET 사이트

.NET Framework은 Windows 전용 구성 요소입니다. Windows Forms 및 WPF(Windows Presentation Foundation) 같은 Windows 특정 기술이나 API를 사용하는 코드는 .NET에서 계속 실행될 수 있지만 다른 운영 체제에서는 실행되지 않습니다.

라이브러리 또는 콘솔 기반 애플리케이션을 많이 변경하지 않고도 플랫폼 간에 사용할 수 있습니다. .NET으로 이식할 때 이를 고려하고 다른 플랫폼에서 애플리케이션을 테스트하는 것이 좋습니다.

## <a name="the-future-of-net-standard"></a>.NET Standard의 미래

[.NET Standard](https://github.com/dotnet/standard)는 여러 .NET 구현에서 사용할 수 있는 .NET API의 공식 규격입니다. .NET Standard는 .NET 에코시스템의 통일성을 높이기 위한 것이었습니다. .NET 5부터 통일성을 위한 다른 접근 방식이 채택되었으며, 이 새로운 접근 방식으로 많은 시나리오에서 .NET Standard가 필요 없어집니다. 자세한 내용은 [.NET 5 및 .NET Standard](../../standard/net-standard.md#net-5-and-net-standard)를 참조하세요.

.NET Standard 2.0은 .NET Framework를 지원하는 마지막 버전이었습니다.

## <a name="tools-to-assist-porting"></a>이식 지원 도구

애플리케이션을 .NET Framework에서 .NET으로 수동으로 이식하는 대신 다양한 도구를 사용하여 마이그레이션의 일부 측면을 자동화할 수 있습니다. 복잡한 프로젝트 이식은 그 자체가 복잡한 프로세스입니다. 이러한 도구가 이 과정에서 도움이 될 수 있습니다.

애플리케이션 이식에 도움이 되는 도구를 사용하는 경우에도 이 문서의 [이식 시 고려 사항 섹션](#considerations-when-porting)을 검토해야 합니다.

### <a name="net-upgrade-assistant"></a>.NET 업그레이드 도우미

[.NET 업그레이드 도우미](upgrade-assistant-overview.md)는 다양한 종류의 .NET Framework 앱에서 실행할 수 있는 명령줄 도구입니다. 이 도구는 .NET Framework 앱을 .NET 5로 업그레이드하는 데 도움이 되도록 설계되었습니다. 도구를 실행한 후 **앱 마이그레이션을 완료하려면 더 많은 작업이 필요한 경우가 대부분** 입니다. 이 도구에는 마이그레이션 완료에 도움이 될 수 있는 분석기 설치가 포함됩니다. 이 도구가 작동하는 .NET Framework 애플리케이션 유형은 다음과 같습니다.

- Windows Forms
- WPF
- ASP.NET MVC
- 콘솔
- 클래스 라이브러리

이 도구는 이 문서에 나열된 다른 도구를 사용하고 마이그레이션 프로세스를 안내합니다. 도구에 대한 자세한 내용은 [.NET 업그레이드 도우미 개요](upgrade-assistant-overview.md)를 참조하세요.

### <a name="try-convert"></a>try-convert

try-convert 도구는 데스크톱 앱을 .NET 5로 이동하는 것을 포함하여 프로젝트나 전체 솔루션을 .NET SDK로 변환할 수 있는 .NET 전역 도구입니다. 다만 프로젝트에 사용자 지정 작업, 대상 또는 가져오기와 같은 복잡한 빌드 프로세스가 있는 경우에는 이 도구를 권장하지 않습니다.

자세한 내용은 [try-convert GitHub 리포지토리](https://github.com/dotnet/try-convert)를 참조하세요.

### <a name="net-portability-analyzer"></a>.NET 이식성 분석기

.NET 이식성 분석기는 어셈블리를 분석하고, 지정된 대상 .NET 플랫폼에 애플리케이션 또는 라이브러리를 이식하는 데 필요한 누락된 .NET API에 대한 자세한 보고서를 제공하는 도구입니다.

Visual Studio에서 .NET 이식성 분석기를 사용하려면 [마켓플레이스에서 확장](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)을 설치하세요.

자세한 내용은 [.NET 이식성 분석기](../../standard/analyzers/portability-analyzer.md)를 참조하세요.

### <a name="net-api-analyzer"></a>.NET API 분석기

[.NET API 분석기](../../standard/analyzers/api-analyzer.md)는 런타임에 <xref:System.PlatformNotSupportedException>을 throw하는 API를 사용하고 있는지 여부를 분석합니다. .NET Framework 4.7.2 이상에서 이식할 때 이 예외가 throw되는 경우는 드물긴 하지만 확인하는 것이 좋습니다. .NET에서 예외를 throw하는 API에 대한 자세한 내용은 [.NET Core에서 항상 예외를 throw하는 API](../compatibility/unsupported-apis.md)를 참조하세요.

API 분석기는 프로젝트에 추가하는 NuGet 패키지인 [Microsoft.DotNet.Analyzers.Compatibility](https://www.nuget.org/packages/Microsoft.DotNet.Analyzers.Compatibility/)로 제공됩니다.

자세한 내용은 [.NET API 분석기](../../standard/analyzers/api-analyzer.md)를 참조하세요.

## <a name="considerations-when-porting"></a>이식 시 고려 사항

애플리케이션을 .NET으로 이식하는 경우 다음 제안 사항을 순서대로 고려하세요.

✔️ [.NET 업그레이드 도우미](upgrade-assistant-overview.md)를 사용하여 프로젝트를 마이그레이션하는 것이 좋습니다. 이 도구는 미리 보기 상태이지만 이 문서에서 설명하는 대부분의 수동 단계를 자동화하고 마이그레이션 경로를 계속하기 위한 좋은 출발점을 제공합니다.

✔️ 종속성을 먼저 조사하는 것이 좋습니다. 종속성은 .NET 5, .NET Standard 또는 .NET Core를 대상으로 지정해야 합니다.

✔️ NuGet _packages.config_ 파일에서 프로젝트 파일의 [PackageReference](/nuget/consume-packages/package-references-in-project-files) 설정으로 마이그레이션하세요. Visual Studio를 사용하여 [ _package.config_ 파일을 변환하세요](/nuget/consume-packages/migrate-packages-config-to-package-reference#migration-steps).

✔️ 앱을 아직 이식할 수 없더라도 최신 프로젝트 파일 형식으로 업그레이드하는 것이 좋습니다. .NET Framework 프로젝트는 오래된 프로젝트 형식을 사용합니다. SDK 스타일 프로젝트라고 하는 최신 프로젝트 형식은 .NET Core 이상을 위해 만들어졌지만 .NET Framework에서도 작동합니다. 프로젝트 파일이 최신 형식이면 나중에 앱을 이식할 수 있는 좋은 기반이 됩니다.

✔️ .NET Framework 프로젝트의 대상을 .NET Framework 4.7.2 이상으로 변경하세요. 그러면 .NET Standard에서 기존 API를 지원하지 않는 경우 최신 API를 대신 사용할 수 있습니다.

✔️ .NET Core 3.1 대신 .NET 5를 대상으로 지정하는 것이 좋습니다. .NET Core 3.1은 LTS(장기 지원)에 포함되지만 .NET 5가 최신 버전이며 .NET 6는 릴리스되면 LTS가 됩니다.

✔️ **Windows Forms 및 WPF** 프로젝트의 경우 .NET 5를 대상으로 지정하세요. .NET 5에는 데스크톱 앱을 위한 향상된 기능이 많이 포함되어 있습니다.

✔️ .NET Framework 프로젝트에도 사용할 수 있는 라이브러리를 마이그레이션하는 경우 .NET Standard 2.0을 대상으로 지정하는 것이 좋습니다. 라이브러리를 다중 대상 지정하여 .NET Framework와 .NET Standard를 모두 대상으로 지정할 수도 있습니다.

✔️ 마이그레이션 후 누락된 API 오류가 발생하는 경우 [Microsoft.Windows.Compatibility NuGet 패키지](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)에 대한 참조를 추가하세요. .NET Framework API 표면의 많은 부분은 NuGet 패키지를 통해 .NET에서 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [.NET 업그레이드 도우미 개요](upgrade-assistant-overview.md)
- [ASP.NET에서 ASP.NET Core로 마이그레이션](/aspnet/core/migration/proper-to-2x)
- [.NET Framework WPF 앱을 .NET으로 마이그레이션](/dotnet/desktop/wpf/migration/convert-project-from-net-framework?view=netdesktop-5.0&preserve-view=true)
- [.NET Framework Windows Forms 앱을 .NET으로 마이그레이션](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
- [.NET으로 .NET Framework 라이브러리 이식](libraries.md)
- [서버 앱에 대한 .NET 5와 .NET Framework 비교](../../standard/choosing-core-framework-server.md)
