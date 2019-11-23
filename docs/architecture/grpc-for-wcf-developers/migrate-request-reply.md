---
title: Wcf 개발자를 위한 gRPC gRPC로 WCF 요청-회신 서비스 마이그레이션
description: WCF에서 gRPC로 간단한 요청-응답 서비스를 마이그레이션하는 방법에 대해 알아봅니다.
ms.date: 09/02/2019
ms.openlocfilehash: f0b20e7b374438f90d83aebc6035a4e4dd94ae18
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971780"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a>WCF 요청-회신 서비스를 gRPC 단항 RPC로 마이그레이션

이 섹션에서는 WCF의 기본 요청-회신 서비스를 ASP.NET Core gRPC의 단항 RPC 서비스로 마이그레이션하는 방법에 대해 설명 합니다. 이러한 서비스는 WCF (Windows Communication Foundation) 및 gRPC에서 가장 간단한 서비스 유형 이므로 시작 하는 것이 좋습니다. 서비스를 마이그레이션한 후에는 동일한 `.proto` 파일에서 클라이언트 라이브러리를 생성 하 여 .NET 클라이언트 응용 프로그램에서 서비스를 사용 하는 방법을 알아봅니다.

## <a name="the-wcf-solution"></a>WCF 솔루션

[PortfoliosSample 솔루션](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) 에는 단일 포트폴리오 또는 지정 된 상인의 모든 포트폴리오를 다운로드 하는 간단한 요청-회신 포트폴리오 서비스가 포함 되어 있습니다. 서비스는 `ServiceContract` 특성을 사용 하 여 `IPortfolioService` 인터페이스에 정의 됩니다.

```csharp
[ServiceContract]
public interface IPortfolioService
{
    [OperationContract]
    Task<Portfolio> Get(Guid traderId, int portfolioId);

    [OperationContract]
    Task<List<Portfolio>> GetAll(Guid traderId);
}
```

`Portfolio` 모델은 `PortfolioItem` 개체의 C# 목록을 포함 하 여 [DataContract](xref:System.Runtime.Serialization.DataContractAttribute)로 표시 되는 간단한 클래스입니다. 이러한 모델은 데이터 액세스 추상화를 나타내는 리포지토리 클래스와 함께 `TraderSys.PortfolioData` 프로젝트에서 정의 됩니다.

```csharp
[DataContract]
public class Portfolio
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public Guid TraderId { get; set; }

    [DataMember]
    public List<PortfolioItem> Items { get; set; }
}

[DataContract]
public class PortfolioItem
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public int ShareId { get; set; }

    [DataMember]
    public int Holding { get; set; }

    [DataMember]
    public decimal Cost { get; set; }
}
```

`ServiceContract` 구현에서는 `DataContract` 형식의 인스턴스를 반환 하는 종속성 주입을 통해 제공 되는 리포지토리 클래스를 사용 합니다.

```csharp
public class PortfolioService : IPortfolioService
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }

    public async Task<Portfolio> Get(Guid traderId, int portfolioId)
    {
        return await _repository.GetAsync(traderId, portfolioId);
    }

    public async Task<List<Portfolio>> GetAll(Guid traderId)
    {
        return await _repository.GetAllAsync(traderId);
    }
}
```

## <a name="the-portfoliosproto-file"></a>포트폴리오의 proto 파일

이전 섹션의 지침을 따른 경우 다음과 같은 `portfolios.proto` 파일을 포함 하는 gRPC 프로젝트가 있어야 합니다.

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

첫 번째 단계는 `DataContract` 클래스를 해당 Protobuf로 마이그레이션하는 것입니다.

## <a name="convert-the-datacontracts-to-grpc-messages"></a>DataContracts를 gRPC 메시지로 변환

`PortfolioItem` 클래스는 `Portfolio` 클래스가 종속 되므로 Protobuf 메시지로 먼저 변환 됩니다. 클래스는 매우 간단 하며 세 가지 속성은 gRPC 데이터 형식에 직접 매핑됩니다. 구매 시 공유에 대해 지불 된 가격을 나타내는 `Cost` 속성은 `decimal` 필드 이며, gRPC는 통화에 적합 하지 않은 실수에 대 한 `float` 또는 `double`만 지원 합니다. 공유 가격은 최소한 하나의 센트에 따라 달라 지므로 비용은 센트의 `int32`으로 표현할 수 있습니다.

