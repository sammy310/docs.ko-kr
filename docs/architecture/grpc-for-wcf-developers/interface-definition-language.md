---
title: 인터페이스 정의 언어-WCF 개발자를 위한 gRPC
description: 프로토콜 버퍼 IDL을 소개 합니다.
ms.date: 09/02/2019
ms.openlocfilehash: 841f041ae350e76e648c71f9d6d113b9d39e0d3b
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543211"
---
# <a name="interface-definition-language"></a>IDL(Interface Definition Language)

WCF (Windows Communication Foundation)를 사용 하면 서비스에서 WSDL (웹 서비스 정의 언어)을 사용 하 여 설명 메타 데이터를 노출할 수 있습니다. WSDL은 런타임에 .NET 리플렉션을 사용 하 여 동적으로 생성 됩니다. 개발자는이 메타 데이터를 사용 하 여 HTTP를 통한 SOAP와 같은 플랫폼 중립적인 바인딩을 사용 하는 경우 해당 서비스에 대 한 클라이언트를 생성할 수 있습니다.

gRPC는 프로토콜 버퍼의 IDL (Interface Definition Language)을 사용 합니다. 프로토콜 버퍼 IDL은 개방형 사양을 사용 하는 사용자 지정 플랫폼 중립적인 언어입니다. 개발자는 입력 및 출력과 함께 서비스를 설명 하는 `.proto` 파일을 작성 합니다. 이러한 `.proto` 파일을 사용 하 여 클라이언트 및 서버에 대 한 언어 또는 플랫폼별 스텁을 생성 하 여 여러 다른 플랫폼에서 통신할 수 있습니다. 팀은 `.proto` 파일을 공유 하 여 코드 종속성을 수행할 필요 없이 다른 사람의 서비스를 사용 하는 코드를 생성할 수 있습니다.

Protobuf IDL의 장점 중 하나는 사용자 지정 언어로, gRPC를 완전히 언어 및 플랫폼에 구애 받지 않고 다른 기술을 찾은 다음 수 없다는 것입니다.

Protobuf IDL은 읽기 및 쓰기를 위한 것 이지만, WSDL은 컴퓨터에서 읽을 수 있는/쓰기 가능한 형식으로 제공 됩니다. WCF 서비스의 WSDL을 변경 하려면 일반적으로 서비스를 변경 하 고 서비스를 실행 한 다음 서버에서 WSDL 파일을 다시 생성 해야 합니다. 이와 대조적으로, `.proto` 파일을 사용 하면 텍스트 편집기를 사용 하 여 변경 내용을 적용 하 고 생성 된 코드를 통해 자동으로 이동할 수 있습니다. Visual Studio 2019은 파일을 저장할 때 백그라운드에서 `.proto` 파일을 빌드합니다. VS Code와 같은 다른 편집기를 사용 하면 프로젝트를 빌드할 때 변경 내용이 적용 됩니다.

XML 및 특히 SOAP와 비교할 때 Protobuf를 사용 하 여 인코드된 메시지는 많은 이점이 있습니다. Protobuf 메시지는 SOAP XML로 serialize 된 데이터 보다 작고 네트워크를 통해 인코딩, 디코딩 및 전송 하는 것이 더 빠를 수 있습니다.

SOAP와 비교할 때 Protobuf의 잠재적인 단점은 메시지 콘텐츠를 디버그 하는 데 추가 도구가 필요 하기 때문입니다.

> [!TIP]
> gRPC *는* 미리 컴파일된 스텁을 사용 하지 않고 서비스에 동적으로 액세스 하는 서버 리플렉션을 지원 합니다. 단, 응용 프로그램 특정 클라이언트 보다 일반적인 용도의 도구를 사용 하는 것이 더 좋습니다. 자세한 내용은 GitHub의 [Grpc 서버 리플렉션 프로토콜](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md) 을 참조 하세요.

> [!NOTE]
> NetTCP 바인딩과 함께 사용 되는 WCF의 이진 형식은 시 압축 성 및 성능 측면에서 Protobuf에 훨씬 가깝습니다. 그러나 NetTCP는 .NET 클라이언트와 서버 사이 에서만 사용할 수 있지만 Protobuf는 플랫폼 간 솔루션입니다.

>[!div class="step-by-step"]
>[이전](approach.md)
>[다음](network-protocols.md)
