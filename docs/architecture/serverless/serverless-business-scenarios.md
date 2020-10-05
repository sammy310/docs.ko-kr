---
title: 서버리스 앱 샘플 비즈니스 시나리오 및 사용 사례
description: 이미지 처리에서 모바일 지원 및 ETL 파이프라인까지 다양한 샘플에 액세스하여 실습 방식으로 서버리스에 대해 알아봅니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/17/2020
ms.openlocfilehash: df76b132579eb3a6d05ce38c94cb9fceb9281aef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171613"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>서버리스 비즈니스 시나리오 및 사용 사례

서버리스 애플리케이션에는 다양한 사용 사례 및 시나리오가 있습니다. 이 장에서는 다양한 시나리오를 예시하는 샘플을 제공합니다. 시나리오에는 관련 설명서 및 공개 소스 코드 리포지토리에 대한 링크가 포함되어 있습니다. 이 장의 샘플을 사용하여 서버리스 솔루션을 직접 빌드하고 구현할 수 있습니다.

## <a name="big-data-processing"></a>빅 데이터 처리

![Map/reduce 다이어그램](/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/media/mapreducearchitecture.png)

이 예제에서는 서버리스를 사용하여 빅 데이터 세트에서 map/reduce 작업을 수행합니다. 2017년에서 일별 뉴욕 노란색 택시 트립의 평균 속도를 결정합니다.

[빅 데이터 처리: Azure에서 서버리스 MapReduce](/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)

## <a name="create-serverless-applications-hands-on-lab"></a>서버리스 애플리케이션 만들기: 실습 랩

함수를 사용하여 서버 쪽 논리를 실행하고 서버리스 아키텍처를 빌드하는 방법을 알아봅니다.

- 비즈니스에 가장 적합한 Azure 서비스 선택
- Azure Functions 만들기
- 트리거 사용
- 체이닝 함수
- 장기 실행 워크플로
- 모니터링
- 개발, 테스트 및 배포

[서버리스 애플리케이션 만들기](/learn/paths/create-serverless-applications/)

## <a name="customer-reviews"></a>고객 리뷰

이 샘플에서는 Visual Studio의 C# 클래스 라이브러리에 대한 새로운 Azure Functions 도구를 소개합니다. 고객이 Azure 스토리지 Blob 및 CosmosDB에 저장된 제품 검토를 제출하는 웹 사이트를 만듭니다. Azure Cognitive Services를 사용하여 고객 리뷰의 자동화된 중재를 수행하는 Azure 함수를 추가합니다. Azure 스토리지 큐를 사용하여 기능에서 웹 사이트를 분리합니다.

[Cognitive Services로 고객 리뷰 앱](/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)

## <a name="docker-linux-image-support"></a>Docker Linux 이미지 지원

이 샘플은 Linux Docker 컨테이너에서 Azure Functions를 빌드하고 실행하는 `Dockerfile`을 만드는 방법을 보여 줍니다.

[Linux에서 Azure Functions](/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)

## <a name="file-processing-and-validation"></a>파일 처리 및 유효성 검사

이 예제에서는 가상 고객의 CSV 파일 세트를 구문 분석합니다. 고객 "일괄 처리"에 필요한 모든 파일이 준비되었는지 확인한 다음, 각 파일 구조의 유효성을 검사합니다. Azure Functions, Logic Apps 및 Durable Functions를 사용하여 다양한 솔루션이 제공됩니다.

[Azure Functions, Logic Apps 및 Durable Functions를 사용하여 파일 처리 및 유효성 검사](/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)

## <a name="game-data-visualization"></a>게임 데이터 시각화

![게임 원격 분석](/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/media/points.png)

개발자가 게임에 대한 편집기 내 데이터 시각화 솔루션을 구현하는 방법의 예제입니다. 실제로 이 샘플을 백 엔드로 사용하여 Unreal Engine 4 플러그 인 및 Unity 플러그 인을 개발했습니다. 서비스 구성 요소는 게임 엔진에 독립적입니다.

[편집기 내 게임 원격 분석 시각화](/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)

## <a name="graphql"></a>GraphQL

GraphQL API를 노출하는 서버리스 함수를 만듭니다.

[GraphQL에 대한 서버리스 함수](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)

## <a name="internet-of-things-iot-reliable-edge-relay"></a>IoT(사물 인터넷) 안정적인 에지 릴레이

