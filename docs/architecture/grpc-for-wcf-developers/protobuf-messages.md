---
title: Protobuf 메시지-WCF 개발자를 위한 gRPC
description: Protobuf 메시지가 IDL에 정의 되 고에서 C#생성 되는 방법에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: 4d543fe88c21999cd820a0bb98073d58a229913a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967430"
---
# <a name="protobuf-messages"></a>Protobuf 메시지

이 섹션에서는 `.proto` 파일에서 Protobuf 메시지를 선언 하는 방법에 대해 설명 하 고, 필드 번호 및 형식의 기본적인 개념을 C# 설명 하 고, `protoc` 컴파일러에 의해 생성 된 코드를 살펴봅니다. 이 장의 나머지 부분에서는 Protobuf에서 다양 한 유형의 데이터가 표시 되는 방식에 대해 자세히 살펴봅니다.

## <a name="declaring-a-message"></a>메시지 선언

WCF에서 주식 시장 거래 응용 프로그램에 대 한 `Stock` 클래스는 다음 예제와 같이 정의 될 수 있습니다.

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

Protobuf에서 동일한 클래스를 구현 하려면 `.proto` 파일에 선언 해야 합니다. 그러면 `protoc` 컴파일러는 빌드 프로세스의 일부로 .NET 클래스를 생성 합니다.

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

첫 번째 줄은 사용 중인 구문 버전을 선언 합니다. 이 언어 버전 3은 2016에서 출시 되었으며 gRPC 서비스에 권장 되는 버전입니다.

`option csharp_namespace` 줄에서는 생성 C# 된 형식에 사용할 네임 스페이스를 지정 합니다. 이 옵션은 `.proto` 파일이 다른 언어로 컴파일될 때 무시 됩니다. Protobuf 파일은 여러 언어에 대 한 언어별 옵션을 포함 하는 것이 일반적입니다.

`Stock` 메시지 정의는 각각 유형, 이름 및 필드 번호가 있는 4 개의 필드를 지정 합니다.

## <a name="field-numbers"></a>필드 번호

필드 번호는 Protobuf의 중요 한 부분입니다. 이진 인코딩 데이터의 필드를 식별 하는 데 사용 됩니다. 즉, 버전에서 서비스 버전으로 변경할 수 없습니다. 이러한 이점은 이전 버전과 앞으로의 호환성이 가능 하다는 것입니다. 클라이언트와 서비스는 누락 값이 처리 되는 경우에는 알 수 없는 필드 번호만 무시 합니다.

이진 형식에서 필드 번호는 형식 식별자와 결합 됩니다. 1에서 15 사이의 필드 번호는 해당 형식을 단일 바이트로 인코딩할 수 있습니다. 16에서 2047 사이의 숫자는 2 바이트를 차지 합니다. 어떤 이유로 든 메시지에서 필드가 2047 개를 초과 해야 하는 경우 더 높은 수준으로 이동할 수 있습니다. 필드 번호 1에서 15 까지의 단일 바이트 식별자가 더 나은 성능을 제공 하므로 가장 기본적인 자주 사용 되는 필드에 사용 해야 합니다.

## <a name="types"></a>형식

형식 선언은 Protobuf의 네이티브 스칼라 데이터 형식을 사용 하며, [다음 섹션](protobuf-data-types.md)에서 자세히 설명 합니다. 이 장의 나머지 부분에서는 Protobuf의 기본 제공 형식에 대해 설명 하 고 일반적인 .NET 형식과의 관계를 보여 줍니다.

> [!NOTE]
> Protobuf는 기본적으로 `decimal` 형식을 지원 하지 않으므로 double이 대신 사용 됩니다. 전체 자릿수가 전체 자릿수가 필요한 응용 프로그램의 경우이 챕터의 다음 부분에 있는 [10 진수에 대 한 섹션](protobuf-data-types.md#decimals) 을 참조 하세요.

## <a name="the-generated-code"></a>생성된 코드

응용 프로그램을 빌드할 때 Protobuf는 각 메시지에 대 한 클래스를 만들어 네이티브 형식을 형식에 C# 매핑합니다. 생성 된 `Stock` 형식에는 다음 서명이 있습니다.

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

각 클래스는 이진 통신 형식으로 serialize 및 deserialize 하는 데 필요한 모든 코드를 포함 하기 때문에 생성 되는 실제 코드는 이보다 훨씬 더 복잡 합니다.

### <a name="property-names"></a>속성 이름

Protobuf 컴파일러는 `.proto` 파일에 `snake_case` 되었지만 속성 이름에 `PascalCase` 적용 됩니다. [Protobuf 스타일 가이드](https://developers.google.com/protocol-buffers/docs/style) 는 다른 플랫폼에 대 한 코드 생성이 해당 규칙에 대해 예상 되는 대/소문자를 생성 하도록 메시지 정의에 `snake_case`를 사용 하는 것을 권장 합니다.

>[!div class="step-by-step"]
>[이전](protocol-buffers.md)
>[다음](protobuf-data-types.md)
