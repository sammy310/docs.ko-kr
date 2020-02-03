---
title: 서버리스 앱 샘플 비즈니스 시나리오 및 사용 사례
description: 이미지 처리에서 모바일 백 엔드 및 ETL 파이프라인까지 다양한 샘플에 액세스하여 실습 방식으로 서버리스에 대해 알아봅니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5f0d7a4c5cd736d1168ec76c1c0ea19627505f15
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787888"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>서버리스 비즈니스 시나리오 및 사용 사례

서버리스 애플리케이션에는 다양한 사용 사례 및 시나리오가 있습니다. 이 장에서는 다양한 시나리오를 예시하는 샘플을 제공합니다. 시나리오에는 관련 설명서 및 공개 소스 코드 리포지토리에 대한 링크가 포함되어 있습니다. 이 장의 샘플을 사용하여 서버리스 솔루션을 직접 빌드하고 구현할 수 있습니다.

## <a name="analyze-and-archive-images"></a>이미지 분석 및 보관

이 샘플에서는 서버리스 이벤트(Event Grid), 워크플로(Logic App) 및 코드(Azure Functions)를 시연합니다. 또한 다른 리소스(이 경우 이미지 분석용 Cognitive Services)와 통합하는 방법을 보여줍니다.

콘솔 애플리케이션을 사용하면 웹 URL에 대한 링크를 전달할 수 있습니다. 앱은 URL을 이벤트 그리드 메시지로 게시합니다. 동시에 서버리스 함수 앱과 논리 앱은 메시지를 구독합니다. 서버리스 함수 앱은 이미지를 Blob 스토리지에 직렬화합니다. 또한 Azure Table Storage에 정보를 저장합니다. 메타데이터에는 원래 이미지 URL과 Blob 스토리지 이름이 저장됩니다. 논리 앱은 Custom Vision API와 상호 작용하여 이미지를 분석하고 시스템 생성 캡션을 만듭니다. 캡션은 메타데이터 테이블에 저장됩니다.

![이미지 아키텍처 분석 및 보관](./media/image-processing-example.png)

별도의 SPA(단일 페이지 애플리케이션)가 서버리스 함수를 호출하여 이미지 및 메타데이터 목록을 가져옵니다. 각 이미지에 대해 보관 파일에서 이미지 데이터를 전달하는 또 다른 함수를 호출합니다. 최종 결과는 자동 캡션이 있는 갤러리입니다.

![자동화된 이미지 갤러리](./media/automated-image-gallery.png)