![IoT 아키텍처](/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/media/architecture.png)

이 샘플은 IoT 디바이스에서 안정적인 업스트림 통신을 가능하게 하는 새로운 통신 프로토콜을 구현합니다. 데이터 갭 검색 및 백필을 자동화합니다.

[IoT 안정적인 에지 릴레이](/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)

## <a name="microservices-reference-architecture"></a>마이크로서비스 참조 아키텍처

![참조 아키텍처](/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/media/macro-architecture.png)

가상 회사인 Relecloud 애플리케이션을 통해 Rideshare를 디자인, 개발 및 제공하는 것과 관련된 의사 결정 과정을 안내하는 참조 아키텍처입니다. 여기에는 모든 아키텍처의 구성 요소를 구성하고 배포하기 위한 실습 지침이 포함되어 있습니다.

[서버리스 마이크로서비스 참조 아키텍처](/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

## <a name="migrate-console-apps-to-serverless"></a>서버리스로 콘솔 앱 마이그레이션

이 샘플은 Azure Functions의 모든 콘솔 애플리케이션을 HTTP 웹 서비스로 변환하는 데 사용할 수 있는 제네릭 함수(`.csx` 파일)입니다. 구성 파일을 편집하고 인수로 `.exe`에 전달되는 입력 매개 변수를 지정하면 됩니다.

[Azure Functions에서 콘솔 앱 실행](/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)

## <a name="serverless-for-mobile"></a>모바일에 대한 서버리스

Azure Functions는 쉽게 구현하고 유지 관리할 수 있으며 HTTP를 통해 액세스할 수 있습니다. 모바일 애플리케이션에 대한 API를 구현하는 좋은 방법입니다. Microsoft는 Xamarin을 사용하여 iOS, Android 및 Windows용 플랫폼 간 도구를 제공합니다. 따라서 Xamarin 및 Azure Functions는 함께 잘 작동합니다. 이 문서에서는 먼저 Azure Portal 또는 Visual Studio에서 Azure 함수를 구현하고, Android, iOS 및 Windows에서 실행되는 Xamarin.Forms를 사용하여 플랫폼 간 클라이언트를 빌드하는 방법을 보여 줍니다.

[Xamarin.Forms 클라이언트를 사용하여 간단한 Azure Function 구현](/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)

## <a name="serverless-messaging"></a>서버리스 메시징

이 샘플에서는 Durable Functions의 팬 아웃 패턴을 활용하여 원하는 수의 세션/파티션에 걸쳐 임의 개수의 메시지를 로드하는 방법을 보여 줍니다. Service Bus, Event Hubs 또는 Storage 큐를 대상으로 합니다. 또한 이 샘플에서는 다른 Azure 함수를 사용하여 이러한 메시지를 사용하는 기능을 추가하고 결과 타이밍 데이터를 다른 이벤트 허브에 로드합니다. 그런 다음, 데이터는 Azure Data Explorer와 같은 분석 서비스로 수집됩니다.

[Azure Functions를 사용하여 Service Bus, Event Hubs 및 Storage 큐를 통해 메시지 생성 및 사용](/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)

## <a name="recommended-resources"></a>권장되는 리소스

- [Linux에서 Azure Functions](/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)
- [빅 데이터 처리: Azure에서 서버리스 MapReduce](/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)
- [서버리스 애플리케이션 만들기](/learn/paths/create-serverless-applications/)
- [Cognitive Services로 고객 리뷰 앱](/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)
- [Azure Functions, Logic Apps 및 Durable Functions를 사용하여 파일 처리 및 유효성 검사](/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)
- [Xamarin.Forms 클라이언트를 사용하여 간단한 Azure Function 구현](/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)
- [편집기 내 게임 원격 분석 시각화](/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)
- [IoT 안정적인 에지 릴레이](/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)
- [Azure Functions를 사용하여 Service Bus, Event Hubs 및 Storage 큐를 통해 메시지 생성 및 사용](/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)
- [Azure Functions에서 콘솔 앱 실행](/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)
- [GraphQL에 대한 서버리스 함수](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)
- [서버리스 마이크로서비스 참조 아키텍처](/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

>[!div class="step-by-step"]
>[이전](orchestration-patterns.md)
>[다음](serverless-conclusion.md)