> [!NOTE]
> `.proto` 파일에서 필드 이름에 `camelCase`를 사용 해야 합니다. 코드 C# 생성기는 `PascalCase`로 변환 하 고 다른 언어의 사용자는 다른 코딩 표준을 준수 하도록 감사 합니다.

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

`Portfolio` 클래스는 약간 더 복잡 합니다. WCF 코드에서 개발자는 `TraderId` 속성에 대해 `Guid`를 사용 하 고 `List<PortfolioItem>`를 포함 합니다. Protobuf에는 `UUID` 형식이 없는 경우 `traderId` 필드에 `string`를 사용 하 여 코드에서 구문 분석 해야 합니다. 항목 목록에 대해 필드의 `repeated` 키워드를 사용 합니다.

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

이제 데이터 메시지가 있으므로 서비스 RPC 끝점을 선언할 수 있습니다.

## <a name="convert-the-servicecontract-to-a-grpc-service"></a>ServiceContract를 gRPC 서비스로 변환

WCF `Get` 메서드는 `Guid traderId` 및 `int portfolioId`의 두 매개 변수를 사용 합니다. gRPC 서비스 메서드는 단일 매개 변수만 사용할 수 있으므로 두 값을 포함 하는 메시지를 만들어야 합니다. 일반적으로 메서드와 동일한 이름을 사용 하 여 이러한 요청 개체의 이름을 `Request`하는 것이 좋습니다. 다시 `string` `Guid`대신 `traderId` 필드에 사용 됩니다.

서비스는 `Portfolio` 메시지를 직접 반환 했지만 나중에 이전 버전과의 호환성에 영향을 줄 수 있습니다. 서비스의 모든 메서드에 대해 별도의 `Request` 및 `Response` 메시지를 정의 하는 것이 좋지만, 대부분의 경우에는 `GetResponse` 메시지를 단일 `Portfolio` 필드로 선언 합니다.

다음 예제에서는 `GetRequest` 메시지를 사용 하 여 gRPC 서비스 메서드를 선언 하는 방법을 보여 줍니다.

```protobuf
message GetRequest {
    string trader_id = 1;
    int32 portfolio_id = 2;
}

message GetResponse {
    Portfolio portfolio = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (GetResponse);
}
```

WCF `GetAll` 메서드는 `traderId`단일 매개 변수만 사용 하므로 매개 변수 형식으로 `string`를 지정 하는 것 처럼 보일 수 있지만 gRPC에는 정의 된 메시지 유형이 필요 합니다. 이 요구 사항은 이후의 이전 버전과의 호환성을 위해 모든 입력 및 출력에 대해 사용자 지정 메시지를 사용 하는 방법을 강제 적용 하는 데 도움이 됩니다.

WCF 메서드는 `List<Portfolio>`도 반환 했지만 단순한 매개 변수 형식을 허용 하지 않는 등의 이유로 gRPC는 `repeated Portfolio` 반환 형식으로 허용 되지 않습니다. 대신 `GetAllResponse` 형식을 만들어 목록을 래핑합니다.

> [!WARNING]
> `PortfolioList` 메시지를 생성 하 고 여러 서비스 메서드에서 사용 하는 것이 좋습니다. 그러나이 하려는 유혹는 그렇지 않습니다. 서비스의 다양 한 메서드가 향후에 진화 하는 방식을 알 수 없기 때문에 메시지를 특정 하 고 완전히 분리 된 상태로 유지 하는 것은 불가능 합니다.

```protobuf
message GetAllRequest {
    string trader_id = 1;
}

message PortfolioList {
    repeated Portfolio portfolios = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (Portfolio);
    rpc GetAll(GetAllRequest) returns (GetAllResponse);
}
```

이러한 변경 내용을 적용 하 여 프로젝트를 저장 하면 gRPC 빌드 대상이 백그라운드에서 실행 되 고 모든 Protobuf 메시지 유형과 상속 하 여 서비스를 구현 하는 기본 클래스가 생성 됩니다.

`Services/GreeterService.cs` 클래스를 열고 예제 코드를 삭제 합니다. 이제 포트폴리오 서비스 구현을 추가할 수 있습니다. 생성 된 기본 클래스는 `Protos` 네임 스페이스에 있고 중첩 클래스로 생성 됩니다. gRPC는 `.proto` 파일에 서비스와 동일한 이름을 사용 하는 정적 클래스를 만든 다음, 해당 정적 클래스 내부에 `Base` 접미사가 있는 기본 클래스를 만듭니다. 따라서 기본 형식의 전체 식별자는 `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`됩니다.

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

