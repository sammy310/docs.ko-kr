---
title: Wcf 개발자를 위한 gRPC gRPC로 WCF 요청-회신 서비스 마이그레이션
description: WCF에서 gRPC로 간단한 요청-응답 서비스를 마이그레이션하는 방법에 대해 알아봅니다.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 12e042e8e7e3683cc4da1fedce2482e7199b04a7
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841506"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a><span data-ttu-id="b16bd-103">WCF 요청-회신 서비스를 gRPC 단항 RPC로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="b16bd-103">Migrate a WCF request-reply service to a gRPC unary RPC</span></span>

<span data-ttu-id="b16bd-104">이 섹션에서는 WCF의 기본 요청-회신 서비스를 ASP.NET Core gRPC의 단항 RPC 서비스로 마이그레이션하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-104">This section covers how to migrate a basic request-reply service in WCF to a unary RPC service in ASP.NET Core gRPC.</span></span> <span data-ttu-id="b16bd-105">이러한 서비스는 WCF (Windows Communication Foundation) 및 gRPC에서 가장 간단한 서비스 유형 이므로 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-105">These services are the simplest service types in both Windows Communication Foundation (WCF) and gRPC, so it's an excellent place to start.</span></span> <span data-ttu-id="b16bd-106">서비스를 마이그레이션한 후에는 동일한 `.proto` 파일에서 클라이언트 라이브러리를 생성 하 여 .NET 클라이언트 응용 프로그램에서 서비스를 사용 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-106">After migrating the service, you'll learn how to generate a client library from the same `.proto` file to consume the service from a .NET client application.</span></span>

## <a name="the-wcf-solution"></a><span data-ttu-id="b16bd-107">WCF 솔루션</span><span class="sxs-lookup"><span data-stu-id="b16bd-107">The WCF solution</span></span>

<span data-ttu-id="b16bd-108">[PortfoliosSample 솔루션](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) 에는 단일 포트폴리오 또는 지정 된 상인의 모든 포트폴리오를 다운로드 하는 간단한 요청-회신 포트폴리오 서비스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-108">The [PortfoliosSample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) includes a simple Request-Reply Portfolio service to download a single portfolio, or all portfolios for a given Trader.</span></span> <span data-ttu-id="b16bd-109">서비스는 `ServiceContract` 특성을 사용 하 여 `IPortfolioService` 인터페이스에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-109">The service is defined in the interface `IPortfolioService` with a `ServiceContract` attribute:</span></span>

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

<span data-ttu-id="b16bd-110">`Portfolio` 모델은 `PortfolioItem` 개체의 C# 목록을 포함 하 여 [DataContract](xref:System.Runtime.Serialization.DataContractAttribute)로 표시 되는 간단한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-110">The `Portfolio` model is a simple C# class marked with [DataContract](xref:System.Runtime.Serialization.DataContractAttribute), including a list of `PortfolioItem` objects.</span></span> <span data-ttu-id="b16bd-111">이러한 모델은 데이터 액세스 추상화를 나타내는 리포지토리 클래스와 함께 `TraderSys.PortfolioData` 프로젝트에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-111">These models are defined in the `TraderSys.PortfolioData` project, along with a repository class representing a data access abstraction.</span></span>

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

<span data-ttu-id="b16bd-112">`ServiceContract` 구현에서는 `DataContract` 형식의 인스턴스를 반환 하는 종속성 주입을 통해 제공 되는 리포지토리 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-112">The `ServiceContract` implementation uses a repository class provided via dependency injection that returns instances of the `DataContract` types.</span></span>

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

## <a name="the-portfoliosproto-file"></a><span data-ttu-id="b16bd-113">포트폴리오의 proto 파일</span><span class="sxs-lookup"><span data-stu-id="b16bd-113">The portfolios.proto file</span></span>

<span data-ttu-id="b16bd-114">이전 섹션의 지침을 따른 경우 다음과 같은 `portfolios.proto` 파일을 포함 하는 gRPC 프로젝트가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-114">If you followed the instructions in the previous section, you should have a gRPC project with a `portfolios.proto` file that looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

