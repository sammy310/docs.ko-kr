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
# <a name="protobuf-messages"></a>Protobuf 메시지

이 섹션에서는 파일에서 `.proto` 프로토콜 버퍼(Protobuf) 메시지를 선언하는 방법을 설명합니다. 필드 번호 및 형식의 기본 개념을 설명하고 `protoc` 컴파일러가 생성하는 C# 코드를 살펴봅니다.

이 장의 나머지 부분에서는 Protobuf에서 다양한 유형의 데이터가 어떻게 표현되는지 자세히 살펴보겠습니다.

## <a name="declaring-a-message"></a>메시지 선언

WCF(Windows 통신 재단)에서 주식 시장 거래 응용 프로그램에 대한 클래스는 `Stock` 다음과 같이 정의될 수 있습니다.

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

Protobuf에서 동등한 클래스를 구현하려면 `.proto` 파일에서 선언해야 합니다. 그러면 `protoc` 컴파일러는 빌드 프로세스의 일부로 .NET 클래스를 생성합니다.

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

첫 번째 줄은 사용 중인 구문 버전을 선언합니다. 언어의 버전 3은 2016년에 출시되었습니다. gRPC 서비스에 권장하는 버전입니다.

줄은 `option csharp_namespace` 생성된 C# 형식에 사용할 네임스페이스를 지정합니다. 이 옵션은 다른 언어에 대해 파일을 컴파일할 `.proto` 때 무시됩니다. Protobuf 파일에는 여러 언어에 대한 언어별 옵션이 포함되어 있는 경우가 많습니다.

메시지 `Stock` 정의는 네 개의 필드를 지정합니다. 각각에는 유형, 이름 및 필드 번호가 있습니다.

## <a name="field-numbers"></a>필드 번호

필드 번호는 프로토부프의 중요한 부분입니다. 이진 인코딩된 데이터의 필드를 식별하는 데 사용되므로 서비스 버전에서 버전으로 변경할 수 없습니다. 장점은 이전 버전과의 호환성과 이전 호환성이 가능하다는 것입니다. 클라이언트와 서비스는 누락된 값이 처리될 가능성이 있는 한 모르는 필드 번호를 무시합니다.

이진 형식에서 필드 번호는 형식 식별자와 결합됩니다. 1에서 15까지의 필드 번호는 해당 형식을 단일 바이트로 인코딩할 수 있습니다. 16에서 2,047까지의 숫자는 2 바이트를 차지합니다. 어떤 이유로든 메시지에 2,047개 이상의 필드가 필요한 경우 더 높은 높이로 올라갈 수 있습니다. 필드 번호 1에서 15에 대한 단일 바이트 식별자는 더 나은 성능을 제공하므로 가장 기본적이며 자주 사용되는 필드에 사용해야 합니다.

## <a name="types"></a>유형

형식 선언은 다음 [섹션에서](protobuf-data-types.md)자세히 설명하는 Protobuf의 기본 스칼라 데이터 형식을 사용하고 있습니다. 이 장의 나머지 부분에서는 Protobuf의 기본 제공 형식을 다루고 일반적인 .NET 형식과 어떻게 관련되는지 보여 줄 것입니다.

> [!NOTE]
> Protobuf는 기본적으로 `decimal` 형식을 지원하지 않으므로 `double` 대신 사용됩니다. 전체 소수점 정밀도가 필요한 응용 프로그램의 경우 이 장의 다음 부분의 [소수점 구분을](protobuf-data-types.md#decimals) 참조하십시오.

## <a name="the-generated-code"></a>생성된 코드

응용 프로그램을 빌드할 때 Protobuf는 각 메시지에 대한 클래스를 만들어 네이티브 형식을 C# 형식에 매핑합니다. 생성된 `Stock` 형식에는 다음과 같은 서명이 있습니다.

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

생성되는 실제 코드는 이보다 훨씬 복잡합니다. 그 이유는 각 클래스에 이진 와이어 형식으로 직렬화하고 직렬화하는 데 필요한 모든 코드가 포함되어 있습니다.

### <a name="property-names"></a>속성 이름

Protobuf 컴파일러는 파일에 `PascalCase` 있었지만 속성 이름에 적용되었습니다. `snake_case` `.proto` [Protobuf 스타일 가이드는](https://developers.google.com/protocol-buffers/docs/style) `snake_case` 다른 플랫폼의 코드 생성이 해당 규칙에 대해 예상되는 사례를 생성하도록 메시지 정의에 사용하는 것이 좋습니다.

>[!div class="step-by-step"]
>[이전](protocol-buffers.md)
>[다음](protobuf-data-types.md)