기본 클래스는 서비스를 구현 하기 위해 재정의할 수 있는 `Get` 및 `GetAll`에 대 한 `virtual` 메서드를 선언 합니다. 메서드는 `abstract`가 아닌 `virtual` 되므로, 구현 하지 않는 경우 서비스는 일반 C# 코드에서 `NotImplementedException`를 throw 할 수 있는 것 처럼 명시적 grpc `Unimplemented` 상태 코드를 반환할 수 있습니다.

ASP.NET Core의 모든 gRPC 단항 서비스 메서드에 대 한 서명이 일치 합니다. 두 매개 변수가 있습니다. 첫 번째 매개 변수는 `.proto` 파일에 선언 된 메시지 유형이 고, 두 번째 매개 변수는 ASP.NET Core의 `HttpContext`와 유사 하 게 작동 하는 `ServerCallContext`입니다. 실제로는 기본 `HttpContext`를 가져오는 데 사용할 수 있는 `ServerCallContext` 클래스에 `GetHttpContext` 라는 확장 메서드가 있는데, 자주 사용 하지 않아도 됩니다. 이 챕터의 뒷부분에 나오는 `ServerCallContext`와 인증에 대해 설명 하는 장에서 살펴보겠습니다.

메서드의 반환 형식은 `T` 응답 메시지 형식인 `Task<T>`입니다. 모든 gRPC 서비스 메서드는 비동기입니다.

## <a name="migrate-the-portfoliodata-library-to-net-core"></a>PortfolioData 라이브러리를 .NET Core로 마이그레이션

이 시점에서 프로젝트에는 WCF 솔루션의 `TraderSys.PortfolioData` 클래스 라이브러리에 포함 된 포트폴리오 리포지토리 및 모델이 필요 합니다. 이러한 항목을 가져오는 가장 쉬운 방법은 Visual Studio **새 프로젝트** 대화 상자를 사용 하 여 *클래스 라이브러리 (.NET Standard)* 템플릿을 사용 하 여 새 클래스 라이브러리를 만들거나 .NET Core CLI를 사용 하 여 명령줄에서 `TraderSys.sln` 파일을 포함 하는 디렉터리에서 다음 명령을 실행 하는 것입니다.

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

라이브러리가 만들어지고 솔루션에 추가 되 면 생성 된 `Class1.cs` 파일을 삭제 하 고 WCF 솔루션 라이브러리의 파일을 새 클래스 라이브러리의 폴더에 복사 하 여 폴더 구조를 유지 합니다.

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

SDK 스타일 .NET 프로젝트에는 자체 디렉터리의 `.cs` 파일이 자동으로 포함 되므로 프로젝트에 명시적으로 추가할 필요가 없습니다. 남은 단계는 `DataContract`를 제거 하 고 `Portfolio` 및 `PortfolioItem` 클래스에서 특성을 `DataMember` 하는 것입니다. 따라서 일반 C# 클래스입니다.

```csharp
public class Portfolio
{
    public int Id { get; set; }
    public Guid TraderId { get; set; }
    public List<PortfolioItem> Items { get; set; }
}

public class PortfolioItem
{
    public int Id { get; set; }
    public int ShareId { get; set; }
    public int Holding { get; set; }
    public decimal Cost { get; set; }
}
```

## <a name="use-aspnet-core-dependency-injection"></a>ASP.NET Core 종속성 주입 사용

