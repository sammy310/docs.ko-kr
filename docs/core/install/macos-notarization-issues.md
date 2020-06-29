---
title: macOS Catalina 공증 관련 사항
description: .NET Core로 빌드된 .NET Core 런타임, SDK 및 앱을 설치할 때 macOS의 공증 및 인증 문제를 처리하는 방법.
author: adegeo
ms.author: adegeo
ms.date: 02/14/2020
ms.openlocfilehash: cd3886b2e772a182156d212aefb9705a3fb5e17c
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324625"
---
# <a name="macos-catalina-notarization-and-the-impact-on-net-core-downloads-and-projects"></a>macOS Catalina 공증과 이것이 .NET Core 다운로드 및 프로젝트에 미치는 영향

macOS Catalina(버전10.15)부터, 2019년 6월 1일 이후에 빌드되어 개발자 ID로 배포되는 모든 소프트웨어는 공증을 받아야 합니다. 이 요구 사항은 .NET Core 런타임, .NET Core SDK, 그리고 .NET Core로 만든 소프트웨어에 적용됩니다. 이 문서에서는 .NET Core 및 macOS 공증과 관련하여 자주 발생하는 시나리오에 대해 설명합니다.

## <a name="installing-net-core"></a>.NET Core 설치

.NET Core(런타임 및 SDK) 버전 3.1, 3.0, 2.1용 설치 프로그램은 2020년 2월 18일부터 공증되었습니다. 그 전에 릴리스된 버전은 공증되지 않았습니다. 공증되지 않은 버전의 .NET Core는 먼저 설치 프로그램을 다운로드한 다음 `sudo installer` 명령을 사용하여 수동으로 설치할 수 있습니다. 자세한 내용은 [Download and manually install for macOS](sdk.md?pivots=os-macos#download-and-manually-install)(macOS에 대해 다운로드 및 수동 설치)를 참조하세요.

아래의 버전부터는 .NET Core 설치 프로그램이 공증됩니다.

- .NET Core 런타임
  - 2.1.16
  - 3.0.3
  - 3.1.2

- .NET Core SDK
  - 2.1.512
  - 3.0.103
  - 3.1.102

## <a name="apphost-is-disabled-by-default"></a>appHost는 기본적으로 사용하지 않도록 설정됩니다.

기본적으로, .NET Core SDK 3.0 이상의 공증되지 않은 버전은 프로젝트가 컴파일, 게시 또는 실행되면 네이티브 Mach-O 실행 파일(**appHost**)을 생성합니다. 이 실행 파일은 앱을 편리하게 실행하는 한 가지 방법입니다. 이 실행 파일을 사용하지 않고 앱을 시작하려면 `dotnet <filename.dll>`을 실행해야 합니다. appHost가 사용하도록 설정되면 `dotnet run` 명령이 appHost의 컨텍스트에서 호출됩니다. 자세한 내용은 [appHost의 컨텍스트](#context-of-the-apphost)를 참조하세요.

.NET Core SDK 3.0 이상의 공증된 버전부터, appHost 실행 파일이 기본적으로 실행되지 않습니다. 프로젝트 파일의 [`UseAppHost`](../project-sdk/msbuild-props.md#useapphost) 부울 설정을 사용하여 appHost가 생성되도록 설정할 수 있습니다. 명령줄에서 `-p:UseAppHost` 매개 변수를 사용하여 실행하는 특정 `dotnet` 명령에 대해 appHost를 켜거나 끌 수도 있습니다.

- 프로젝트 파일

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- 명령줄 매개 변수

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

appHost는 앱을 [자체 포함](../deploying/index.md#publish-self-contained) 방식으로 게시하면 항상 만들어집니다.

`UseAppHost` 설정에 대한 자세한 내용은 [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost)(Microsoft.NET.Sdk의 MSBuild 속성)를 참조하세요.

### <a name="context-of-the-apphost"></a>appHost의 컨텍스트

프로젝트에서 appHost가 사용하도록 설정된 상태에서 `dotnet run` 명령을 사용하여 앱을 실행하면 앱이 기본 호스트(기본 호스트는 `dotnet` 명령임)가 아닌 appHost의 컨텍스트에서 호출됩니다. 프로젝트에서 appHost를 사용하지 않도록 설정된 경우 `dotnet run` 명령이 기본 호스트의 컨텍스트에서 앱을 실행합니다. appHost를 사용하지 않도록 설정된 경우에도 앱을 자체 포함 방식으로 게시하면 appHost 실행 파일이 생성되고, 사용자가 해당 실행 파일을 사용하여 앱을 실행할 수 있습니다. `dotnet <filename.dll>`을 사용하여 앱을 실행하면 기본 호스트인 공유 런타임으로 앱이 호출됩니다.

appHost를 사용하는 앱이 호출될 경우, 앱에서 액세스하는 인증서 파티션은 공증된 기본 호스트와 다릅니다. 앱에서 기본 호스트를 통해 설치된 인증서에 액세스해야 하는 경우, `dotnet run` 명령을 사용하여 앱을 프로젝트 파일에서 실행하거나 `dotnet <filename.dll>` 명령을 사용하여 앱을 직접 시작하세요.

[ASP.NET Core 및 macOS와 인증서](#aspnet-core-and-macos-and-certificates) 섹션에서 이 시나리오에 대한 자세한 내용을 확인할 수 있습니다.

## <a name="aspnet-core-and-macos-and-certificates"></a>ASP.NET Core 및 macOS와 인증서

.NET Core는 macOS 키체인에서 <xref:System.Security.Cryptography.X509Certificates> 클래스로 인증서를 관리하는 기능을 제공합니다. macOS 키체인에 대한 액세스에서는 어느 파티션을 고려해야 할지 결정할 때 애플리케이션 ID를 기본 키로 사용합니다. 예를 들어, 서명되지 않은 애플리케이션은 비밀을 서명되지 않은 파티션에 저장하지만, 서명된 애플리케이션은 비밀을 해당 애플리케이션에서만 액세스할 수 있는 파티션에 저장합니다. 앱을 호출하는 실행 파일의 소스가 어느 파티션을 사용할지를 결정합니다.

.NET Core는 [appHost](#apphost-is-disabled-by-default), 기본 호스트(`dotnet` 명령), 사용자 지정 호스트와 같은 3가지 소스의 실행을 제공합니다. 각 실행 모델에는 서명되었거나 서명되지 않은 서로 다른 ID를 가질 수 있으며, 키체인 내의 서로 다른 파티션에 대한 액세스를 갖습니다. 하나의 모드로 가져온 인증서는 다른 모드에서 액세스하지 못할 수 있습니다. 예를 들어, .NET Core의 공증된 버전에는 서명된 기본 호스트가 있습니다. 인증서는 그 ID에 따라 보안 파티션으로 가져와집니다. appHost는 서명되지 않았으므로 appHost에서 이러한 인증서에 액세스할 수 없습니다.

또 다른 예로, 기본적으로 ASP.NET Core는 기본 호스트를 통해 기본 SSL 인증서를 가져옵니다. appHost를 사용하는 ASP.NET Core 애플리케이션은 이 인증서에 액세스할 수 없으며, .NET Core에서 이 인증서에 액세스할 수 없다는 사실을 감지하면 오류가 발생합니다. 오류 메시지는 이 문제를 해결하는 방법에 대한 지침을 제공합니다.

인증서 공유가 필요한 경우, macOS는 `security` 유틸리티를 통해 구성 옵션을 제공합니다.

ASP.NET Core 인증서 문제를 해결하는 방법에 대한 자세한 내용은 [Enforce HTTPS in ASP.NET Core](/aspnet/core/security/enforcing-ssl?view=aspnetcore-3.1&tabs=visual-studio#troubleshoot-certificate-problems)(ASP.NET Core에서 HTTPS 강제 적용)를 참조하세요.

## <a name="default-entitlements"></a>기본 자격

.NET Core의 기본 호스트(`dotnet` 명령)는 기본 자격 집합을 갖습니다. 이러한 자격은 .NET Core가 올바르게 작동하는 데 필요합니다. 애플리케이션에 그 밖의 자격이 필요한 경우가 있는데, 이 경우 [appHost](#apphost-is-disabled-by-default)를 생성하여 사용한 다음 로컬에서 필수 자격을 추가해야 합니다.

.NET Core의 기본 자격 집합

- `com.apple.security.cs.allow-jit`
- `com.apple.security.cs.allow-unsigned-executable-memory`
- `com.apple.security.cs.allow-dyld-environment-variables`
- `com.apple.security.cs.disable-library-validation`

## <a name="notarize-a-net-core-app"></a>.NET Core 앱 공증하기

애플리케이션을 macOS Catalina(버전 10.15) 이상에서 실행하려면 앱을 공증해야 합니다. 공증을 위해 애플리케이션과 함께 제출하는 appHost에는 .NET Core의 [기본 자격](#default-entitlements)과 같거나 높은 기본 자격을 사용해야 합니다.

## <a name="next-steps"></a>다음 단계

- [..NET Core 종속성 및 요구 사항](dependencies.md)
- [Install the .NET Core SDK](sdk.md)(.NET Core SDK 설치)
- [.NET Core 런타임 설치](runtime.md)
