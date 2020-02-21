---
title: 프로토콜 버퍼-WCF 개발자를 위한 gRPC
description: GRPC 네트워킹에 사용 되는 프로토콜 버퍼 통신 형식을 소개 합니다.
ms.date: 09/09/2019
ms.openlocfilehash: cc4ff272a9912d6f2dd8f8ddb1972c7369f980fe
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503447"
---
# <a name="protocol-buffers"></a>프로토콜 버퍼

gRPC 서비스는 WCF (Windows Communication Foundation)의 데이터 계약과 비슷하게 *Protobuf (프로토콜 버퍼) 메시지로*데이터를 보내고 받습니다. Protobuf은 사용자가 읽을 수 있는 형식 (예: XML 또는 JSON)의 오버 헤드 없이 읽기 및 쓰기를 위해 컴퓨터의 구조화 된 데이터를 serialize 하는 효율적인 방법입니다.

이 장에서는 Protobuf가 작동 하는 방식과 고유한 Protobuf 메시지를 정의 하는 방법을 설명 합니다.

## <a name="how-protobuf-works"></a>Protobuf 작동 방식

WCF의 데이터 계약을 비롯 한 대부분의 .NET 개체 serialization 기술은 런타임에 개체 구조를 분석 하기 위해 리플렉션을 사용 하 여 작업 합니다. 이와 대조적으로 대부분의 Protobuf 라이브러리는 `.proto` 파일에서 전용 언어 (*프로토콜 버퍼 언어*)를 사용 하 여 앞에서 구조를 정의 해야 합니다. 그런 다음 컴파일러는이 파일을 사용 하 여 지원 되는 플랫폼에 대 한 코드를 생성 합니다. 지원 되는 플랫폼에는 .NET, JavaC++, C/, JavaScript 등이 포함 됩니다. 

Protobuf 컴파일러 `protoc`는 대체 구현을 사용할 수 있지만 Google에서 유지 관리 됩니다. 생성 된 코드는 데이터의 빠른 serialization 및 deserialization을 위해 효율적이 고 최적화 됩니다.

Protobuf 통신 형식은 이진 인코딩입니다. 메시지를 나타내는 데 사용 되는 바이트 수를 최소화 하기 위해 몇 가지 뛰어난 트릭을 사용 합니다. 이진 인코딩 형식에 대 한 정보는 Protobuf를 사용 하는 데 필요 하지 않습니다. 하지만 관심이 있는 경우 [프로토콜 버퍼 웹 사이트](https://developers.google.com/protocol-buffers/docs/encoding)에서 자세히 알아볼 수 있습니다.

>[!div class="step-by-step"]
>[이전](why-grpc.md)
>[다음](protobuf-messages.md)
