---
title: 프로토부프 메시지 - WCF 개발자를 위한 gRPC
description: Protobuf 메시지가 IDL에 정의되고 C#에서 생성되는 방법을 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: 5b3d4383de39a3785ef804fec21939a740f54669
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147986"
---
# <a name="protobuf-messages"></a><span data-ttu-id="dbef2-103">Protobuf 메시지</span><span class="sxs-lookup"><span data-stu-id="dbef2-103">Protobuf messages</span></span>

<span data-ttu-id="dbef2-104">이 섹션에서는 파일에서 `.proto` 프로토콜 버퍼(Protobuf) 메시지를 선언하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-104">This section covers how to declare Protocol Buffer (Protobuf) messages in `.proto` files.</span></span> <span data-ttu-id="dbef2-105">필드 번호 및 형식의 기본 개념을 설명하고 `protoc` 컴파일러가 생성하는 C# 코드를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-105">It explains the fundamental concepts of field numbers and types, and it looks at the C# code that the `protoc` compiler generates.</span></span>

<span data-ttu-id="dbef2-106">이 장의 나머지 부분에서는 Protobuf에서 다양한 유형의 데이터가 어떻게 표현되는지 자세히 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-106">The rest of the chapter will look in more detail at how different types of data are represented in Protobuf.</span></span>

## <a name="declaring-a-message"></a><span data-ttu-id="dbef2-107">메시지 선언</span><span class="sxs-lookup"><span data-stu-id="dbef2-107">Declaring a message</span></span>

<span data-ttu-id="dbef2-108">WCF(Windows 통신 재단)에서 주식 시장 거래 응용 프로그램에 대한 클래스는 `Stock` 다음과 같이 정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-108">In Windows Communication Foundation (WCF), a `Stock` class for a stock market trading application might be defined like the following example:</span></span>

```csharp
namespace TraderSys
{
    [DataContract]
    public class Stock
    {
        [DataMember]
        public int Id { get; set;}
        [DataMember]
        public string Symbol { get; set;}
        [DataMember]
        public string DisplayName { get; set;}
        [DataMember]
        public int MarketId { get; set; }
    }
}
```

<span data-ttu-id="dbef2-109">Protobuf에서 동등한 클래스를 구현하려면 `.proto` 파일에서 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-109">To implement the equivalent class in Protobuf, you must declare it in the `.proto` file.</span></span> <span data-ttu-id="dbef2-110">그러면 `protoc` 컴파일러는 빌드 프로세스의 일부로 .NET 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-110">The `protoc` compiler will then generate the .NET class as part of the build process.</span></span>

```protobuf
syntax "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string display_name = 3;
    int32 market_id = 4;

}  
```

<span data-ttu-id="dbef2-111">첫 번째 줄은 사용 중인 구문 버전을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-111">The first line declares the syntax version being used.</span></span> <span data-ttu-id="dbef2-112">언어의 버전 3은 2016년에 출시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-112">Version 3 of the language was released in 2016.</span></span> <span data-ttu-id="dbef2-113">gRPC 서비스에 권장하는 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-113">It's the version that we recommend for gRPC services.</span></span>

<span data-ttu-id="dbef2-114">줄은 `option csharp_namespace` 생성된 C# 형식에 사용할 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-114">The `option csharp_namespace` line specifies the namespace to be used for the generated C# types.</span></span> <span data-ttu-id="dbef2-115">이 옵션은 다른 언어에 대해 파일을 컴파일할 `.proto` 때 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-115">This option will be ignored when the `.proto` file is compiled for other languages.</span></span> <span data-ttu-id="dbef2-116">Protobuf 파일에는 여러 언어에 대한 언어별 옵션이 포함되어 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-116">Protobuf files often contain language-specific options for several languages.</span></span>

<span data-ttu-id="dbef2-117">메시지 `Stock` 정의는 네 개의 필드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-117">The `Stock` message definition specifies four fields.</span></span> <span data-ttu-id="dbef2-118">각각에는 유형, 이름 및 필드 번호가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-118">Each has a type, a name, and a field number.</span></span>

## <a name="field-numbers"></a><span data-ttu-id="dbef2-119">필드 번호</span><span class="sxs-lookup"><span data-stu-id="dbef2-119">Field numbers</span></span>

<span data-ttu-id="dbef2-120">필드 번호는 프로토부프의 중요한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-120">Field numbers are an important part of Protobuf.</span></span> <span data-ttu-id="dbef2-121">이진 인코딩된 데이터의 필드를 식별하는 데 사용되므로 서비스 버전에서 버전으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-121">They're used to identify fields in the binary encoded data, which means they can't change from version to version of your service.</span></span> <span data-ttu-id="dbef2-122">장점은 이전 버전과의 호환성과 이전 호환성이 가능하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-122">The advantage is that backward compatibility and forward compatibility are possible.</span></span> <span data-ttu-id="dbef2-123">클라이언트와 서비스는 누락된 값이 처리될 가능성이 있는 한 모르는 필드 번호를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-123">Clients and services will simply ignore field numbers that they don't know about, as long as the possibility of missing values is handled.</span></span>

