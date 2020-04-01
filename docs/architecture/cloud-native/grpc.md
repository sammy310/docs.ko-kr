---
title: gRPC
description: gRPC, 클라우드 네이티브 응용 프로그램에서의 역할 및 HTTP RESTful 통신과 어떻게 다른지 알아봅니다.
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 28a07ad5ec105d3fc5b65e4cf0ac0cd85eb16627
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2020
ms.locfileid: "80524210"
---
# <a name="grpc"></a>gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

지금까지 이 책에서는 [REST 기반](https://docs.microsoft.com/azure/architecture/best-practices/api-design) 커뮤니케이션에 중점을 두어 왔습니다. REST는 엔터티 리소스에 대해 CRUD 기반 작업을 정의하는 유연한 아키텍처 스타일임을 알 수 있습니다. 클라이언트는 요청/응답 통신 모델과 HTTP 전체의 리소스와 상호 작용합니다. REST가 널리 구현되는 동안, 새로운 통신 기술, gRPC는 클라우드 네이티브 커뮤니티전반에 걸쳐 엄청난 추진력을 얻고 있다.

## <a name="what-is-grpc"></a>gRPC란 무엇입니까?

gRPC는 오래된 [RPC(원격 프로시저 호출)](https://en.wikipedia.org/wiki/Remote_procedure_call) 프로토콜을 발전시키는 최신 고성능 프레임워크입니다. 응용 프로그램 수준에서 gRPC는 클라이언트와 백 엔드 서비스 간의 메시징을 간소화합니다. 구글에서 유래한 gRPC는 오픈 소스이며 클라우드 네이티브 오퍼링의 [CNCF(클라우드 네이티브 컴퓨팅 재단)](https://www.cncf.io/) 생태계의 일부입니다. CNCF는 gRPC를 [인큐베이팅 프로젝트로 간주합니다.](https://github.com/cncf/toc/blob/master/process/graduation_criteria.adoc) 인큐베이팅은 최종 사용자가 프로덕션 응용 프로그램에서 기술을 사용하고 있으며 프로젝트에는 건강한 수의 기여자가 있음을 의미합니다.

일반적인 gRPC 클라이언트 앱은 비즈니스 작업을 구현하는 로컬 프로세스 내 함수를 노출합니다. 커버 아래에서 해당 로컬 함수는 원격 컴퓨터에서 다른 함수를 호출합니다. 로컬 호출로 보이는 것은 기본적으로 원격 서비스에 대한 투명한 프로세스 외 호출이 됩니다. RPC 배관은 컴퓨터 간의 지점 간 네트워킹 통신, 직렬화 및 실행을 추상화합니다.

클라우드 네이티브 응용 프로그램에서 개발자는 프로그래밍 언어, 프레임워크 및 기술 에서 작업하는 경우가 많습니다. 이러한 *상호 운용성은* 메시지 계약과 플랫폼 간 통신에 필요한 배관을 복잡하게 만듭니다.  gRPC는 이러한 문제를 추상화하는 "균일한 수평 레이어"를 제공합니다. 개발자는 기본 플랫폼의 코드로 비즈니스 기능에 중점을 두고 gRPC는 통신 배관을 처리합니다.

gRPC는 Java, JavaScript, C#, Go, Swift 및 NodeJS를 포함하여 가장 인기 있는 개발 스택에서 포괄적인 지원을 제공합니다.

## <a name="grpc-benefits"></a>gRPC 혜택

gRPC는 전송 프로토콜에 HTTP/2를 사용합니다. HTTP 1.1과 호환되는 동안 HTTP/2에는 다음과 같은 많은 고급 기능이 있습니다.

- 데이터를 일반 텍스트로 전송하는 HTTP 1.1과 달리 데이터 전송을 위한 이진 프로토콜입니다.
- 동일한 연결을 통해 여러 병렬 요청을 전송하기 위한 다중 화 지원 - HTTP 1.1은 한 번에 하나의 요청/응답 메시지로 처리를 제한합니다.
- 클라이언트 요청과 서버 응답을 동시에 전송하기 위한 양방향 전이중 통신.
- 기본 제공 스트리밍을 통해 대용량 데이터 세트를 비동기적으로 스트리밍하는 요청 및 응답을 지원합니다.

gRPC는 가볍고 성능이 우수합니다. 60~80% 더 작은 메시지로 JSON 직렬화보다 최대 8배 더 빠를 수 있습니다. 마이크로소프트 [윈도 커뮤니케이션 재단 (WCF)](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) 말에서, gRPC 성능 속도 및 고도로 최적화 된 [NetTCP 바인딩의](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8)효율성을 초과 . 마이크로소프트 스택을 선호하는 NetTCP와 달리 gRPC는 크로스 플랫폼입니다.

## <a name="protocol-buffers"></a>프로토콜 버퍼

gRPC는 프로토콜 버퍼라는 오픈 소스 기술을 [수용합니다.](https://developers.google.com/protocol-buffers/docs/overview) 서비스가 서로 보내는 구조화 된 메시지를 직렬화하기 위한 매우 효율적이고 플랫폼 중립적인 직렬화 형식을 제공합니다. 개발자는 플랫폼 간 인터페이스 정의 언어(IDL)를 사용하여 각 마이크로 서비스에 대한 서비스 계약을 정의합니다. 텍스트 기반 `.proto` 파일로 구현된 계약은 각 서비스에 대한 메서드, 입력 및 출력을 설명합니다. 동일한 계약 파일을 다른 개발 플랫폼에 구축된 gRPC 클라이언트 및 서비스에 사용할 수 있습니다.

프로토 파일인 Protobuf 컴파일러를 `protoc`사용하여 대상 플랫폼에 대한 클라이언트 및 서비스 코드를 모두 생성합니다. 코드에는 다음 구성 요소가 포함됩니다.

- 메시지에 대한 서비스 작업 및 데이터 요소를 나타내는 클라이언트 및 서비스에서 공유하는 강력한 형식의 개체입니다.
- 원격 gRPC 서비스가 상속하고 확장할 수 있는 필수 네트워크 배관이 있는 강력한 형식의 기본 클래스입니다.
- 원격 gRPC 서비스를 호출하는 데 필요한 배관이 포함된 클라이언트 스텁입니다.

런타임시 각 메시지는 표준 Protobuf 표현으로 직렬화되고 클라이언트와 원격 서비스 간에 교환됩니다. JSON 또는 XML과 달리 Protobuf 메시지는 컴파일된 이진 바이트로 직렬화됩니다.

Microsoft 아키텍처 사이트에서 사용할 수 있는 [WCF 개발자를 위한 gRPC](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/)책에서는 gRPC 및 프로토콜 버퍼에 대한 심층적인 커버리지를 제공합니다.

## <a name="grpc-support-in-net"></a>.NET에서 gRPC 지원

gRPC는 .NET 코어 3.0 SDK 이상에 통합됩니다. 다음 도구는 이를 지원합니다.

- 웹 개발 워크로드가 설치된 Visual Studio 2019 버전 16.3 이상입니다.
- Visual Studio Code
- 도트넷 CLI

SDK에는 엔드포인트 라우팅, 기본 제공 IoC 및 로깅을 위한 툴링이 포함되어 있습니다. 오픈 소스 Kestrel 웹 서버는 HTTP/2 연결을 지원합니다. 그림 4-20은 gRPC 서비스에 대한 스켈레톤 프로젝트를 스캐폴드하는 Visual Studio 2019 템플릿을 보여 주었습니다. .NET Core가 Windows, Linux 및 macOS를 완전히 지원하는 방법을 확인합니다.

![비주얼 스튜디오 2019에서 gRPC 지원](./media/visual-studio-2019-grpc-template.png)

**그림 4-20**. 비주얼 스튜디오 2019에서 gRPC 지원
  
그림 4-21은 Visual Studio 2019에 포함된 내장 스캐폴딩으로부터 생성된 스켈레톤 gRPC 서비스를 보여 주었습니다.  

![비주얼 스튜디오 2019의 gRPC 프로젝트](./media/grpc-project.png  )

**그림 4-21**. 비주얼 스튜디오 2019의 gRPC 프로젝트

이전 그림에서 프로토 설명 파일 및 서비스 코드를 기록합니다. 곧 보시다시피 Visual Studio는 시작 클래스와 기본 프로젝트 파일 모두에서 추가 구성을 생성합니다.

## <a name="grpc-usage"></a>gRPC 사용량

다음 시나리오에 대 한 gRPC를 선호 합니다.

- 처리를 계속하려면 즉각적인 응답이 필요한 동기 백엔드 마이크로 서비스-마이크로 서비스 통신입니다.
- 혼합 프로그래밍 플랫폼을 지원해야 하는 수개 국어 환경입니다.
- 성능이 중요한 낮은 대기 시간 및 높은 처리량 통신.
- 지점 간 실시간 통신 - gRPC는 폴링 없이 실시간으로 메시지를 푸시할 수 있으며 양방향 스트리밍을 지원합니다.
- 네트워크 제한 환경 - 이진 gRPC 메시지는 항상 동등한 텍스트 기반 JSON 메시지보다 작습니다.

당시, 이 글의 gRPC는 주로 백 엔드 서비스와 함께 사용됩니다. 대부분의 최신 브라우저는 프런트 엔드 gRPC 클라이언트를 지원하는 데 필요한 HTTP/2 컨트롤 수준을 제공할 수 없습니다. 즉, 자바 스크립트 또는 Blazor 웹 어셈블리 기술로 구축 된 브라우저 기반 앱에서 gRPC 통신을 가능하게하는 [초기 이니셔티브가](https://devblogs.microsoft.com/aspnet/grpc-web-experiment/) 있습니다. [.NET용 gRPC-Web을](https://github.com/grpc/grpc/blob/master/doc/PROTOCOL-WEB.md) 사용하면 ASP.NET 코어 gRPC 앱이 브라우저 앱에서 gRPC 기능을 지원할 수 있습니다.

- 강력한 형식의 코드 생성 클라이언트
- 소형 프로토부프 메시지
- 서버 스트리밍

## <a name="grpc-implementation"></a>gRPC 구현

마이크로 서비스 참조 아키텍처인 [eShop on Containers는](https://github.com/dotnet-architecture/eShopOnContainers).NET Core 응용 프로그램에서 gRPC 서비스를 구현하는 방법을 보여 주며, 그림 4-22는 백 엔드 아키텍처를 제시합니다.

![컨테이너에 eShop을 위한 백 엔드 아키텍처](./media/eshop-with-aggregators.png)

**그림 4-22**. 컨테이너에 eShop을 위한 백 엔드 아키텍처

이전 그림에서 eShop이 여러 API 게이트웨이를 노출하여 [프런트 엔드 패턴(BFF)에 대한 백 엔드를](https://docs.microsoft.com/azure/architecture/patterns/backends-for-frontends) 수용하는 방법을 알아두십시오. 이 장의 앞에서 BFF 패턴에 대해 설명했습니다. 웹 쇼핑 API 게이트웨이와 백 엔드 쇼핑 마이크로 서비스 사이에 있는 애그리게이터 마이크로 서비스(회색)에 주의하십시오. Aggregator는 클라이언트로부터 단일 요청을 수신하고, 다양한 마이크로 서비스로 디스패치하고, 결과를 집계한 다음, 요청 클라이언트로 다시 보냅니다. 이러한 작업에는 일반적으로 즉각적인 응답을 생성하기 위해 동기 통신이 필요합니다. eShop에서는 그림 4-23과 같이 gRPC를 사용하여 애그리게이터의 백엔드 호출이 수행됩니다.

![컨테이너에 eShop에서 gRPC](./media/grpc-implementation.png)

**그림 4-23** 컨테이너에 eShop에서 gRPC

gRPC 통신에는 클라이언트와 서버 구성 요소가 모두 필요합니다. 이전 그림에서는 쇼핑 애그리게이터가 gRPC 클라이언트를 구현하는 방법을 알아두고 있습니다. 클라이언트는 각각 gRPC 서버를 구현하는 백엔드 마이크로 서비스에 동기 gRPC 호출(빨간색)을 만듭니다. 클라이언트와 서버 모두 .NET Core 3.0 SDK의 기본 제공 gRPC 배관을 활용합니다. 클라이언트 측 *스텁은* 원격 gRPC 호출을 호출하는 배관을 제공합니다. 서버 측 구성 요소는 사용자 지정 서비스 클래스가 상속하고 사용할 수 있는 gRPC 배관을 제공합니다.

RESTful API와 gRPC 통신을 모두 노출하는 마이크로 서비스는 트래픽을 관리하기 위해 여러 개의 끝점이 필요합니다. RESTful 호출에 대한 HTTP 트래픽을 수신하는 끝점과 gRPC 호출에 대해 다른 끝점을 엽니다. gRPC 통신에 필요한 HTTP/2 프로토콜에 대해 gRPC 끝점을 구성해야 합니다.

마이크로 서비스를 비동기 통신 패턴으로 분리하려고 노력하지만 일부 작업에는 직접 호출이 필요합니다. gRPC는 마이크로 서비스 간의 직접 동기 통신을 위한 기본 선택이어야 합니다. HTTP/2 및 프로토콜 버퍼를 기반으로 하는 고성능 통신 프로토콜은 완벽한 선택입니다.

## <a name="looking-ahead"></a>앞을 내다보며

앞으로 gRPC는 클라우드 네이티브 시스템에 대한 견인력을 계속 얻을 것입니다. 성능 이점과 개발 용이성은 매력적입니다. 그러나 REST는 오랫동안 주변에 있을 가능성이 높습니다. 공개적으로 노출된 API와 이전 버전과의 호환성을 위해 탁월합니다.

>[!div class="step-by-step"]
>[이전](service-to-service-communication.md)
>[다음](service-mesh-communication-infrastructure.md)
