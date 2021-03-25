---
title: Windows 호환성 팩을 사용하여 코드 포팅
description: Windows 호환성 팩에 대해 알아보고 이를 사용하여 기존 .NET Framework 코드를 .NET 5 및 .NET Core 3.1로 포팅하는 방법을 알아봅니다.
author: terrajobst
ms.date: 03/04/2021
ms.openlocfilehash: c90cc960cd9ff3707877afc023f95e0e03716aab
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604816"
---
# <a name="use-the-windows-compatibility-pack-to-port-code-to-net-5"></a>Windows 호환성 팩을 사용하여 코드를 .NET 5 이상으로 포팅

기존 코드를 .NET Framework에서 .NET으로 포팅할 때 가장 일반적인 문제 중 일부는 .NET Framework에만 있는 API 및 기술에 대한 종속성입니다. *Windows 호환성 팩* 은 이러한 기술을 대부분 제공하므로 .NET 애플리케이션과 .NET Standard 라이브러리를 훨씬 쉽게 빌드할 수 있습니다.

호환성 팩은 API 집합을 크게 늘리는 [.NET Standard 2.0의 논리적 확장](../whats-new/dotnet-core-2-0.md#api-changes-and-library-support)입니다. 기존 코드는 거의 수정하지 않고 컴파일됩니다. "모든 .NET 구현이 제공하는 API 집합" 약속을 지키기 위해 .NET Standard에는 레지스트리, WMI(Windows Management Instrumentation) 또는 리플렉션 내보내기 API와 같은 모든 플랫폼에서 작동할 수 없는 기술은 포함하지 않습니다. Windows 호환 기능 팩은 .NET Standard의 위에 있으며 해당 Windows 전용 기술에 대한 액세스 권한을 제공합니다. .NET으로 이동하려고 하지만 적어도 첫 번째 단계로 Windows에 머물려는 고객에게 특히 유용합니다. 이 시나리오에서는 Windows 전용 기술을 사용하여 마이그레이션 장애물을 제거할 수 있습니다.

## <a name="package-contents"></a>패키지 내용

Windows 호환성 팩은 [Microsoft.Windows.Compatibility NuGet 패키지](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)를 통해 제공되며 .NET 또는 .NET Standard를 대상으로 하는 프로젝트에서 참조할 수 있습니다.

다음 기술 영역에서 Windows 전용 및 플랫폼 간 API를 포함하여 약 20,000개의 API를 제공합니다.

- 코드 페이지
- CodeDom
- 구성
- 디렉터리 서비스
- 그리기
- ODBC
- 권한
- 포트
- Windows ACL(액세스 제어 목록)
- WCF(Windows Communication Foundation)
- Windows Cryptography
- Windows EventLog
- Windows Management Instrumentation(WMI)
- Windows 성능 카운터
- Windows 레지스트리
- Windows 런타임 캐싱
- Windows 서비스

자세한 내용은 [호환성 팩의 사양](https://github.com/dotnet/designs/blob/master/accepted/2018/compat-pack/compat-pack.md)을 참조하세요.

## <a name="get-started"></a>시작하기

1. 이식하기 전에 [이식 프로세스](index.md)를 참조하세요.

2. 기존 코드를 .NET 또는 .NET Standard로 이식하는 경우 [Microsoft.Windows.Compatibility NuGet 패키지](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)를 설치합니다.

   Windows에서 유지하려는 경우 모두 준비되었습니다.

3. Linux 또는 macOS에서 .NET 애플리케이션 또는 .NET Standard 라이브러리를 실행하려는 경우 [API 분석기](../../standard/analyzers/api-analyzer.md)를 사용하여 플랫폼 간에 작동하지 않는 API의 사용량을 찾습니다.

4. 이러한 API의 사용량을 제거하거나 플랫폼 간 대체 방법으로 바꾸거나 다음과 같은 플랫폼 검사를 사용하여 보호합니다.

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

데모의 경우 [Windows 호환 기능 팩의 Channel 9 비디오](https://channel9.msdn.com/Events/Connect/2017/T123)를 확인하세요.

## <a name="see-also"></a>참고 항목

- [.NET Framework에서 .NET으로 포팅 개요](index.md)
- [ASP.NET에서 ASP.NET Core로 마이그레이션](/aspnet/core/migration/proper-to-2x)
- [.NET Framework WPF 앱을 .NET으로 마이그레이션](/dotnet/desktop/wpf/migration/convert-project-from-net-framework?view=netdesktop-5.0&preserve-view=true)
- [.NET Framework Windows Forms 앱을 .NET으로 마이그레이션](/dotnet/desktop/winforms/migration/?view=netdesktop-5.0&preserve-view=true)
- [.NET으로 .NET Framework 라이브러리 포팅](libraries.md)