이제이 라이브러리에 대 한 참조를 gRPC 응용 프로그램 프로젝트에 추가 하 고 gRPC 서비스 구현에서 종속성 주입을 사용 하 여 `PortfolioRepository` 클래스를 사용할 수 있습니다. WCF 응용 프로그램에서는 Autofac IoC 컨테이너에서 종속성 주입을 제공 했습니다. ASP.NET Core에 종속성 주입 구운 있습니다. `Startup` 클래스의 `ConfigureServices` 메서드에 리포지토리를 등록할 수 있습니다.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Register the repository class as a scoped service (instance per request)
        services.AddScoped<IPortfolioRepository, PortfolioRepository>();

        services.AddGrpc();
    }

    // ...
}
```

이제 다음과 같이 `IPortfolioRepository` 구현을 `PortfolioService` 클래스에서 생성자 매개 변수로 지정할 수 있습니다.

```csharp
public class PortfolioService : Protos.Portfolios.PortfoliosBase
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }
}
```

## <a name="implement-the-grpc-service"></a>GRPC 서비스 구현

이제 `portfolios.proto` 파일에서 메시지와 서비스를 선언 했으므로 gRPC 생성 `Portfolios.PortfoliosBase` 클래스에서 상속 되는 `PortfolioService` 클래스에서 서비스 메서드를 구현 해야 합니다. 메서드는 기본 클래스에서 `virtual`로 선언 됩니다. 이를 재정의 하지 않으면 기본적으로 gRPC "구현 되지 않음" 상태 코드가 반환 됩니다.

`Get` 메서드를 구현 하 여 시작 합니다. 기본 재정의는 다음 예제와 같습니다.

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

첫 번째 문제는 `request.TraderId`가 문자열이 고 서비스에 `Guid`가 필요한 것입니다. 문자열에 대해 예상 되는 형식이 `UUID`경우에도 코드는 호출자가 잘못 된 값을 보내고 적절 하 게 응답할 가능성을 처리 해야 합니다. 서비스는 `RpcException`를 throw 하 여 오류에 응답할 수 있으며, 표준 `InvalidArgument` 상태 코드를 사용 하 여 문제를 표현 합니다.

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    return base.Get(request, context);
}
```

`traderId`에 대 한 적절 한 `Guid` 값이 있으면 리포지토리를 사용 하 여 포트폴리오를 검색 하 고 클라이언트에 반환할 수 있습니다.

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a>내부 모델을 gRPC 메시지에 매핑

리포지토리가 자체 POCO 모델 `Portfolio`를 반환 하지만 gRPC에는 자체 Protobuf message *`Portfolio`필요 하므로* 이전 코드는 실제로 작동 하지 않습니다. Entity Framework 형식을 데이터 전송 형식에 매핑하는 것과 매우 유사 하 게 가장 좋은 방법은 둘 간의 변환을 제공 하는 것입니다. 이에 대 한 코드를 저장 하는 좋은 위치는 Protobuf에서 생성 된 클래스에 있습니다 .이 클래스는 확장 될 수 있도록 `partial` 클래스로 선언 됩니다.

```csharp
namespace TraderSys.Portfolios.Protos
{
    public partial class PortfolioItem
    {
        public static PortfolioItem FromRepositoryModel(PortfolioData.Models.PortfolioItem source)
        {
            if (source is null) return null;

            return new PortfolioItem
            {
                Id = source.Id,
                ShareId = source.ShareId,
                Holding = source.Holding,
                CostCents = (int)(source.Cost * 100)
            };
        }
    }

    public partial class Portfolio
    {
        public static Portfolio FromRepositoryModel(PortfolioData.Models.Portfolio source)
        {
            if (source is null) return null;

            var target = new Portfolio
            {
                Id = source.Id,
                TraderId = source.TraderId.ToString(),
            };

            target.Items.AddRange(source.Items.Select(PortfolioItem.FromRepositoryModel));

            return target;
        }
    }
}
```