<span data-ttu-id="b16bd-115">첫 번째 단계는 `DataContract` 클래스를 해당 Protobuf로 마이그레이션하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-115">The first step is to migrate the `DataContract` classes to their Protobuf equivalents.</span></span>

## <a name="convert-the-datacontracts-to-grpc-messages"></a><span data-ttu-id="b16bd-116">DataContracts를 gRPC 메시지로 변환</span><span class="sxs-lookup"><span data-stu-id="b16bd-116">Convert the DataContracts to gRPC messages</span></span>

<span data-ttu-id="b16bd-117">`PortfolioItem` 클래스는 `Portfolio` 클래스가 종속 되므로 Protobuf 메시지로 먼저 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-117">The `PortfolioItem` class will be converted to a Protobuf message first, as the `Portfolio` class depends on it.</span></span> <span data-ttu-id="b16bd-118">클래스는 매우 간단 하며 세 가지 속성은 gRPC 데이터 형식에 직접 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-118">The class is very simple, and three of the properties map directly to gRPC data types.</span></span> <span data-ttu-id="b16bd-119">구매 시 공유에 대해 지불 된 가격을 나타내는 `Cost` 속성은 `decimal` 필드 이며, gRPC는 통화에 적합 하지 않은 실수에 대 한 `float` 또는 `double`만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-119">The `Cost` property, representing the price paid for the shares at purchase, is a `decimal` field, and gRPC only supports `float` or `double` for real numbers, which aren't suitable for currency.</span></span> <span data-ttu-id="b16bd-120">공유 가격은 최소한 하나의 센트에 따라 달라 지므로 비용은 센트의 `int32`으로 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-120">Since share prices vary by a minimum of one cent, the cost can be expressed as an `int32` of cents.</span></span>

> [!NOTE]
> <span data-ttu-id="b16bd-121">`.proto` 파일에서 필드 이름에 `camelCase`를 사용 해야 합니다. 코드 C# 생성기는 `PascalCase`로 변환 하 고 다른 언어의 사용자는 다른 코딩 표준을 준수 하도록 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-121">Remember to use `camelCase` for field names in your `.proto` file; the C# code generator will convert them to `PascalCase` for you, and users of other languages will thank you for respecting their different coding standards.</span></span>

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

<span data-ttu-id="b16bd-122">`Portfolio` 클래스는 약간 더 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-122">The `Portfolio` class is a little more complicated.</span></span> <span data-ttu-id="b16bd-123">WCF 코드에서 개발자는 `TraderId` 속성에 대해 `Guid`를 사용 하 고 `List<PortfolioItem>`를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-123">In the WCF code, the developer used a `Guid` for the `TraderId` property, and contains a `List<PortfolioItem>`.</span></span> <span data-ttu-id="b16bd-124">Protobuf에는 `UUID` 형식이 없는 경우 `traderId` 필드에 `string`를 사용 하 여 코드에서 구문 분석 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-124">In Protobuf, which doesn't have a first-class `UUID` type, you should use a `string` for the `traderId` field and parse it in your own code.</span></span> <span data-ttu-id="b16bd-125">항목 목록에 대해 필드의 `repeated` 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-125">For the list of items, use the `repeated` keyword on the field.</span></span>

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

<span data-ttu-id="b16bd-126">이제 데이터 메시지가 있으므로 서비스 RPC 끝점을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-126">Now we have our data messages, we can declare the service RPC endpoints.</span></span>

## <a name="convert-the-servicecontract-to-a-grpc-service"></a><span data-ttu-id="b16bd-127">ServiceContract를 gRPC 서비스로 변환</span><span class="sxs-lookup"><span data-stu-id="b16bd-127">Convert the ServiceContract to a gRPC service</span></span>

