---
title: gRPC
description: GRPC, 클라우드 네이티브 응용 프로그램에서의 역할 및 HTTP RESTful 통신과 어떻게 다른 지에 대해 알아봅니다.
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 35a8325dd82e946d88b09b223287e2871be88ffa
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201329"
---
# <a name="grpc"></a>gRPC

지금까지이 책에서는 [REST 기반](https://docs.microsoft.com/azure/architecture/best-practices/api-design) 통신에 초점을 두었습니다. REST는 엔터티 리소스에 대해 CRUD 기반 작업을 정의 하는 유연한 아키텍처 스타일입니다. 클라이언트는 요청/응답 통신 모델을 사용 하 여 HTTP에서 리소스와 상호 작용 합니다. REST는 널리 구현 되는 반면, 최신 통신 기술인 gRPC는 클라우드 네이티브 커뮤니티에서 엄청난 모멘텀를 얻었습니다.

## <a name="what-is-grpc"></a>GRPC 란?

gRPC는 오래 된 [원격 프로시저 호출 (RPC)](https://en.wikipedia.org/wiki/Remote_procedure_call) 프로토콜을 진화 하는 현대적인 고성능 프레임 워크입니다. 응용 프로그램 수준에서 gRPC는 클라이언트와 백 엔드 서비스 간의 메시징을 간소화 합니다. Google에서 시작 하 여 gRPC는 오픈 소스 이며 클라우드 기본 제공의 [CNCF (Cloud Native 컴퓨팅 Foundation)](https://www.cncf.io/) 에코 시스템의 일부입니다. CNCF는 gRPC에 [incubating 프로젝트](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc)를 고려 합니다. Incubating은 최종 사용자가 프로덕션 응용 프로그램의 기술을 사용 하 고 있고 프로젝트에 참가자 수가 정상 임을 의미 합니다.

일반적인 gRPC 클라이언트 앱은 비즈니스 작업을 구현 하는 로컬 in-process 함수를 노출 합니다. 내부적으로 해당 로컬 함수는 원격 컴퓨터에서 다른 함수를 호출 합니다. 로컬 호출로 표시 되는 것은 기본적으로 원격 서비스에 대 한 out-of-process 호출로 인해 수행 됩니다. RPC는 지점 간 네트워킹 통신, serialization 및 컴퓨터 간의 실행을 추상화 합니다.

클라우드 네이티브 응용 프로그램에서 개발자는 종종 프로그래밍 언어, 프레임 워크 및 기술에 대해 작업을 수행 합니다. 이러한 *상호 운용성* 은 메시지 계약과 플랫폼 간 통신에 필요한 통로를 복잡 하 게 합니다.  gRPC는 이러한 문제를 추상화 하는 "균일 한 수평 계층"을 제공 합니다. 개발자는 기본 플랫폼의 비즈니스 기능에 초점을 맞춘 반면, gRPC는 통신 연결을 처리 합니다.

gRPC는 Java, JavaScript, c #, Go, Swift 및 NodeJS를 비롯 하 여 가장 인기 있는 개발 스택에 대 한 포괄적인 지원을 제공 합니다.

## <a name="grpc-benefits"></a>gRPC 혜택

gRPC는 해당 전송 프로토콜에 대해 HTTP/2를 사용 합니다. Http/2는 HTTP 1.1와 호환 되지만 다음과 같은 다양 한 고급 기능을 제공 합니다.

- 데이터 전송을 위한 이진 프로토콜-데이터를 일반 텍스트로 전송 하는 HTTP 1.1와는 다릅니다.
- 동일한 연결을 통해 여러 병렬 요청을 보내기 위한 멀티플렉싱 지원-HTTP 1.1는 한 번에 하나의 요청/응답 메시지로 처리를 제한 합니다.
- 클라이언트 요청과 서버 응답을 동시에 전송 하기 위한 양방향 전이중 통신입니다.
- 대량 데이터 집합을 비동기적으로 스트림 하는 요청 및 응답을 설정 하는 기본 제공 스트리밍입니다.

gRPC는 간단 하 고 성능이 높습니다. 메시지 60-80% 더 작게 JSON serialization 보다 최대 8 배 더 빠를 수 있습니다. Microsoft [Windows Communication Foundation (WCF)](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) 용어에서 grpc 성능은 매우 최적화 된 [nettcp 바인딩의](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8)속도와 효율성을 초과 합니다. Microsoft stack을 중심으로 하는 NetTCP와는 달리 gRPC는 플랫폼 간입니다.

## <a name="protocol-buffers"></a>프로토콜 버퍼

gRPC는 [프로토콜 버퍼](https://developers.google.com/protocol-buffers/docs/overview)라는 오픈 소스 기술을 채택 합니다. 서비스에서 서로 전송 하는 구조화 된 메시지를 serialize 하기 위한 매우 효율적이 고 플랫폼 중립적인 serialization 형식을 제공 합니다. 개발자는 크로스 플랫폼 IDL (인터페이스 정의 언어)을 사용 하 여 각 마이크로 서비스에 대 한 서비스 계약을 정의 합니다. 텍스트 기반 파일로 구현 되는 계약은 `.proto` 각 서비스의 메서드, 입력 및 출력을 설명 합니다. 동일한 계약 파일은 다양 한 개발 플랫폼에서 빌드된 gRPC 클라이언트 및 서비스에 사용할 수 있습니다.

Protobuf 컴파일러 인 프로토콜 파일을 사용 하 여 `protoc` 대상 플랫폼에 대 한 클라이언트와 서비스 코드를 모두 생성 합니다. 코드에는 다음 구성 요소가 포함 됩니다.

- 클라이언트 및 서비스에서 공유 하는 강력한 형식의 개체로, 메시지의 서비스 작업 및 데이터 요소를 나타냅니다.
- 원격 gRPC 서비스가 상속 하 고 확장할 수 있는 필수 네트워크를 사용 하는 강력한 형식의 기본 클래스입니다.
- 원격 gRPC 서비스를 호출 하는 데 필요한 통로를 포함 하는 클라이언트 스텁입니다.

런타임에 각 메시지는 표준 Protobuf 표현으로 직렬화 되 고 클라이언트와 원격 서비스 간에 교환 됩니다. JSON 또는 XML과 달리 Protobuf 메시지는 컴파일된 이진 바이트로 serialize 됩니다.

Microsoft 아키텍처 사이트에서 사용할 수 있는 [WCF 개발자를 위한 Grpc](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/)는 grpc와 프로토콜 버퍼에 대 한 심층적인 검사를 제공 합니다.

## <a name="grpc-support-in-net"></a>.NET의 gRPC 지원

gRPC는 .NET Core 3.0 SDK 이상에 통합 되어 있습니다. 지원 되는 도구는 다음과 같습니다.

- 웹 개발 워크 로드가 설치 된 Visual Studio 2019, 버전 16.3 이상
- Visual Studio Code
- dotnet CLI

SDK에는 끝점 라우팅, 기본 제공 IoC 및 로깅에 대 한 도구가 포함 되어 있습니다. 오픈 소스 Kestrel 웹 서버는 HTTP/2 연결을 지원 합니다. 그림 4-20에는 gRPC 서비스에 대 한 기본 프로젝트를 스 캐 폴드 Visual Studio 2019 템플릿이 나와 있습니다. .NET Core는 Windows, Linux 및 macOS를 완벽 하 게 지 원하는 방법에 유의 하세요.

![Visual Studio 2019의 gRPC 지원](./media/visual-studio-2019-grpc-template.png)

**그림 4-20**. Visual Studio 2019의 gRPC 지원
  
그림 4-21에는 Visual Studio 2019에 포함 된 기본 제공 스 캐 폴딩에서 생성 된 기본 gRPC 서비스가 나와 있습니다.  

![Visual Studio 2019의 gRPC 프로젝트](./media/grpc-project.png  )

**그림 4-21**. Visual Studio 2019의 gRPC 프로젝트

위의 그림에서 프로토콜 설명 파일 및 서비스 코드를 확인 합니다. 곧 볼 수 있듯이 Visual Studio는 시작 클래스와 기본 프로젝트 파일 모두에 추가 구성을 생성 합니다.

## <a name="grpc-usage"></a>gRPC 사용

다음 시나리오에서는 gRPC를 선호 합니다.

- 동기식 백 엔드 마이크로 서비스-마이크로 서비스 통신을 계속 하려면 즉각적인 응답이 필요 합니다.
- 혼합 프로그래밍 플랫폼을 지원 해야 하는 Polyglot 환경
- 성능이 중요 한 낮은 대기 시간 및 높은 처리량의 통신.
- 지점 간 실시간 통신-gRPC는 폴링을 사용 하지 않고 실시간으로 메시지를 푸시 하 고 양방향 스트리밍을 매우 잘 지원 합니다.
- 네트워크 제한 환경 – 이진 gRPC 메시지는 항상 동등한 텍스트 기반 JSON 메시지 보다 작습니다.

이 문서를 작성할 당시에는 gRPC가 백 엔드 서비스에서 주로 사용 됩니다. 대부분의 최신 브라우저는 프런트 엔드 gRPC 클라이언트를 지 원하는 데 필요한 HTTP/2 제어 수준을 제공할 수 없습니다. 즉, JavaScript 또는 Blazor Weasembom기술로 빌드된 브라우저 기반 앱에서 gRPC 통신을 가능 하 게 하는 [초기 이니셔티브](https://devblogs.microsoft.com/aspnet/grpc-web-experiment/) 가 있습니다. [.Net 용 grpc-웹](https://github.com/grpc/grpc/blob/master/doc/PROTOCOL-WEB.md) 을 사용 하면 ASP.NET Core grpc 앱이 브라우저 앱에서 grpc 기능을 지원할 수 있습니다.

- 강력 하 게 형식화 된 코드 생성 클라이언트
- Compact Protobuf 메시지
- 서버 스트리밍

## <a name="grpc-implementation"></a>gRPC 구현

Microsoft의 마이크로 서비스 참조 아키텍처 인 [컨테이너의 eShop](https://github.com/dotnet-architecture/eShopOnContainers)는 .net Core 응용 프로그램에서 grpc 서비스를 구현 하는 방법을 보여 줍니다. 그림 4-22에서는 백 엔드 아키텍처를 제공 합니다.

![컨테이너의 eShop 백 엔드 아키텍처](./media/eshop-with-aggregators.png)

**그림 4-22**. 컨테이너의 eShop 백 엔드 아키텍처

위의 그림에서 eShop 여러 API 게이트웨이를 노출 하 여 bff ( [프런트 엔드 패턴](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) )를 수용 하는 방법을 확인 합니다. 이 챕터의 앞부분에서 BFF 패턴에 대해 설명 했습니다. 웹 쇼핑 API 게이트웨이와 백 엔드 쇼핑 마이크로 서비스 사이에 있는 집계 마이크로 서비스 (회색)에 주의 하세요. 집계는 클라이언트에서 단일 요청을 수신 하 고, 다양 한 마이크로 서비스에 디스패치 하 고, 결과를 집계 하 고, 요청 클라이언트로 다시 보냅니다. 이러한 작업에는 일반적으로 즉각적인 응답을 생성 하기 위해 동기식 통신이 필요 합니다. EShop에서 집계의 백 엔드 호출은 그림 4-23에 표시 된 것 처럼 gRPC를 사용 하 여 수행 됩니다.

![컨테이너의 eShop의 gRPC](./media/grpc-implementation.png)

**그림 4-23** 컨테이너의 eShop의 gRPC

gRPC 통신에는 클라이언트 및 서버 구성 요소가 모두 필요 합니다. 위의 그림에서 쇼핑 집계가 gRPC 클라이언트를 구현 하는 방법을 확인 합니다. 클라이언트는 각에 gRPC 서버를 구현 하는 동기 gRPC 호출 (빨간색)을 백 엔드 마이크로 서비스에 만듭니다. 클라이언트와 서버 모두 .NET Core SDK에서 배관 된 기본 제공 gRPC를 활용 합니다. 클라이언트 쪽 *스텁은* 원격 grpc 호출을 호출 하는 통로를 제공 합니다. 서버 쪽 구성 요소는 사용자 지정 서비스 클래스가 상속 및 소비할 수 있는 gRPC 배관을 제공 합니다.

RESTful API 및 gRPC 통신을 모두 노출 하는 마이크로 서비스에는 트래픽을 관리 하는 여러 끝점이 필요 합니다. RESTful 호출 및 gRPC 호출에 대 한 HTTP 트래픽을 수신 대기 하는 끝점을 엽니다. Grpc 통신에 필요한 HTTP/2 프로토콜에 대해 gRPC 끝점을 구성 해야 합니다.

마이크로 서비스를 비동기 통신 패턴으로 분리 하려고 하지만 일부 작업은 직접 호출 해야 합니다. gRPC는 마이크로 서비스 간의 직접 동기식 통신을 위한 기본 선택 사항 이어야 합니다. HTTP/2 및 프로토콜 버퍼를 기준으로 하는 고성능 통신 프로토콜을 사용 하면 완벽 하 게 선택할 수 있습니다.

## <a name="looking-ahead"></a>미리 보기

잘 살펴보면, grpc는 클라우드 네이티브 시스템에 대해 트랙 션을 계속 해 서 얻습니다. 성능 이점과 개발의 용이성은 매우 강력 합니다. 그러나 REST는 오랜 시간 동안 발생할 수 있습니다. 공개적으로 노출 된 Api 및 이전 버전과의 호환성을 위해 뛰어나지만.

>[!div class="step-by-step"]
>[이전](service-to-service-communication.md)
>[다음](service-mesh-communication-infrastructure.md)
