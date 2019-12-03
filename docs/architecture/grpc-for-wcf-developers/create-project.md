---
title: WCF 개발자를 위한 새 ASP.NET Core gRPC 프로젝트 gRPC 만들기
description: Visual Studio 또는 명령줄을 사용 하 여 gRPC 프로젝트를 만드는 방법에 대해 알아봅니다.
ms.date: 09/02/2019
ms.openlocfilehash: ea6d7658404f61fedb25d7de7ddedb7c51437383
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711442"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a>새 ASP.NET Core gRPC 프로젝트 만들기

.NET Core SDK는 명령줄에서 프로젝트와 솔루션을 만들고 관리할 수 있는 강력한 CLI 도구인 `dotnet`와 함께 제공 됩니다. SDK는 Visual Studio와 긴밀 하 게 통합 되므로 친숙 한 그래픽 사용자 인터페이스를 통해서도 모든 기능을 사용할 수 있습니다. 이 장에서는 새 ASP.NET Core gRPC 프로젝트를 만드는 두 가지 방법을 모두 보여 줍니다.

## <a name="create-the-project-by-using-visual-studio"></a>Visual Studio를 사용 하 여 프로젝트 만들기

> [!IMPORTANT]
> ASP.NET Core 3.0 앱을 개발 하려면 **ASP.NET 및 웹 개발** 워크 로드가 설치 된 Visual Studio 2019 16.3 이상이 필요 합니다.

*빈 솔루션* 템플릿에서 **TraderSys** 라는 빈 솔루션을 만듭니다. `src`이라는 솔루션 폴더를 추가 합니다. 그런 다음 폴더를 마우스 오른쪽 단추로 클릭 하 고 **추가** > **새 프로젝트**를 선택 합니다. 템플릿 검색 상자에 `grpc`를 입력 하면 `gRPC Service`라는 프로젝트 템플릿이 표시 됩니다.

![새 프로젝트 추가 대화 상자 스크린샷](media/create-project/new-grpc-project.png)

**다음** 을 선택 하 여 **새 프로젝트 구성** 대화 상자를 계속 진행 합니다. 프로젝트 이름을 `TraderSys.Portfolios`로 `src` 하 고 **위치**에 하위 디렉터리를 추가 합니다.

![새 프로젝트 구성 대화 상자 스크린샷](media/create-project/configure-project.png)

**다음** 을 선택 하 여 **새 grpc 서비스 만들기** 대화 상자를 계속 진행 합니다.

![새 gRPC 서비스 만들기 대화 상자 스크린샷](media/create-project/create-new-grpc-service.png)

현재는 서비스 만들기에 대 한 옵션이 제한적입니다. Docker는 나중에 도입 되므로 지금은이 옵션을 선택 하지 않은 상태로 둡니다. **만들기**를 선택 합니다. 첫 번째 ASP.NET Core 3.0 gRPC 프로젝트가 생성 되어 솔루션에 추가 됩니다. `dotnet CLI`를 사용 하는 방법을 모르는 경우 [예제 코드 섹션 정리](#clean-up-the-example-code) 로 건너뜁니다.

## <a name="create-the-project-by-using-the-net-core-cli"></a>.NET Core CLI를 사용 하 여 프로젝트를 만듭니다.

이 섹션에서는 명령줄에서 솔루션 및 프로젝트를 만드는 방법을 설명 합니다.

다음 명령에 표시 된 대로 솔루션을 만듭니다. `-o` (또는 `--output`) 플래그는 현재 디렉터리에 생성 되는 출력 디렉터리를 지정 합니다 (이미 존재 하지 않는 경우). 솔루션의 이름은 `TraderSys.sln`디렉터리와 동일 합니다. `-n` (또는 `--name`) 플래그를 사용 하 여 다른 이름을 제공할 수 있습니다.

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

ASP.NET Core 3.0는 gRPC 서비스용 CLI 템플릿과 함께 제공 됩니다. 이 템플릿을 사용 하 여 새 프로젝트를 만듭니다 .이 템플릿을 사용 하 여 ASP.NET Core 프로젝트에 대 한 기본으로 `src` 하위 디렉터리에 배치 합니다. `-n` 플래그를 사용 하 여 다른 이름을 지정 하지 않은 경우 프로젝트 이름은 디렉터리 (`TraderSys.Portfolios.csproj`) 뒤에 지정 됩니다.

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

마지막으로 `dotnet sln` 명령을 사용 하 여 솔루션에 프로젝트를 추가 합니다.

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> 특정 디렉터리에는 단일 `.csproj` 파일만 포함 되어 있으므로, 디렉터리만 지정 하 여 입력을 저장할 수 있습니다.

이제 Visual Studio 2019, Visual Studio Code 또는 원하는 편집기에서이 솔루션을 열 수 있습니다.

## <a name="clean-up-the-example-code"></a>예제 코드 정리

이제 이전 책에서 검토 한 gRPC 템플릿을 사용 하 여 예제 서비스를 만들었습니다. 이는 재고 거래 컨텍스트에서 유용 하지 않으므로 첫 번째 프로젝트에 대 한 항목을 편집 합니다.

### <a name="rename-and-edit-the-proto-file"></a>프로토콜 파일 이름 바꾸기 및 편집

계속 해 서 `Protos/greet.proto` 파일의 이름을 `Protos/portfolios.proto`로 바꾸고 편집기에서 엽니다. `package` 줄 뒤에 나오는 모든 항목을 삭제 합니다. 그런 다음 `option csharp_namespace`, `package` 및 `service` 이름을 변경 하 고 기본 `SayHello` 서비스를 제거 합니다. 이제 코드는 다음과 같습니다.

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> 템플릿은 기본적으로 `Protos` 네임 스페이스 파트를 추가 하지 않지만,이를 추가 하면 gRPC에서 생성 된 클래스와 사용자 고유의 클래스를 코드에서 명확 하 게 구분 하 여 쉽게 유지할 수 있습니다.

Visual Studio와 같은 IDE (통합 개발 환경)에서 `greet.proto` 파일의 이름을 바꾸면이 파일에 대 한 참조가 `.csproj` 파일에서 자동으로 업데이트 됩니다. 그러나 Visual Studio Code와 같은 다른 편집기에서이 참조는 자동으로 업데이트 되지 않으므로 프로젝트 파일을 수동으로 편집 해야 합니다.

GRPC 빌드 대상에는 컴파일할 `.proto` 파일 및 필요한 코드 생성 형태 ("Server" 또는 "Client")를 지정할 수 있는 `Protobuf` item 요소가 있습니다.

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a>`GreeterService` 클래스 이름 바꾸기

`GreeterService` 클래스는 `Services` 폴더에 있으며 `Greeter.GreeterBase`에서 상속 됩니다. `PortfolioService`로 이름을 바꾸고 기본 클래스를 `Portfolios.PortfoliosBase`변경 합니다. `override` 메서드를 삭제 합니다.

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

`Startup` 클래스의 `Configure` 메서드에 `GreeterService` 클래스에 대 한 참조가 있습니다. 리팩터링을 사용 하 여 클래스의 이름을 바꾼 경우이 참조는 자동으로 업데이트 되어야 합니다. 그러나 그렇지 않은 경우 수동으로 편집 해야 합니다.

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

다음 섹션에서는이 새 서비스에 기능을 추가 합니다.

>[!div class="step-by-step"]
>[이전](migrate-wcf-to-grpc.md)
>[다음](migrate-request-reply.md)
