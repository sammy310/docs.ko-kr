---
title: .NET의 구성
description: 구성 API를 사용하여 .NET 애플리케이션을 구성하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 09/16/2020
ms.topic: overview
ms.openlocfilehash: 5955e46c2f5acb6776ada4e3fd6a65507d3faa1f
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "102402111"
---
# <a name="configuration-in-net"></a>.NET의 구성

.NET의 구성은 하나 이상의 [구성 공급자](#configuration-providers)를 사용하여 수행합니다. 구성 공급자는 다음과 같은 다양한 구성 소스를 사용하여 키-값 쌍에서 구성 데이터를 읽습니다.

- 설정 파일(예: *appsettings.json*)
- 환경 변수
- [Azure Key Vault](/azure/key-vault/general/overview)
- [Azure App Configuration](/azure/azure-app-configuration/overview)
- 명령줄 인수
- 설치되거나 만들어진 사용자 지정 공급자
- 디렉터리 파일
- 메모리 내 .NET 개체

## <a name="configure-console-apps"></a>콘솔 앱 구성

[dotnet new](../tools/dotnet-new.md) 또는 Visual Studio를 사용하여 만든 새 .NET 콘솔 애플리케이션은 기본적으로 구성 기능을 공개하지 ‘않습니다’. 새 .NET 콘솔 애플리케이션에서 구성을 추가하려면 `Microsoft.Extensions.Hosting`에 [패키지 참조를 추가](../tools/dotnet-add-package.md)합니다. 다음 코드와 일치하도록 *Program.cs* 파일을 수정합니다.

:::code language="csharp" source="snippets/configuration/console/Program.cs" highlight="18":::

<xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])?displayProperty=nameWithType> 메서드는 다음 순서로 앱의 기본 구성을 제공합니다.

1. [ChainedConfigurationProvider](xref:Microsoft.Extensions.Configuration.ChainedConfigurationSource): 기존 `IConfiguration`을 소스로 추가합니다.
1. [JSON 구성 공급자](configuration-providers.md#file-configuration-provider)를 사용하는 *appsettings.json*
1. [JSON 구성 공급자](configuration-providers.md#file-configuration-provider)를 사용하는 *appsettings.* `Environment` *.json*. 예: *appsettings*.***Production**_._json* 및 *appsettings*.***Development** _._json*.
1. 앱이 `Development` 환경에서 실행되는 경우 앱 비밀
1. [환경 변수 구성 공급자](configuration-providers.md#environment-variable-configuration-provider)를 사용하는 환경 변수
1. [명령줄 구성 공급자](configuration-providers.md#command-line-configuration-provider)를 사용하는 명령줄 인수

나중에 추가된 구성 공급자는 이전 키 설정을 재정의합니다. 예를 들어 `SomeKey`가 *appsettings.json* 과 환경 모두에서 설정된 경우 환경 값이 사용됩니다. [명령줄 구성 공급자](configuration-providers.md#command-line-configuration-provider)는 기본 구성 공급자를 사용하여 다른 모든 공급자를 재정의합니다.

### <a name="binding"></a>바인딩

.NET의 구성에 관련된 주요 이점 중 하나는 구성 값을 .NET 개체 인스턴스에 바인딩하는 기능입니다. 예를 들어, JSON 구성 공급자는 *appsettings.json* 파일을 .NET 개체에 매핑하는 데 사용될 수 있으며 종속성 주입과 함께 사용됩니다. 이를 통해 옵션 패턴을 사용할 수 있으며 옵션 패턴은 클래스를 사용하여 관련 설정 그룹에 대한 강력한 형식의 액세스를 제공합니다.

## <a name="configuration-providers"></a>구성 공급자

다음 표에서는 .NET Core 앱에서 사용할 수 있는 구성 공급자를 보여 줍니다.

| 공급자                                                                                                               | 다음에서 구성 제공        |
|------------------------------------------------------------------------------------------------------------------------|------------------------------------|
| [Azure 앱 구성 공급자](/azure/azure-app-configuration/quickstart-aspnet-core-app)                          | Azure App Configuration            |
| [Azure Key Vault 구성 공급자](/azure/key-vault/general/tutorial-net-virtual-machine)                        | Azure Key Vault                    |
| [명령줄 구성 공급자](configuration-providers.md#command-line-configuration-provider)                  | 명령줄 매개 변수            |
| [사용자 지정 구성 공급자](custom-configuration-provider.md)                                                      | 사용자 지정 소스                      |
| [환경 변수 구성 공급자](configuration-providers.md#environment-variable-configuration-provider) | 환경 변수              |
| [파일 구성 공급자](configuration-providers.md#file-configuration-provider)                                  | JSON, XML, INI 파일           |
| [파일별 키 구성 공급자](configuration-providers.md#key-per-file-configuration-provider)                  | 디렉터리 파일                    |
| [메모리 구성 공급자](configuration-providers.md#memory-configuration-provider)                              | 메모리 내 컬렉션              |
| [앱 비밀(비밀 관리자)](/aspnet/core/security/app-secrets)                                                      | 사용자 프로필 디렉터리의 파일 |

다양한 구성 공급자에 관한 자세한 내용은 [.NET의 구성 공급자](configuration-providers.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

- [.NET의 구성 공급자](configuration-providers.md)
- [사용자 지정 구성 공급자 구현](custom-configuration-provider.md)
- 구성 버그는 [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) 리포지토리에서 만들어야 합니다.