> [!NOTE]
> `string`/`Guid` 또는 `decimal`/`double` 및 목록 매핑과 같은 하위 수준 형식 변환을 구성 하는 경우 [Automapper](https://automapper.org/) 와 같은 라이브러리를 사용 하 여 내부 모델 클래스에서 Protobuf 형식으로의 변환을 처리할 수 있습니다.

변환 코드가 준비 되 면 `Get` 메서드 구현을 완료할 수 있습니다.

```csharp
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}

```

`GetAll` 메서드의 구현은 유사 합니다. Protobuf 메시지의 `repeated` 필드는 `RepeatedField<T>`형식의 `readonly` 속성으로 생성 되므로 다음 예제와 같이 `AddRange` 메서드를 사용 하 여 항목을 추가 해야 합니다.

```csharp
public override async Task<GetAllResponse> GetAll(GetAllRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolios = await _repository.GetAllAsync(traderId);

    var response = new GetAllResponse();
    response.Portfolios.AddRange(portfolios.Select(Portfolio.FromRepositoryModel));

    return response;
}
```

WCF 요청-응답 서비스를 gRPC로 마이그레이션 했으면 `.proto` 파일에서 해당 클라이언트에 대 한 클라이언트를 만드는 방법을 살펴보겠습니다.

## <a name="generate-client-code"></a>클라이언트 코드 생성

동일한 솔루션에서 클라이언트를 포함 하는 .NET Standard 클래스 라이브러리를 만듭니다. 이는 주로 클라이언트 코드를 만드는 예제 이지만 NuGet을 사용 하 여 이러한 라이브러리를 패키지 하 고 다른 .NET 팀이 사용할 수 있도록 내부 리포지토리에 배포할 수 있습니다. 계속 해 서 `TraderSys.Portfolios.Client` 라는 새 .NET Standard 클래스 라이브러리를 솔루션에 추가 하 고 `Class1.cs` 파일을 삭제 합니다.

> [!CAUTION]
> [Grpc .Net 클라이언트](https://www.nuget.org/packages/Grpc.Net.Client) NuGet 패키지에는 .net Core 3.0 (또는 다른 .NET Standard 2.1 규격 런타임)가 필요 합니다. 이전 버전의 .NET Framework 및 .NET Core는 [Grpc. 핵심](https://www.nuget.org/packages/Grpc.Core) NuGet 패키지에서 지원 됩니다.

Visual Studio 2019에서는 이전 버전의 Visual Studio에서 WCF 프로젝트에 서비스 참조를 추가 하는 방법과 유사 하 게 gRPC 서비스에 대 한 참조를 추가할 수 있습니다. 서비스 참조 및 연결된 서비스는 모두 동일한 UI에서 관리 되며, 솔루션 탐색기에서 `TraderSys.Portfolios.Client` 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭 하 고 **연결 된 서비스 추가**를 선택 하 여 액세스할 수 있습니다. 표시 되는 도구 창에서 **서비스 참조** 섹션을 선택 하 고 **새 Grpc 서비스 참조 추가**를 클릭 합니다.

![Visual Studio 2019의 연결된 서비스 UI](media/migrate-request-reply/add-connected-service.png)

`TraderSys.Portfolios` 프로젝트에서 `portfolios.proto` 파일을 찾아 **클래스의 유형을 클라이언트로 생성 하** 고 **확인**을 클릭 합니다.

![Visual Studio 2019의 새 gRPC 서비스 참조 추가 대화 상자](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> 이 대화 상자는 URL 필드를 제공 합니다. 조직에서 `.proto` 파일의 웹 액세스 가능 디렉터리를 유지 관리 하는 경우이 URL 주소를 설정 하 여 클라이언트를 만들 수 있습니다.

Visual Studio **연결 된 서비스 추가** 기능을 사용 하는 경우 `portfolios.proto` 파일은 복사 되지 않고 클래스 라이브러리 프로젝트에 *연결 된 파일로*추가 되므로 서비스 프로젝트의 파일에 대 한 변경 내용이 클라이언트 프로젝트에 자동으로 적용 됩니다. `csproj` 파일의 `<Protobuf>` 요소는 다음과 같습니다.

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> Visual Studio를 사용 하지 않거나 명령줄에서 작업 하는 것을 선호 하는 경우 **dotnet pc** 전역 도구를 사용 하 여 .Net grpc 프로젝트 내에서 Protobuf 참조를 관리할 수 있습니다. [자세한 내용은 **dotnet grpc** 설명서를 참조](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc)하세요.

### <a name="use-the-portfolios-service-from-a-client-application"></a>클라이언트 응용 프로그램에서 포트폴리오 서비스 사용

다음 코드는 콘솔 응용 프로그램에서 생성 된 클라이언트를 사용 하는 간단한 예입니다. GRPC 클라이언트 코드에 대 한 자세한 탐색은이 챕터의 끝에 있습니다.

```csharp
public class Program
{
    public async Task Main(string[] args)
    {
        GetResponse response;

        using (var channel = GrpcChannel.ForAddress("https://localhost:5001"))
        {
            var client = new Protos.Portfolios.PortfoliosClient(channel);

            response = await client.GetAsync(new GetRequest
            {
                TraderId = args[0],
                PortfolioId = int.Parse(args[1])
            });
        }

        foreach (var item in response.Portfolio.Items)
        {
            Console.WriteLine($"Holding {item.Holding} of Share ID {item.ShareId}.");
        }
    }
}
```

이제 기본 WCF 응용 프로그램을 ASP.NET Core gRPC 서비스로 마이그레이션하고 .NET 응용 프로그램에서 서비스를 사용 하는 클라이언트를 만들었습니다. 다음 섹션에서는 관련 된 "이중" 서비스에 대해 다룹니다.

>[!div class="step-by-step"]
>[이전](create-project.md)
>[다음](migrate-duplex-services.md)
