---
title: REST 및 gRPC
description: GRPC, 클라우드 네이티브 응용 프로그램에서의 역할 및 HTTP REST와의 차이점에 대해 알아봅니다.
author: robvet
ms.date: 09/08/2019
ms.openlocfilehash: 4c829407d494a3529d1fb9953cd3f56f73e90636
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711638"
---
# <a name="rest-and-grpc"></a>REST 및 gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

지금까지이 책에서는 [REST 기반](https://docs.microsoft.com/azure/architecture/best-practices/api-design) 통신에 초점을 두었습니다. REST는 분산 컴퓨터 시스템 간의 상호 운용성을 촉진 하는 아키텍처 스타일입니다. 서버의 모든 응답이 클라이언트의 요청에 대 한 요청/응답 모델을 사용 합니다. 널리 사용 되는 반면 나머지는 모든 문제에 적합 하지는 않습니다. 최신 통신 기술인 gRPC는 인기 있는 환경을 빠르게 활용 하 고 클라우드 기본 환경을 활용 합니다.

## <a name="grpc"></a>gRPC

gRPC는 Google에서 시작 하는 오픈 소스 통신입니다. 분산 컴퓨팅에서 널리 사용 되는 [RPC (원격 프로시저 호출)](https://en.wikipedia.org/wiki/Remote_procedure_call) 모델을 기반으로 합니다. 이 모델을 따라 로컬 클라이언트 프로그램은 작업을 실행 하는 in-process 메서드를 노출 합니다. 내부적으로이 호출은 분산 네트워크를 통해 out-of-process 마이크로 서비스에서 호출 됩니다. 개발자는 작업을 로컬 프로시저 호출로 코딩 합니다. 기본 플랫폼은 지점 및 지점 네트워킹 통신, serialization 및 실행을 추상화 합니다.

gRPC는 간단 하 고 성능이 뛰어난 최신 RPC 프레임 워크입니다. 전송 프로토콜에 대해 HTTP/2를 사용 합니다. Http/2는 HTTP 1.1와 호환 되지만 다음과 같은 다양 한 고급 기능을 제공 합니다.

- HTTP 1.1는 데이터를 일반 텍스트로 전송 하지만, HTTP/2는 이진 프로토콜입니다. 더 작은 메모리를 사용 하 여 데이터를 더 빠르게 구문 분석 하 고, 성능 향상을 위해 네트워크 대기 시간을 줄이고, 네트워크 리소스를 보다 효율적으로 관리 합니다.
- HTTP 1.1은 한 번에 하나의 왕복 요청/응답을 처리 하는 것으로 제한 되지만, h t t p/2는 동일한 연결을 통해 멀티플렉싱 또는 여러 병렬 요청을 지원 합니다.
- H t t p/2는 클라이언트와 서버가 동시에 통신할 수 있는 전이중 또는 양방향 통신을 지원 합니다. 클라이언트는 서버에서 응답 데이터를 다시 보낼 때 동시에 요청 데이터를 업로드할 수 있습니다.
- 스트리밍은 HTTP/2로 기본 설정 됩니다. 즉, 요청 및 응답이 모두 대량 데이터 집합을 비동기적으로 스트리밍할 수 있습니다.
- GRPC와 HTTP/2를 결합 하면 성능이 크게 향상 됩니다. [Windows Communication Foundation (WCF)](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) 용어에서 grpc 성능은 [nettcp 바인딩의](https://docs.microsoft.com/dotnet/api/system.servicemodel.nettcpbinding?view=netframework-4.8)속도와 효율성을 충족 하 고 초과 합니다. 그러나 NetTCP와 달리 gRPC는 C# 또는 Visual Basic 같은 Microsoft 언어로 제한 되지 않습니다.

gRPC는 Java, C#, Golang 및 nodejs를 비롯 한 가장 인기 있는 플랫폼에서 지원 됩니다.

## <a name="protocol-buffers"></a>프로토콜 버퍼

gRPC는 [프로토콜 버퍼](https://developers.google.com/protocol-buffers/docs/overview) 또는 Protobuf 메시지 라는 다른 오픈 소스 기술을 채택 하 여 데이터를 보내고 받습니다. [WCF 데이터 계약과](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-data-contracts)마찬가지로 Protobuf는 시스템에서 읽고 쓰도록 구조화 된 데이터를 serialize 합니다. 사용자가 읽을 수 있는 형식 (예: XML 또는 JSON)이 발생 하는 오버 헤드를 줄입니다.

많은 개체 serialization 기술은 런타임에 데이터 개체의 구조 전체를 반영 합니다. Protobuf를 사용 하려면 플랫폼에 상관 없는 언어 (프로토콜 버퍼 언어)를 사용 하 여 구조를 앞에 정의 해야 합니다. 각 정의는 ". proto" 파일에 저장 됩니다. 그런 다음 Protobuf 컴파일러, "Proton"를 사용 하 여 지원 되는 플랫폼에 대 한 클라이언트 및 서버 코드를 생성 합니다. 생성 된 코드는 데이터의 빠른 직렬화/deserialization을 위해 최적화 됩니다. 런타임에 각 메시지는 강력한 형식의 서비스 계약에 래핑되어 표준 Protobuf 표현으로 serialize 됩니다.

## <a name="grpc-support-in-net"></a>.NET의 gRPC 지원

Microsoft .NET Core framework 3.0에는 gRPC에 대 한 도구 및 기본 지원이 포함 되어 있습니다. 그림 4-20에는 gRPC 서비스를 위한 gRPC 기본 프로젝트를 스 캐 폴드 하는 Visual Studio 2019 템플릿이 나와 있습니다. .NET Core는 Windows, Linux 및 macOS 플랫폼을 지 원하는 방법을 확인 합니다.

![Visual Studio 2019의 gRPC 지원](./media/visual-studio-2019-grpc-template.png)

**그림 4-20**. Visual Studio 2019의 gRPC 지원

.NET Core 3.0는 끝점 라우팅, 기본 제공 IoC 지원 및 로깅을 포함 하 여 gRPC를 프레임 워크에 원활 하 게 통합 합니다. 오픈 소스 Kestrel 웹 서버는 HTTP/2 연결을 완벽 하 게 지원 합니다.

그림 4-21에는 Visual Studio 2019의 gRPC 서비스 구조가 나와 있습니다. 폴더 구조에는 프로토콜 파일 및 서비스 코드에 대 한 폴더가 포함 되어 있습니다.

![Visual Studio 2019의 gRPC 프로젝트](./media/grpc-project.png  )

**그림 4-21**. Visual Studio 2019의 gRPC 프로젝트

## <a name="grpc-usage"></a>gRPC 사용

gRPC는 다음과 같은 시나리오에 적합 합니다.

- 짧은 대기 시간 및 높은 처리량의 통신. gRPC는 효율성이 중요 한 경량 마이크로 서비스에 적합 합니다.
- 지점 간 실시간 통신. gRPC는 양방향 스트리밍을 위한 뛰어난 지원 기능을 제공 합니다. gRPC 서비스는 폴링을 사용 하지 않고 실시간으로 메시지를 푸시할 수 있습니다.
- Polyglot 환경 – gRPC 도구는 널리 사용 되는 개발 언어를 지원 하므로 다국어 환경에 적합 합니다.
- 네트워크 제한 환경 – gRPC 메시지는 경량 메시지 형식인 Protobuf를 사용 하 여 직렬화 됩니다. GRPC 메시지는 항상 해당 하는 JSON 메시지 보다 작습니다.

이 책을 작성할 당시 대부분의 브라우저에서 gRPC를 제한적으로 지원 합니다. gRPC는 HTTP/2 기능을 많이 사용 하며, 브라우저에서 gRPC 클라이언트를 지원 하기 위해 웹 요청에 필요한 제어 수준을 제공 하지 않습니다. gRPC는 일반적으로 내부 마이크로 서비스에서 통신을 마이크로 서비스 하는 데 사용 됩니다. 그림 4-22에서는 단순 하지만 일반적인 사용 패턴을 보여 줍니다.

![gRPC 사용 패턴](./media/grpc-usage.png)

**그림 4-22**. gRPC 사용 패턴

위의 그림에서는 프런트 엔드 트래픽이 HTTP를 사용 하 여 호출 되는 방법에 대해 설명 합니다. 단, 백 엔드 마이크로 서비스 마이크로 서비스에는 gRPC가 사용 됩니다.

잘 살펴보면, gRPC는 클라우드 네이티브 시스템에 대해 REST의 우위를 dethroning에서 주요 역할을 할 수 있습니다. 성능 이점과 개발의 용이성은 너무 양호 합니다. 그러나 실수를 하지 마십시오. 나머지는 오랜 시간 동안 계속 해 서 해결 됩니다. 공개적으로 노출 된 Api 및 이전 버전과의 호환성을 위해 계속 뛰어나지만.

>[!div class="step-by-step"]
>[이전](service-to-service-communication.md)
>[다음](service-mesh-communication-infrastructure.md)