<span data-ttu-id="b16bd-128">WCF `Get` 메서드는 `Guid traderId` 및 `int portfolioId`의 두 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-128">The WCF `Get` method takes two parameters: `Guid traderId` and `int portfolioId`.</span></span> <span data-ttu-id="b16bd-129">gRPC 서비스 메서드는 단일 매개 변수만 사용할 수 있으므로 두 값을 포함 하는 메시지를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-129">gRPC service methods can only take a single parameter, so a message must be created to hold the two values.</span></span> <span data-ttu-id="b16bd-130">일반적으로 메서드와 동일한 이름을 사용 하 여 이러한 요청 개체의 이름을 `Request`하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-130">It's common practice to name these request objects with the same name as the method and the suffix `Request`.</span></span> <span data-ttu-id="b16bd-131">다시 `string` `Guid`대신 `traderId` 필드에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-131">Again, `string` is being used for the `traderId` field instead of `Guid`.</span></span>

<span data-ttu-id="b16bd-132">서비스는 `Portfolio` 메시지를 직접 반환 했지만 나중에 이전 버전과의 호환성에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-132">The service could just return a `Portfolio` message directly, but again, this could impact backward compatibility in the future.</span></span> <span data-ttu-id="b16bd-133">서비스의 모든 메서드에 대해 별도의 `Request` 및 `Response` 메시지를 정의 하는 것이 좋지만, 대부분의 경우에는 `GetResponse` 메시지를 단일 `Portfolio` 필드로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-133">It's a good practice to define separate `Request` and `Response` messages for every method in a service, even if many of them are the same right now, so declare a `GetResponse` message with a single `Portfolio` field.</span></span>

<span data-ttu-id="b16bd-134">다음 예제에서는 `GetRequest` 메시지를 사용 하 여 gRPC 서비스 메서드를 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-134">The following example shows the declaration of the gRPC service method using the `GetRequest` message:</span></span>

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

<span data-ttu-id="b16bd-135">WCF `GetAll` 메서드는 `traderId`단일 매개 변수만 사용 하므로 매개 변수 형식으로 `string`를 지정 하는 것 처럼 보일 수 있지만 gRPC에는 정의 된 메시지 유형이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-135">The WCF `GetAll` method only takes a single parameter, `traderId`, so it might seem that one could specify `string` as the parameter type, but gRPC requires a defined message type.</span></span> <span data-ttu-id="b16bd-136">이 요구 사항은 이후의 이전 버전과의 호환성을 위해 모든 입력 및 출력에 대해 사용자 지정 메시지를 사용 하는 방법을 강제 적용 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-136">This requirement helps to enforce the practice of using custom messages for all inputs and outputs, for future backward compatibility.</span></span>

<span data-ttu-id="b16bd-137">WCF 메서드는 `List<Portfolio>`도 반환 했지만 단순한 매개 변수 형식을 허용 하지 않는 등의 이유로 gRPC는 `repeated Portfolio` 반환 형식으로 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-137">The WCF method also returned a `List<Portfolio>`, but for the same reason it doesn't allow simple parameter types, gRPC won't allow `repeated Portfolio` as a return type.</span></span> <span data-ttu-id="b16bd-138">대신 `GetAllResponse` 형식을 만들어 목록을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-138">Instead, create a `GetAllResponse` type to wrap the list.</span></span>

> [!WARNING]
> <span data-ttu-id="b16bd-139">`PortfolioList` 메시지를 생성 하 고 여러 서비스 메서드에서 사용 하는 것이 좋습니다. 그러나이 하려는 유혹는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-139">You may be tempted to create a `PortfolioList` message or similar and use it across multiple service methods, but you should resist this temptation.</span></span> <span data-ttu-id="b16bd-140">서비스의 다양 한 메서드가 향후에 진화 하는 방식을 알 수 없기 때문에 메시지를 특정 하 고 완전히 분리 된 상태로 유지 하는 것은 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-140">It's impossible to know how the various methods on a service may evolve in the future, so keep their messages specific and cleanly separated.</span></span>

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

<span data-ttu-id="b16bd-141">이러한 변경 내용을 적용 하 여 프로젝트를 저장 하면 gRPC 빌드 대상이 백그라운드에서 실행 되 고 모든 Protobuf 메시지 유형과 상속 하 여 서비스를 구현 하는 기본 클래스가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-141">If you save your project with these changes, the gRPC build target will run in the background and generate all the Protobuf message types and a base class you can inherit to implement the service.</span></span>

