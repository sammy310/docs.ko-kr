---
title: 프로토콜 버퍼 - WCF 개발자를 위한 gRPC
description: gRPC 네트워킹에 사용되는 프로토콜 버퍼스 와이어 형식 소개.
ms.date: 09/09/2019
ms.openlocfilehash: 35319d299a8bc2866a87954b3e54bfda9314ffe8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147934"
---
# <a name="protocol-buffers"></a>프로토콜 버퍼

gRPC 서비스는 WCF(Windows 통신 재단)의 데이터 계약과 유사한 *프로토콜 버퍼(Protobuf) 메시지로*데이터를 송수신합니다. Protobuf는 XML 또는 JSON과 같은 사람이 읽을 수 있는 형식의 오버헤드 없이 기계가 읽고 쓸 수 있도록 구조화된 데이터를 직렬화하는 효율적인 방법입니다.

이 장에서는 Protobuf의 작동 방식과 사용자 고유의 Protobuf 메시지를 정의하는 방법을 다룹니다.

## <a name="how-protobuf-works"></a>프로토부프의 작동 방식

WCF의 데이터 계약을 포함한 대부분의 .NET 개체 직렬화 기술은 리플렉션을 사용하여 런타임에 개체 구조를 분석합니다. 반면 대부분의 Protobuf 라이브러리는 `.proto` 파일에서 전용 언어(프로토콜 버퍼*언어)를*사용하여 구조를 미리 정의해야 합니다. 그런 다음 컴파일러는 이 파일을 사용하여 지원되는 플랫폼에 대한 코드를 생성합니다. 지원되는 플랫폼에는 .NET, Java, C/C+, 자바스크립트 등이 있습니다.

프로토부프 컴파일러는 `protoc`대체 구현을 사용할 수 있지만 Google에서 유지 관리합니다. 생성된 코드는 데이터의 빠른 직렬화 및 직렬화를 위해 효율적이고 최적화되어 있습니다.

Protobuf 와이어 형식은 이진 인코딩입니다. 그것은 메시지를 나타내는 데 사용 되는 바이트의 수를 최소화 하기 위해 몇 가지 영리한 트릭을 사용 합니다. Protobuf를 사용하기 위해 바이너리 인코딩 형식에 대한 지식이 필요하지 않습니다. 그러나 관심이 있다면 프로토콜 버퍼 웹 사이트에서 자세히 알아볼 수 [있습니다.](https://developers.google.com/protocol-buffers/docs/encoding)

>[!div class="step-by-step"]
>[이전](why-grpc.md)
>[다음](protobuf-messages.md)
