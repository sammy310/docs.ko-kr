---
title: GRPC가 WCF 개발자를 위한 RPC gRPC 접근 방법
description: WCF의 주요 기능을 gRPC와 비교 합니다.
ms.date: 09/02/2019
ms.openlocfilehash: 1ebfd102217c9685c5ff5200386c642b2017e98f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968125"
---
# <a name="how-grpc-approaches-rpc"></a>gRPC의 RPC 접근 방법

WCF (Windows Communication Foundation) 및 gRPC는 모두 다른 컴퓨터에서 실행 되는 서비스에 대 한 호출을 수행 하는 RPC ( *원격 프로시저 호출* ) 패턴의 구현 이거나, 다른 프로세스에서 클라이언트 응용 프로그램의 단순히 메서드 호출 처럼 원활 하 게 작동 합니다. WCF 및 gRPC의 목표는 동일 하지만 구현에 대 한 세부 정보는 상당히 다릅니다.

다음 표에서는 WCF의 주요 기능이 gRPC와 어떻게 관련 되어 있으며 책의 나머지 부분에서 더 자세한 설명을 찾을 수 있는 방법을 설명 합니다.

| 기능 | WCF | gRPC |
| -------- | --- | ---- |
| 목표 | 네트워킹 구현에서 비즈니스 코드 분리 | 인터페이스 정의 및 네트워킹 구현에서 비즈니스 코드 분리 |
| 서비스 및 메시지 정의 (3-4 장)  | 서비스 계약, 작업 계약 및 데이터 계약 | 프로토콜 파일을 사용 하 여 서비스 및 메시지 선언 |
| Language (3-5 장) | 또는로 C# 작성 된 계약 Visual Basic | 프로토콜 버퍼 언어 |
| 통신 형식 (3 장) | SOAP/XML, 일반 XML, JSON, .NET 이진 등을 비롯 한 구성 가능. | 프로토콜 버퍼 이진 형식 (다른 형식을 사용할 수 있지만).
| 상호 운용성 (4 장) | HTTP를 통해 SOAP를 사용 하는 경우 | 공식 지원: .NET, Java, Python, JavaScript, C/C++, Go, Rust, Ruby, Swift, DART, PHP. 커뮤니티의 다른 언어에 대 한 비공식 지원. |
| 네트워킹 (4 장) | 런타임에 구성 됩니다. NetTCP, HTTP, MSMQ 등을 전환 합니다. | HTTP/2 (현재는 ASP.NET Core gRPC만 TCP를 통해) |
| 접근 방식 (4 장) | 기본 클래스의 serialization/deserialization 및 네트워킹 코드의 런타임 생성 | 기본 클래스에서 직렬화/deserialization 및 네트워킹 코드의 빌드 시간 생성 |
| 보안 (6 장) | 인증, WS-SECURITY, 메시지 암호화 | 자격 증명, ASP.NET Core 보안, TLS 네트워킹 |

>[!div class="step-by-step"]
>[이전](grpc-overview.md)
>[다음](interface-definition-language.md)
