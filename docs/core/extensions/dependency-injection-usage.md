---
title: .NET에서 종속성 주입 사용
description: .NET 애플리케이션에서 종속성 주입을 사용하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 11/13/2020
ms.topic: tutorial
no-loc:
- Transient
- Scoped
- Singleton
- Example
ms.openlocfilehash: d6654d5d1c8f7959e96998c18a1790cce46ebf41
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102402158"
---
# <a name="tutorial-use-dependency-injection-in-net"></a>자습서: .NET에서 종속성 주입 사용

이 자습서에서는 [.NET에서 DI(종속성 주입)](dependency-injection.md)를 사용하는 방법을 보여 줍니다. ‘Microsoft 확장’에서 DI는 <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>에서 서비스가 추가 및 구성되는 주요 구성 요소입니다. <xref:Microsoft.Extensions.Hosting.IHost> 인터페이스는 등록된 모든 서비스의 컨테이너 역할을 하는 <xref:System.IServiceProvider> 인스턴스를 공개합니다.

이 자습서에서는 다음 작업 방법을 알아봅니다.

> [!div class="checklist"]
>
> - 종속성 주입을 사용하는 .NET 콘솔 앱 만들기
> - [제네릭 호스트](generic-host.md) 빌드 및 구성
> - 여러 인터페이스 및 해당 구현 작성
> - DI를 위해 서비스 수명 및 범위 지정 사용

## <a name="prerequisites"></a>사전 요구 사항

- [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet) 이상
- 새 .NET 애플리케이션 만들기 및 NuGet 패키지 설치에 관한 지식

## <a name="create-a-new-console-application"></a>새 콘솔 애플리케이션 만들기

[dotnet new](../tools/dotnet-new.md) 명령 또는 IDE 새 프로젝트 마법사를 사용하여 **ConsoleDI.Example** 라는 새 .NET 콘솔 애플리케이션을 만듭니다. [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) NuGet 패키지를 프로젝트에 추가합니다.

## <a name="add-interfaces"></a>인터페이스 추가

프로젝트 루트 디렉터리에 다음 인터페이스를 추가합니다.

*IOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/IOperation.cs":::

`IOperation` 인터페이스는 단일 `OperationId` 속성을 정의합니다.

*ITransientOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/ITransientOperation.cs":::

*IScopedOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/IScopedOperation.cs":::

*ISingletonOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/ISingletonOperation.cs":::

`IOperation`의 모든 하위 인터페이스는 의도한 서비스 수명에 이름을 지정합니다. 예: “Transient” 또는 “Singleton”.

## <a name="add-default-implementation"></a>기본 구현 추가

다양한 작업에 대해 다음 기본 구현을 추가합니다.

*DefaultOperation.cs*

:::code language="csharp" source="snippets/configuration/console-di/DefaultOperation.cs":::

`DefaultOperation`은 명명된 모든 마커 인터페이스를 구현하고 새 GUID(Globally Unique identifier)의 마지막 4개 문자로 `OperationId` 속성을 초기화합니다.

## <a name="add-service-that-requires-di"></a>DI가 필요한 서비스 추가

콘솔 앱에 서비스 역할을 하는 다음 작업 로거 개체를 추가합니다.

*OperationLogger.cs*

:::code language="csharp" source="snippets/configuration/console-di/OperationLogger.cs":::

`OperationLogger`는 앞에서 언급한 각 마커 인터페이스인 `ITransientOperation`, `IScopedOperation`, `ISingletonOperation`이 필요한 생성자를 정의합니다. 개체는 소비자가 지정된 `scope` 매개 변수를 사용하여 작업을 로그할 수 있는 단일 메서드를 공개합니다. 호출된 경우 `LogOperations` 메서드는 범위 문자열과 메시지를 사용하여 각 작업의 고유 식별자를 로그합니다.

## <a name="register-services-for-di"></a>DI를 위해 서비스 등록

다음 코드로 *Program.cs* 를 업데이트합니다.

:::code language="csharp" source="snippets/configuration/console-di/Program.cs" range="1-18,35-60" highlight="22-26":::

> 각 `services.Add{SERVICE_NAME}` 확장 메서드는 서비스를 추가하고 잠재적으로 구성합니다. 앱에서 이 규칙을 따르는 것이 좋습니다. 확장 메서드를 <xref:Microsoft.Extensions.DependencyInjection?displayProperty=fullName> 네임스페이스에 배치하여 서비스 등록 그룹을 캡슐화합니다. DI 확장 메서드에 대해 `Microsoft.Extensions.DependencyInjection` 네임스페이스 부분을 포함하면 다음도 가능합니다.
>
> - 더 이상의 `using` 블록을 추가하지 않고도 [IntelliSense](/visualstudio/ide/using-intellisense)에 표시할 수 있습니다.
> - 일반적으로 해당 확장 메서드가 호출되는 `Program` 또는 `Startup` 클래스의 과도한 `using` 문을 방지합니다.

앱은 다음을 수행합니다.

- [기본 바인더 설정](generic-host.md#default-builder-settings)을 사용하여 <xref:Microsoft.Extensions.Hosting.IHostBuilder> 인스턴스를 만듭니다.
- 서비스를 구성하고 해당 서비스 수명으로 서비스를 추가합니다.
- <xref:Microsoft.Extensions.Hosting.IHostBuilder.Build>를 호출하고 <xref:Microsoft.Extensions.Hosting.IHost> 인스턴스를 할당합니다.
- `ExemplifyScoping`를 호출하여 <xref:Microsoft.Extensions.Hosting.IHost.Services?displayProperty=nameWithType>를 전달합니다.

## <a name="conclusion"></a>결론

앱은 다음 예제와 같은 출력을 표시합니다.

```console
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ 80f4...Always different        ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ f3c0...Always different        ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ c878...Changes only with scope ]
Scope 1-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]

Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ITransientOperation [ f9af...Always different        ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 1 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
...
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ITransientOperation [ fa65...Always different        ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): IScopedOperation    [ 2bd0...Changes only with scope ]
Scope 2-Call 2 .GetRequiredService<OperationLogger>(): ISingletonOperation [ 1586...Always the same         ]
```

앱 출력에서 다음을 확인할 수 있습니다.

- Transient 작업은 항상 다르지만 서비스를 검색할 때마다 새 인스턴스가 만들어집니다.
- Scoped 작업은 새 범위에서 변경될 뿐 아니라 한 범위 내에서는 동일한 인스턴스입니다.
- Singleton 작업은 항상 동일하며 새 인스턴스는 한 번만 만들어집니다.

## <a name="see-also"></a>참고 항목

* [종속성 주입 지침](dependency-injection-guidelines.md)
* [ASP.NET Core에서 종속성 주입](/aspnet/core/fundamentals/dependency-injection)
