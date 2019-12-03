---
title: GRPC가 WCF 개발자를 위한 RPC gRPC 접근 방법
description: WCF의 주요 기능을 gRPC와 비교 합니다.
ms.date: 09/02/2019
ms.openlocfilehash: b924d2f20b54de2d6476a0b27626d5dd7fd0986f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711488"
---
# <a name="how-grpc-approaches-rpc"></a>gRPC의 RPC 접근 방법

WCF (Windows Communication Foundation) 및 gRPC는 모두 RPC ( *원격 프로시저 호출* ) 패턴의 구현입니다. 이 패턴은 다른 컴퓨터에서 실행 되거나 다른 프로세스에서 실행 되는 서비스에 대 한 호출을 목표로 클라이언트 응용 프로그램의 메서드 호출과 같이 원활 하 게 작동 합니다. WCF 및 gRPC의 목표는 동일 하지만 구현에 대 한 세부 정보는 상당히 다릅니다.

다음 표에서는 WCF의 주요 기능이 gRPC와 어떻게 관련 되어 있는지를 설명 하 고 자세한 설명을 확인할 수 있습니다.

| 기능 | WCF | gRPC |
| -------- | --- | ---- |
| 목표 | 네트워킹 구현에서 비즈니스 코드를 분리 합니다. | 인터페이스 정의 및 네트워킹 구현에서 비즈니스 코드를 분리 합니다. |
| 서비스 및 메시지 정의 (3-4 장)  | 서비스 계약, 작업 계약 및 데이터 계약입니다. | 는 프로토콜 파일을 사용 하 여 서비스와 메시지를 선언 합니다. |
| Language (3-5 장) | 또는 Visual Basic에서 C# 작성 한 계약입니다. | 프로토콜 버퍼 언어입니다. |
| 통신 형식 (3 장) | SOAP/XML, 일반 XML, JSON 및 .NET 이진을 포함 하 여 구성할 수 있습니다. | 프로토콜 버퍼 이진 형식 (다른 형식을 사용할 수 있지만).
| 상호 운용성 (4 장) | HTTP를 통해 SOAP를 사용 하는 경우. | 공식 지원: .NET, Java, Python, JavaScript, C/C++, Go, Rust, Ruby, Swift, DART, PHP. 커뮤니티의 다른 언어에 대 한 비공식 지원. |
| 네트워킹 (4 장) | 런타임에 구성 됩니다. NetTCP, HTTP 및 MSMQ 사이를 전환 합니다. | HTTP/2 (현재는 ASP.NET Core gRPC만 TCP를 통해) |
| 접근 방식 (4 장) | 기본 클래스에서 serialization, deserialization 및 네트워킹 코드의 런타임 생성 | 기본 클래스에서 serialization, deserialization 및 네트워킹 코드의 빌드 시간 생성 |
| 보안 (6 장) | 인증, WS-SECURITY, 메시지 암호화가 있습니다. | 자격 증명, ASP.NET Core 보안, TLS 네트워킹. |

>[!div class="step-by-step"]
>[이전](grpc-overview.md)
>[다음](interface-definition-language.md)