논리 앱을 빌드하는 전체 리포지토리 및 지침은 다음에서 사용할 수 있습니다. [Event grid glue](https://github.com/JeremyLikness/Event-Grid-Glue).

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>Xamarin.Forms 및 함수를 사용하는 플랫폼 간 모바일 클라이언트

Azure Web Portal 또는 Visual Studio에서 간단한 서버리스 Azure 함수를 구현하는 방법을 알아봅니다. Android, iOS 및 Windows에서 실행되는 Xamarin.Forms를 사용하여 클라이언트를 빌드합니다. 그런 다음 서버와 서버리스 백 엔드가 있는 모바일 클라이언트 간 통신 매체로 JSON(JavaScript Object Notation)을 사용하도록 애플리케이션을 수정합니다.

자세한 내용은 [Xamarin Forms 클라이언트를 사용하여 간단한 Azure 함수 구현](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)을 참조하세요.

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>서버리스 이미지 인식을 사용하여 사진 모자이크 생성

이 샘플에서는 Azure Functions 및 Microsoft Cognitive Services Custom Vision Service를 사용하여 입력 이미지에서 사진 모자이크를 생성합니다. 모델은 이미지를 인식하도록 학습됩니다. 이미지가 업로드되면 이미지를 인식하고 Bing으로 검색합니다. 원본 이미지는 검색 결과를 사용하여 재작성됩니다.

![올랜도 아이 사진 및 모자이크](./media/orlando-eye-both.png)

예를 들어 올랜도 아이와 같은 올랜도 랜드마크를 사용하여 모델을 학습할 수 있습니다. Custom Vision은 올랜도 아이 이미지를 인식하고, 함수는 "올랜도 아이"에 대해 Bing 이미지 검색 결과로 구성된 사진 모자이크를 만듭니다.

자세한 내용은 [Azure Functions 사진 모자이크 생성기](https://github.com/Azure-Samples/functions-dotnet-photo-mosaic)를 참조하세요.

## <a name="migrate-an-existing-application-to-the-cloud"></a>기존 애플리케이션을 클라우드로 마이그레이션

이전 장에서 설명한 대로 온-프레미스 애플리케이션을 호스트하기 위해 N 계층 아키텍처를 사용하는 것이 일반적입니다. 가상 머신을 사용하여 리소스를 "있는 그대로" 마이그레이션하는 것은 클라우드로 전환하는 가장 덜 위험한 경로이지만 많은 기업은 이를 애플리케이션을 리팩터링할 수 있는 기회로 삼습니다. 다행히 리팩터링은 "양자택일"이 아닙니다. 실제로 앱을 마이그레이션한 다음 증분식으로 구성 요소를 클라우드 네이티브 구성 요소로 대체할 수 있습니다.

애플리케이션은 Azure Functions의 프록시 기능을 사용하여 레거시 온-프레미스 코드의 엔드포인트를 서버리스 엔드포인트로 리팩터링할 수 있습니다.

![마이그레이션 아키텍처](./media/migration-architecture.png)

프록시는 서버리스 함수로 이동할 때 개별 요청을 다시 라우팅하도록 업데이트되는 단일 API 엔드포인트를 제공합니다.

전체 마이그레이션 과정을 안내하는 다음의 동영상을 볼 수 있습니다. [Lift and shift with serverless Azure functions](https://channel9.msdn.com/Events/Connect/2017/E102). 샘플 코드에 액세스합니다. [Bring your own app](https://github.com/JeremyLikness/bring-own-app-connect-17).

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>CSV 파일을 구문 분석하여 데이터베이스에 삽입

ETL(추출, 변환 및 로드)은 서로 다른 시스템을 통합하는 일반적인 비즈니스 기능입니다. 기존의 접근 방식에서는 전용 FTP 서버를 설정한 후 파일을 구문 분석하고 비즈니스용으로 변환하는 예약 작업을 배포하는 경우가 많습니다. 서버리스 아키텍처는 파일이 업로드될 때 트리거를 실행할 수 있기 때문에 작업을 더 쉽게 수행할 수 있습니다. Azure Functions는 특정 문제에 초점을 맞춘 작은 코드 조각을 이상적으로 구성하여 ETL과 같은 작업을 처리합니다.

![CSV 구문 분석 프로세스를 보여 주는 스크린샷](./media/serverless-business-scenarios/csv-parse-database-import.png)

소스 코드 및 실습 랩은 [CSV import lab](https://github.com/JeremyLikness/azure-fn-file-process-hol)을 참조하세요.

## <a name="shorten-links-and-track-metrics"></a>링크 단축 및 메트릭 추적

링크 단축 도구는 원래 짧은 Twitter 게시물에서 140자 제한을 수용할 수 있도록 URL을 인코딩하는 데 도움이 되었습니다. 이후 용도가 확대되면서 가장 일반적으로 분석을 위해 클릭을 추적하는 데 사용됩니다. 링크 단축 시나리오는 링크 및 보고서 메트릭을 관리하는 온전한 서버리스 애플리케이션입니다.

Azure Functions는 긴 URL을 붙여 넣어 짧은 URL을 생성할 수 있는 SPA(단일 페이지 애플리케이션)를 제공하는 데 사용됩니다. URL에는 캠페인(토픽) 및 미디어(링크를 게시하는 소셜 네트워크)와 같은 항목을 추적하도록 태그가 지정되어 있습니다. 짧은 코드는 Azure Table Storage에 키로 저장되고 긴 URL은 값으로 저장됩니다. 짧은 링크를 클릭하면 다른 함수가 긴 URL을 조회하고, 리디렉션을 전송하고, 이벤트에 대한 정보를 큐에 넣습니다. 다른 Azure 함수가 큐를 처리하고 Azure Cosmos DB에 정보를 저장합니다.

![링크 단축기 아키텍처](./media/link-shortener-architecture.png)

그런 다음 Power BI 대시보드를 만들어 수집된 데이터에 대한 인사이트를 확보할 수 있습니다. 백 엔드에서 Application Insights는 중요한 메트릭을 제공합니다. 원격 분석에는 평균 사용자가 리디렉션하는 데 소요되는 시간과 Azure Table Storage에 액세스하는 데 걸리는 시간이 포함됩니다.

![Power BI 예제](./media/power-bi-example.png)

전체 링크 단축기 리포지토리 및 지침은 다음에서 사용할 수 있습니다. [Serverless URL shortener](https://github.com/jeremylikness/serverless-url-shortener). 다음은 간소화된 버전입니다. [Azure Storage for serverless .NET apps in minutes](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/).

## <a name="verify-device-connectivity-using-a-ping"></a>ping을 사용하여 장치 연결 확인

이 샘플은 Azure IoT Hub와 Azure 함수로 구성됩니다. IoT Hub의 새 메시지는 Azure 함수를 트리거합니다. 서버리스 코드는 동일한 메시지 내용을 전송한 장치로 다시 보냅니다. 프로젝트에는 솔루션에 필요한 모든 코드 및 배포 구성이 있습니다.

자세한 내용은 [Azure IoT Hub ping](https://github.com/Azure-Samples/iot-hub-node-ping)을 참조하세요.

## <a name="recommended-resources"></a>권장되는 리소스

- [Azure Functions 사진 모자이크 생성기](https://github.com/Azure-Samples/functions-dotnet-photo-mosaic)
- [Azure IoT Hub ping(영문)](https://github.com/Azure-Samples/iot-hub-node-ping)
- [Azure Storage for serverless .NET apps in minutes](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/)
- [Bring your own app](https://github.com/JeremyLikness/bring-own-app-connect-17)
- [CSV import lab](https://github.com/JeremyLikness/azure-fn-file-process-hol)
- [Event grid glue](https://github.com/JeremyLikness/Event-Grid-Glue)
- [Xamarin.Forms 클라이언트를 사용하여 간단한 Azure Function 구현](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)
- [Lift and shift with serverless Azure functions](https://channel9.msdn.com/Events/Connect/2017/E102)
- [Serverless URL shortener](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
>[이전](orchestration-patterns.md)
>[다음](serverless-conclusion.md)