<span data-ttu-id="dbef2-124">이진 형식에서 필드 번호는 형식 식별자와 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-124">In the binary format, the field number is combined with a type identifier.</span></span> <span data-ttu-id="dbef2-125">1에서 15까지의 필드 번호는 해당 형식을 단일 바이트로 인코딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-125">Field numbers from 1 to 15 can be encoded with their type as a single byte.</span></span> <span data-ttu-id="dbef2-126">16에서 2,047까지의 숫자는 2 바이트를 차지합니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-126">Numbers from 16 to 2,047 take 2 bytes.</span></span> <span data-ttu-id="dbef2-127">어떤 이유로든 메시지에 2,047개 이상의 필드가 필요한 경우 더 높은 높이로 올라갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-127">You can go higher if you need more than 2,047 fields on a message for any reason.</span></span> <span data-ttu-id="dbef2-128">필드 번호 1에서 15에 대한 단일 바이트 식별자는 더 나은 성능을 제공하므로 가장 기본적이며 자주 사용되는 필드에 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-128">The single byte identifiers for field numbers 1 to 15 offer better performance, so you should use them for the most basic, frequently used fields.</span></span>

## <a name="types"></a><span data-ttu-id="dbef2-129">유형</span><span class="sxs-lookup"><span data-stu-id="dbef2-129">Types</span></span>

<span data-ttu-id="dbef2-130">형식 선언은 다음 [섹션에서](protobuf-data-types.md)자세히 설명하는 Protobuf의 기본 스칼라 데이터 형식을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-130">The type declarations are using Protobuf's native scalar data types, which are discussed in more detail in [the next section](protobuf-data-types.md).</span></span> <span data-ttu-id="dbef2-131">이 장의 나머지 부분에서는 Protobuf의 기본 제공 형식을 다루고 일반적인 .NET 형식과 어떻게 관련되는지 보여 줄 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-131">The rest of this chapter will cover Protobuf's built-in types and show how they relate to common .NET types.</span></span>

> [!NOTE]
> <span data-ttu-id="dbef2-132">Protobuf는 기본적으로 `decimal` 형식을 지원하지 않으므로 `double` 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-132">Protobuf doesn't natively support a `decimal` type, so `double` is used instead.</span></span> <span data-ttu-id="dbef2-133">전체 소수점 정밀도가 필요한 응용 프로그램의 경우 이 장의 다음 부분의 [소수점 구분을](protobuf-data-types.md#decimals) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="dbef2-133">For applications that require full decimal precision, refer to the [section on decimals](protobuf-data-types.md#decimals) in the next part of this chapter.</span></span>

## <a name="the-generated-code"></a><span data-ttu-id="dbef2-134">생성된 코드</span><span class="sxs-lookup"><span data-stu-id="dbef2-134">The generated code</span></span>

<span data-ttu-id="dbef2-135">응용 프로그램을 빌드할 때 Protobuf는 각 메시지에 대한 클래스를 만들어 네이티브 형식을 C# 형식에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-135">When you build your application, Protobuf creates classes for each of your messages, mapping its native types to C# types.</span></span> <span data-ttu-id="dbef2-136">생성된 `Stock` 형식에는 다음과 같은 서명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-136">The generated `Stock` type would have the following signature:</span></span>

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

<span data-ttu-id="dbef2-137">생성되는 실제 코드는 이보다 훨씬 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-137">The actual code that's generated is far more complicated than this.</span></span> <span data-ttu-id="dbef2-138">그 이유는 각 클래스에 이진 와이어 형식으로 직렬화하고 직렬화하는 데 필요한 모든 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-138">The reason is that each class contains all the code necessary to serialize and deserialize itself to the binary wire format.</span></span>

### <a name="property-names"></a><span data-ttu-id="dbef2-139">속성 이름</span><span class="sxs-lookup"><span data-stu-id="dbef2-139">Property names</span></span>

<span data-ttu-id="dbef2-140">Protobuf 컴파일러는 파일에 `PascalCase` 있었지만 속성 이름에 적용되었습니다. `snake_case` `.proto`</span><span class="sxs-lookup"><span data-stu-id="dbef2-140">Note that the Protobuf compiler applied `PascalCase` to the property names, although they were `snake_case` in the `.proto` file.</span></span> <span data-ttu-id="dbef2-141">[Protobuf 스타일 가이드는](https://developers.google.com/protocol-buffers/docs/style) `snake_case` 다른 플랫폼의 코드 생성이 해당 규칙에 대해 예상되는 사례를 생성하도록 메시지 정의에 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dbef2-141">The [Protobuf style guide](https://developers.google.com/protocol-buffers/docs/style) recommends using `snake_case` in your message definitions so that the code generation for other platforms produces the expected case for their conventions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dbef2-142">[이전](protocol-buffers.md)
>[다음](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="dbef2-142">[Previous](protocol-buffers.md)
[Next](protobuf-data-types.md)</span></span>
