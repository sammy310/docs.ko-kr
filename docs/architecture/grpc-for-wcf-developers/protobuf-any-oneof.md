---
title: Variant 형식의 Protobuf Any 및 중 필드-WCF 개발자를 위한 gRPC
description: 모든 형식 및 중 키워드를 사용 하 여 메시지에서 variant 개체 형식을 나타내는 방법에 대해 알아봅니다.
ms.date: 09/09/2019
ms.openlocfilehash: 6fe7acbd1ec35289f7ad6f3acee8509ab934619d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543198"
---
# <a name="protobuf-any-and-oneof-fields-for-variant-types"></a>Variant 형식에 대 한 Protobuf Any 및 중 필드

WCF (Windows Communication Foundation)에서 동적 속성 형식 (`object`형식의 속성)을 처리 하는 것은 복잡 합니다. 예를 들어 serializer를 지정 하 고 [Knowntype](xref:System.Runtime.Serialization.KnownTypeAttribute) 특성을 제공 해야 합니다.

프로토콜 버퍼 (Protobuf)는 둘 이상의 형식이 될 수 있는 값을 처리 하는 두 가지 간단한 옵션을 제공 합니다. `Any` 형식은 알려진 Protobuf 메시지 유형을 나타낼 수 있습니다. `oneof` 키워드를 사용 하 여 모든 메시지에서 필드 범위 중 하나만 설정할 수 있도록 지정할 수 있습니다.

## <a name="any"></a>Any

`Any`는 Protobuf의 "잘 알려진 형식" 중 하나 이며, 지원 되는 모든 언어의 구현이 포함 된 유용한 재사용 가능 메시지 유형을 수집 합니다. `Any` 형식을 사용 하려면 `google/protobuf/any.proto` 정의를 가져와야 합니다.

```protobuf
syntax "proto3"

import "google/protobuf/any.proto"

message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
    int32 id = 1;
    google.protobuf.Any instrument = 2;
}
```

C# 코드에서 `Any` 클래스는 필드를 설정 하 고, 메시지를 추출 하 고, 형식을 확인 하는 메서드를 제공 합니다.

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    if (change.Instrument.Is(Stock.Descriptor))
    {
        FormatStock(change.Instrument.Unpack<Stock>());
    }
    else if (change.Instrument.Is(Currency.Descriptor))
    {
        FormatCurrency(change.Instrument.Unpack<Currency>());
    }
    else
    {
        throw new ArgumentException("Unknown instrument type");
    }
}
```

Protobuf의 내부 리플렉션 코드는 생성 된 각 형식에 대해 `Descriptor` 정적 필드를 사용 하 여 `Any` 필드 형식을 확인 합니다. `TryUnpack<T>` 메서드도 있지만에서 초기화 되지 않은 `T` 인스턴스를 만드는 경우에도 마찬가지입니다. 앞에서 설명한 대로 `Is` 메서드를 사용 하는 것이 좋습니다.

## <a name="oneof"></a>중

중 필드는 언어 기능입니다. 컴파일러는 메시지 클래스를 생성할 때 `oneof` 키워드를 처리 합니다. `oneof`를 사용 하 여 `ChangeNotification` 메시지를 지정 하는 것은 다음과 같습니다.

```protobuf
message Stock {
    // Stock-specific data
}

message Currency {
    // Currency-specific data
}

message ChangeNotification {
  int32 id = 1;
  oneof instrument {
    Stock stock = 2;
    Currency currency = 3;
  }
}
```

`oneof` 집합 내의 필드는 전체 메시지 선언에 고유한 필드 번호를 포함 해야 합니다.

`oneof`사용 하는 경우 생성 C# 된 코드에는 설정 된 필드를 지정 하는 열거형이 포함 됩니다. 열거형을 테스트 하 여 설정 된 필드를 찾을 수 있습니다. 설정 되지 않은 필드는 예외를 throw 하는 대신 `null` 또는 기본값을 반환 합니다.

```csharp
public void FormatChangeNotification(ChangeNotification change)
{
    switch (change.InstrumentCase)
    {
        case ChangeNotification.InstrumentOneofCase.None:
            return;
        case ChangeNotification.InstrumentOneofCase.Stock:
            FormatStock(change.Stock);
            break;
        case ChangeNotification.InstrumentOneofCase.Currency:
            FormatCurrency(change.Currency);
            break;
        default:
            throw new ArgumentException("Unknown instrument type");
    }
}
```

`oneof` 집합의 일부인 필드를 설정 하면 자동으로 집합의 다른 필드가 모두 지워집니다. `oneof`에서 `repeated`를 사용할 수 없습니다. 대신이 제한 사항을 해결 하기 위해 반복 되는 필드 또는 `oneof` 집합을 사용 하 여 중첩 된 메시지를 만들 수 있습니다.

>[!div class="step-by-step"]
>[이전](protobuf-reserved.md)
>[다음](protobuf-enums.md)