<span data-ttu-id="b16bd-142">`Services/GreeterService.cs` 클래스를 열고 예제 코드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-142">Open up the `Services/GreeterService.cs` class and delete the example code.</span></span> <span data-ttu-id="b16bd-143">이제 포트폴리오 서비스 구현을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-143">Now you can add the Portfolio service implementation.</span></span> <span data-ttu-id="b16bd-144">생성 된 기본 클래스는 `Protos` 네임 스페이스에 있고 중첩 클래스로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-144">The generated base class will be in the `Protos` namespace and is generated as a nested class.</span></span> <span data-ttu-id="b16bd-145">gRPC는 `.proto` 파일에 서비스와 동일한 이름을 사용 하는 정적 클래스를 만든 다음, 해당 정적 클래스 내부에 `Base` 접미사가 있는 기본 클래스를 만듭니다. 따라서 기본 형식의 전체 식별자는 `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-145">gRPC creates a static class with the same name as the service in the `.proto` file, and then a base class with the suffix `Base` inside that static class, so the full identifier for the base type is `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span></span>

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

<span data-ttu-id="b16bd-146">기본 클래스는 서비스를 구현 하기 위해 재정의할 수 있는 `Get` 및 `GetAll`에 대 한 `virtual` 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-146">The base class declares `virtual` methods for `Get` and `GetAll` that can be overridden to implement the service.</span></span> <span data-ttu-id="b16bd-147">메서드는 `abstract`가 아닌 `virtual` 되므로, 구현 하지 않는 경우 서비스는 일반 C# 코드에서 `NotImplementedException`를 throw 할 수 있는 것 처럼 명시적 grpc `Unimplemented` 상태 코드를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-147">The methods are `virtual` rather than `abstract` so that if you don't implement them, the service can return an explicit gRPC `Unimplemented` status code, much like you might throw a `NotImplementedException` in regular C# code.</span></span>

<span data-ttu-id="b16bd-148">ASP.NET Core의 모든 gRPC 단항 서비스 메서드에 대 한 서명이 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-148">The signature for all gRPC unary service methods in ASP.NET Core is consistent.</span></span> <span data-ttu-id="b16bd-149">두 매개 변수가 있습니다. 첫 번째 매개 변수는 `.proto` 파일에 선언 된 메시지 유형이 고, 두 번째 매개 변수는 ASP.NET Core의 `HttpContext`와 유사 하 게 작동 하는 `ServerCallContext`입니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-149">There are two parameters: the first is the message type declared in the `.proto` file, and the second is a `ServerCallContext` that works similarly to the `HttpContext` from ASP.NET Core.</span></span> <span data-ttu-id="b16bd-150">실제로는 기본 `HttpContext`를 가져오는 데 사용할 수 있는 `ServerCallContext` 클래스에 `GetHttpContext` 라는 확장 메서드가 있는데, 자주 사용 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-150">In fact, there's an extension method called `GetHttpContext` on the `ServerCallContext` class that you can use to get the underlying `HttpContext`, although you shouldn't need to use it often.</span></span> <span data-ttu-id="b16bd-151">이 챕터의 뒷부분에 나오는 `ServerCallContext`와 인증에 대해 설명 하는 장에서 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-151">We'll take a look at `ServerCallContext` later in this chapter, and also in the chapter that discusses authentication.</span></span>

<span data-ttu-id="b16bd-152">메서드의 반환 형식은 `T` 응답 메시지 형식인 `Task<T>`입니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-152">The method's return type is a `Task<T>` where `T` is the response message type.</span></span> <span data-ttu-id="b16bd-153">모든 gRPC 서비스 메서드는 비동기입니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-153">All gRPC service methods are asynchronous.</span></span>

## <a name="migrate-the-portfoliodata-library-to-net-core"></a><span data-ttu-id="b16bd-154">PortfolioData 라이브러리를 .NET Core로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="b16bd-154">Migrate the PortfolioData library to .NET Core</span></span>

<span data-ttu-id="b16bd-155">이 시점에서 프로젝트에는 WCF 솔루션의 `TraderSys.PortfolioData` 클래스 라이브러리에 포함 된 포트폴리오 리포지토리 및 모델이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-155">At this point, the project needs the Portfolio repository and models contained in the `TraderSys.PortfolioData` class library in the WCF solution.</span></span> <span data-ttu-id="b16bd-156">이러한 항목을 가져오는 가장 쉬운 방법은 Visual Studio **새 프로젝트** 대화 상자를 사용 하 여 *클래스 라이브러리 (.NET Standard)* 템플릿을 사용 하 여 새 클래스 라이브러리를 만들거나 .NET Core CLI를 사용 하 여 명령줄에서 `TraderSys.sln` 파일을 포함 하는 디렉터리에서 다음 명령을 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-156">The easiest way to bring them across is to create a new class library using either the Visual Studio **New project** dialog with the *Class Library (.NET Standard)* template, or from the command line using the .NET Core CLI, running the following commands from the directory containing the `TraderSys.sln` file.</span></span>

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

<span data-ttu-id="b16bd-157">라이브러리가 만들어지고 솔루션에 추가 되 면 생성 된 `Class1.cs` 파일을 삭제 하 고 WCF 솔루션 라이브러리의 파일을 새 클래스 라이브러리의 폴더에 복사 하 여 폴더 구조를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-157">Once the library has been created and added to the solution, delete the generated `Class1.cs` file and copy the files from the WCF solution's library into the new class library's folder, keeping the folder structure.</span></span>

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

<span data-ttu-id="b16bd-158">SDK 스타일 .NET 프로젝트에는 자체 디렉터리의 `.cs` 파일이 자동으로 포함 되므로 프로젝트에 명시적으로 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-158">SDK-style .NET projects automatically include any `.cs` files in or under their own directory, so there's no need to explicitly add them to the project.</span></span> <span data-ttu-id="b16bd-159">남은 단계는 `DataContract`를 제거 하 고 `Portfolio` 및 `PortfolioItem` 클래스에서 특성을 `DataMember` 하는 것입니다. 따라서 일반 C# 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-159">The only step remaining is to remove the `DataContract` and `DataMember` attributes from the `Portfolio` and `PortfolioItem` classes so they're plain old C# classes.</span></span>

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

## <a name="use-aspnet-core-dependency-injection"></a><span data-ttu-id="b16bd-160">ASP.NET Core 종속성 주입 사용</span><span class="sxs-lookup"><span data-stu-id="b16bd-160">Use ASP.NET Core dependency injection</span></span>

<span data-ttu-id="b16bd-161">이제이 라이브러리에 대 한 참조를 gRPC 응용 프로그램 프로젝트에 추가 하 고 gRPC 서비스 구현에서 종속성 주입을 사용 하 여 `PortfolioRepository` 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-161">Now you can add a reference to this library to the gRPC application project and consume the `PortfolioRepository` class using dependency injection in the gRPC service implementation.</span></span> <span data-ttu-id="b16bd-162">WCF 응용 프로그램에서는 Autofac IoC 컨테이너에서 종속성 주입을 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-162">In the WCF application, dependency injection was provided by the Autofac IoC container.</span></span> <span data-ttu-id="b16bd-163">ASP.NET Core에 종속성 주입 구운 있습니다. `Startup` 클래스의 `ConfigureServices` 메서드에 리포지토리를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-163">ASP.NET Core has dependency injection baked in; the repository can be registered in the `ConfigureServices` method in the `Startup` class.</span></span>

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

<span data-ttu-id="b16bd-164">이제 다음과 같이 `IPortfolioRepository` 구현을 `PortfolioService` 클래스에서 생성자 매개 변수로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-164">The `IPortfolioRepository` implementation can now be specified as a constructor parameter in the `PortfolioService` class, as follows:</span></span>

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

## <a name="implement-the-grpc-service"></a><span data-ttu-id="b16bd-165">GRPC 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="b16bd-165">Implement the gRPC service</span></span>

<span data-ttu-id="b16bd-166">이제 `portfolios.proto` 파일에서 메시지와 서비스를 선언 했으므로 gRPC 생성 `Portfolios.PortfoliosBase` 클래스에서 상속 되는 `PortfolioService` 클래스에서 서비스 메서드를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-166">Now that you've declared your messages and your service in the `portfolios.proto` file, you have to implement the service methods in the `PortfolioService` class that inherits from the gRPC-generated `Portfolios.PortfoliosBase` class.</span></span> <span data-ttu-id="b16bd-167">메서드는 기본 클래스에서 `virtual`로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-167">The methods are declared as `virtual` in the base class.</span></span> <span data-ttu-id="b16bd-168">이를 재정의 하지 않으면 기본적으로 gRPC "구현 되지 않음" 상태 코드가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-168">If you don't override them, they'll return a gRPC "Not Implemented" status code by default.</span></span>

<span data-ttu-id="b16bd-169">`Get` 메서드를 구현 하 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-169">Start by implementing the `Get` method.</span></span> <span data-ttu-id="b16bd-170">기본 재정의는 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-170">The default override looks like the following example:</span></span>

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

<span data-ttu-id="b16bd-171">첫 번째 문제는 `request.TraderId`가 문자열이 고 서비스에 `Guid`가 필요한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-171">The first issue is that `request.TraderId` is a string, and the service requires a `Guid`.</span></span> <span data-ttu-id="b16bd-172">문자열에 대해 예상 되는 형식이 `UUID`경우에도 코드는 호출자가 잘못 된 값을 보내고 적절 하 게 응답할 가능성을 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-172">Even though the expected format for the string is a `UUID`, the code has to deal with the possibility that a caller has sent an invalid value and respond appropriately.</span></span> <span data-ttu-id="b16bd-173">서비스는 `RpcException`를 throw 하 여 오류에 응답할 수 있으며, 표준 `InvalidArgument` 상태 코드를 사용 하 여 문제를 표현 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-173">The service can respond with errors by throwing an `RpcException`, and use the standard `InvalidArgument` status code to express the problem.</span></span>

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

<span data-ttu-id="b16bd-174">`traderId`에 대 한 적절 한 `Guid` 값이 있으면 리포지토리를 사용 하 여 포트폴리오를 검색 하 고 클라이언트에 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-174">Once there's a proper `Guid` value for `traderId`, the repository can be used to retrieve the Portfolio and return it to the client.</span></span>

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a><span data-ttu-id="b16bd-175">내부 모델을 gRPC 메시지에 매핑</span><span class="sxs-lookup"><span data-stu-id="b16bd-175">Map internal models to gRPC messages</span></span>

<span data-ttu-id="b16bd-176">리포지토리가 자체 POCO 모델 `Portfolio`를 반환 하지만 gRPC에는 자체 Protobuf message *`Portfolio`필요 하므로* 이전 코드는 실제로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-176">The previous code doesn't actually work because the repository is returning its own POCO model `Portfolio`, but gRPC needs *its* own Protobuf message `Portfolio`.</span></span> <span data-ttu-id="b16bd-177">Entity Framework 형식을 데이터 전송 형식에 매핑하는 것과 매우 유사 하 게 가장 좋은 방법은 둘 간의 변환을 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-177">Much like mapping Entity Framework types to data transfer types, the best solution is to provide conversion between the two.</span></span> <span data-ttu-id="b16bd-178">이에 대 한 코드를 저장 하는 좋은 위치는 Protobuf에서 생성 된 클래스에 있습니다 .이 클래스는 확장 될 수 있도록 `partial` 클래스로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-178">A good place to put the code for this is in the Protobuf-generated class, which is declared as a `partial` class so it can be extended.</span></span>

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
> <span data-ttu-id="b16bd-179">`string`/`Guid` 또는 `decimal`/`double` 및 목록 매핑과 같은 하위 수준 형식 변환을 구성 하는 경우 [Automapper](https://automapper.org/) 와 같은 라이브러리를 사용 하 여 내부 모델 클래스에서 Protobuf 형식으로의 변환을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-179">You could use a library like [AutoMapper](https://automapper.org/) to handle this conversion from internal model classes to Protobuf types, as long as you configure the lower-level type conversions like `string`/`Guid` or `decimal`/`double` and the list mapping.</span></span>

<span data-ttu-id="b16bd-180">변환 코드가 준비 되 면 `Get` 메서드 구현을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-180">With the conversion code in place, the `Get` method implementation can be completed.</span></span>

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

<span data-ttu-id="b16bd-181">`GetAll` 메서드의 구현은 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-181">The implementation of the `GetAll` method is similar.</span></span> <span data-ttu-id="b16bd-182">Protobuf 메시지의 `repeated` 필드는 `RepeatedField<T>`형식의 `readonly` 속성으로 생성 되므로 다음 예제와 같이 `AddRange` 메서드를 사용 하 여 항목을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-182">Note that the `repeated` fields on Protobuf messages are generated as `readonly` properties of type `RepeatedField<T>`, so you have to add items to them using the `AddRange` method, like in the following example:</span></span>

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

<span data-ttu-id="b16bd-183">WCF 요청-응답 서비스를 gRPC로 마이그레이션 했으면 `.proto` 파일에서 해당 클라이언트에 대 한 클라이언트를 만드는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-183">Having successfully migrated the WCF request-reply service to gRPC, let's look at creating a client for it from the `.proto` file.</span></span>

## <a name="generate-client-code"></a><span data-ttu-id="b16bd-184">클라이언트 코드 생성</span><span class="sxs-lookup"><span data-stu-id="b16bd-184">Generate client code</span></span>

<span data-ttu-id="b16bd-185">동일한 솔루션에서 클라이언트를 포함 하는 .NET Standard 클래스 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-185">Create a .NET Standard class library in the same solution to contain the client.</span></span> <span data-ttu-id="b16bd-186">이는 주로 클라이언트 코드를 만드는 예제 이지만 NuGet을 사용 하 여 이러한 라이브러리를 패키지 하 고 다른 .NET 팀이 사용할 수 있도록 내부 리포지토리에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-186">This is primarily an example of creating client code, but you could package such a library using NuGet and distribute it on an internal repository for other .NET teams to consume.</span></span> <span data-ttu-id="b16bd-187">계속 해 서 `TraderSys.Portfolios.Client` 라는 새 .NET Standard 클래스 라이브러리를 솔루션에 추가 하 고 `Class1.cs` 파일을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-187">Go ahead and add a new .NET Standard Class Library called `TraderSys.Portfolios.Client` to the solution and delete the `Class1.cs` file.</span></span>

> [!CAUTION]
> <span data-ttu-id="b16bd-188">[Grpc .Net 클라이언트](https://www.nuget.org/packages/Grpc.Net.Client) NuGet 패키지에는 .net Core 3.0 (또는 다른 .NET Standard 2.1 규격 런타임)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-188">The [Grpc.Net.Client](https://www.nuget.org/packages/Grpc.Net.Client) NuGet package requires .NET Core 3.0 (or another .NET Standard 2.1-compliant runtime).</span></span> <span data-ttu-id="b16bd-189">이전 버전의 .NET Framework 및 .NET Core는 [Grpc. 핵심](https://www.nuget.org/packages/Grpc.Core) NuGet 패키지에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-189">Earlier versions of .NET Framework and .NET Core are supported by the [Grpc.Core](https://www.nuget.org/packages/Grpc.Core) NuGet package.</span></span>

<span data-ttu-id="b16bd-190">Visual Studio 2019에서는 이전 버전의 Visual Studio에서 WCF 프로젝트에 서비스 참조를 추가 하는 방법과 유사 하 게 gRPC 서비스에 대 한 참조를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-190">In Visual Studio 2019, you can add references to gRPC services similar to the way you'd add Service References to WCF projects in earlier versions of Visual Studio.</span></span> <span data-ttu-id="b16bd-191">서비스 참조 및 연결된 서비스는 모두 동일한 UI에서 관리 되며, 솔루션 탐색기에서 `TraderSys.Portfolios.Client` 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭 하 고 **연결 된 서비스 추가**를 선택 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-191">Service References and Connected Services are all managed under the same UI now, which you can access by right-clicking the **Dependencies** node in the `TraderSys.Portfolios.Client` project in Solution Explorer and selecting **Add Connected Service**.</span></span> <span data-ttu-id="b16bd-192">표시 되는 도구 창에서 **서비스 참조** 섹션을 선택 하 고 **새 Grpc 서비스 참조 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-192">In the tool window that appears, select the **Service References** section and click **Add new gRPC service reference**.</span></span>

![Visual Studio 2019의 연결된 서비스 UI](media/migrate-request-reply/add-connected-service.png)

<span data-ttu-id="b16bd-194">`TraderSys.Portfolios` 프로젝트에서 `portfolios.proto` 파일을 찾아 **클래스의 유형을 클라이언트로 생성 하** 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-194">Browse to the `portfolios.proto` file in the `TraderSys.Portfolios` project, leave the **type of class to be generated** as **Client**, and click **OK**.</span></span>

![Visual Studio 2019의 새 gRPC 서비스 참조 추가 대화 상자](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> <span data-ttu-id="b16bd-196">이 대화 상자는 URL 필드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-196">Notice that this dialog also provides a URL field.</span></span> <span data-ttu-id="b16bd-197">조직에서 `.proto` 파일의 웹 액세스 가능 디렉터리를 유지 관리 하는 경우이 URL 주소를 설정 하 여 클라이언트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-197">If your organization maintains a web-accessible directory of `.proto` files, you can create clients just by setting this URL address.</span></span>

<span data-ttu-id="b16bd-198">Visual Studio **연결 된 서비스 추가** 기능을 사용 하는 경우 `portfolios.proto` 파일은 복사 되지 않고 클래스 라이브러리 프로젝트에 *연결 된 파일로*추가 되므로 서비스 프로젝트의 파일에 대 한 변경 내용이 클라이언트 프로젝트에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-198">When using the Visual Studio **Add Connected Service** feature, the `portfolios.proto` file is added to the Class Library project as a *linked file*, rather than copied, so changes to the file in the service project will automatically be applied in the client project.</span></span> <span data-ttu-id="b16bd-199">`csproj` 파일의 `<Protobuf>` 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-199">The `<Protobuf>` element in the `csproj` file looks like this:</span></span>

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> <span data-ttu-id="b16bd-200">Visual Studio를 사용 하지 않거나 명령줄에서 작업 하는 것을 선호 하는 경우 **dotnet pc** 전역 도구를 사용 하 여 .Net grpc 프로젝트 내에서 Protobuf 참조를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-200">If you are not using Visual Studio or prefer to work from the command line, you can use the **dotnet-grpc** global tool to manage Protobuf references within a .NET gRPC project.</span></span> <span data-ttu-id="b16bd-201">[자세한 내용은 **dotnet grpc** 설명서를 참조](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc)하세요.</span><span class="sxs-lookup"><span data-stu-id="b16bd-201">[Refer to the **dotnet-grpc** documentation for more information](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc).</span></span>

### <a name="use-the-portfolios-service-from-a-client-application"></a><span data-ttu-id="b16bd-202">클라이언트 응용 프로그램에서 포트폴리오 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="b16bd-202">Use the Portfolios service from a client application</span></span>

<span data-ttu-id="b16bd-203">다음 코드는 콘솔 응용 프로그램에서 생성 된 클라이언트를 사용 하는 간단한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-203">The following code is a brief example of using the generated client in a console application.</span></span> <span data-ttu-id="b16bd-204">GRPC 클라이언트 코드에 대 한 자세한 탐색은이 챕터의 끝에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-204">A more detailed exploration of the gRPC client code is at the end of this chapter.</span></span>

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

<span data-ttu-id="b16bd-205">이제 기본 WCF 응용 프로그램을 ASP.NET Core gRPC 서비스로 마이그레이션하고 .NET 응용 프로그램에서 서비스를 사용 하는 클라이언트를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-205">Now, you've migrated a basic WCF application to an ASP.NET Core gRPC service and created a client to consume the service from a .NET application.</span></span> <span data-ttu-id="b16bd-206">다음 섹션에서는 관련 된 "이중" 서비스에 대해 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="b16bd-206">The next section will cover the more involved "duplex" services.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b16bd-207">[이전](create-project.md)
>[다음](migrate-duplex-services.md)</span><span class="sxs-lookup"><span data-stu-id="b16bd-207">[Previous](create-project.md)
[Next](migrate-duplex-services.md)</span></span>
