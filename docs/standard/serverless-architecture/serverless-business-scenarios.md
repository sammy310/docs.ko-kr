---
title: 샘플 비즈니스 시나리오 및 서버 리스 앱에 대 한 사용 사례
description: 모바일 백 엔드 및 ETL 파이프라인에서 이미지 처리 범위는 샘플에 액세스 하 여 실습 접근 방식을 통해 서버 리스에 대해 알아봅니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 177fb1d7f79a0067ab185e520778b593d4b8eaf6
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653901"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>서버리스 비즈니스 시나리오 및 사용 사례

여러 사용 사례 및 서버 리스 응용 프로그램에 대 한 시나리오는 있습니다. 이 장에서 다양 한 시나리오를 보여 주는 샘플이 포함 되어 있습니다. 시나리오 관련된 설명서 및 공개 소스 코드 리포지토리 링크에 포함 됩니다. 이 챕터에 샘플 사용을 구축 하 고 서버 리스 솔루션 구현에 직접 시작할 수 있습니다.

## <a name="analyze-and-archive-images"></a>분석 하 고 이미지를 보관 합니다.

이 샘플에는 서버 리스 이벤트 (Event Grid), 워크플로 (논리 앱) 및 코드 (Azure Functions) 보여 줍니다. 또한 이미지 분석을 위해이 사례 Cognitive Services에서 다른 리소스와 통합 하는 방법을 보여 줍니다.

콘솔 응용 프로그램을 사용 하는 웹에서 링크 URL을 전달할 수 있습니다. 앱은 이벤트 그리드 메시지로 URL을 게시합니다. 동시에 서버 리스 함수 앱 및 논리 앱을 메시지에 등록합니다. 서버 리스 함수 앱은 blob storage에 이미지를 serialize합니다. 또한 Azure Table Storage에 정보를 저장 합니다. 메타 데이터는 원래 이미지 URL 및 blob 이미지의 이름을 저장합니다. 이미지를 분석 하 고 시스템에서 생성 된 캡션이 생성 하는 사용자 지정 비전 API를 사용 하 여 논리 앱 상호 작용 합니다. 캡션에 메타 데이터 테이블에 저장 됩니다.

![분석 하 고 이미지 아키텍처를 보관 합니다.](./media/image-processing-example.png)

이미지 및 메타 데이터의 목록을 가져오려면 서버 리스 함수를 호출 하는 별도 단일 페이지 응용 프로그램 (SPA). 각 이미지에 대 한 보관 파일의 이미지 데이터를 제공 하는 다른 함수를 호출 합니다. 최종 결과 자동 캡션이 있는 갤러리입니다.

![자동화 된 이미지 갤러리](./media/automated-image-gallery.png)

논리 앱을 작성 하기 위한 지침 확인 하 고 전체 저장소는 다음과 같습니다. [Event grid 붙이기](https://github.com/JeremyLikness/Event-Grid-Glue)합니다.

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>Xamarin.Forms 및 함수를 사용 하 여 플랫폼 간 모바일 클라이언트

Azure 웹 포털에서 또는 Visual Studio에서 간단한 서버 리스 Azure 함수를 구현 하는 방법을 참조 하세요. Android, iOS 및 Windows에서 실행 되는 Xamarin.Forms 사용 하 여 클라이언트를 빌드하십시오. 응용 프로그램은 다음 서버 및 서버 리스 백 엔드를 사용 하 여 모바일 클라이언트 간의 통신 미디어로 개체 JSON (JavaScript Notation)을 사용 하도록 구체화 됩니다.

자세한 내용은 참조 하세요. [Xamarin.Forms 클라이언트를 사용 하 여 간단한 Azure 함수를 구현 합니다.](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>서버 리스 이미지 인식에는 사진 시스템 생성

샘플 입력된 이미지에서 사진 시스템을 생성 하려면 Azure Functions 및 Microsoft Cognitive Services Custom Vision Service를 사용 합니다. 모델은 이미지를 인식 하도록 학습 됩니다. 이미지가 업로드 된 이미지를 인식 하 고 Bing을 사용 하 여 검색 합니다. 원래 이미지 검색 결과 사용 하 여 재작성 됩니다.

![Orlando 눈 사진 및 시스템](./media/orlando-eye-both.png)

예를 들어, Orlando 눈 같은 Orlando 이정표를 사용 하 여 모델을 교육할 수 있습니다. Custom Vision Orlando 눈 모양, 이미지 인식 및 함수는 사진 시스템 Bing 이미지 검색 결과의 구성에 대 한 만들기 "Orlando 눈."

자세한 내용은 [Azure Functions 사진 시스템 생성기](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/)합니다.

## <a name="migrate-an-existing-application-to-the-cloud"></a>클라우드로 기존 응용 프로그램 마이그레이션

이전 챕터에서 설명 했 듯이 응용 프로그램 온-프레미스를 호스트 하는 N 계층 아키텍처를 도입에 공통적으로 적용 됩니다. "있는 그대로" 리소스를 마이그레이션 있지만 가상 컴퓨터를 사용 하 여 경로인 이상 위험한 클라우드, 많은 회사 응용 프로그램을 리팩터링 기회를 사용 하도록 선택 합니다. 다행 스럽게도 리팩터링 아니어도 "완전" 노력 합니다. 실제로 앱을 마이그레이션한 다음 증분 클라우드 네이티브 이미지를 사용 하 여 구성 요소를 대체 하는 것이 같습니다.

응용 프로그램 서버 리스 끝점에 대 한 끝점에서 레거시 온-프레미스 코드 리팩터링을 사용할 수 있도록 Azure functions 프록시 기능을 사용 합니다.

![마이그레이션 아키텍처](./media/migration-architecture.png)

프록시 서버 리스 functions로 이동 하는 것 처럼 개별 요청을 다시 라우팅하도록 업데이트 되는 단일 API 끝점을 제공 합니다.

전체 마이그레이션 과정을 안내 하는 비디오를 볼 수 있습니다. [리프트 앤 시프트 서버 리스 Azure functions를 사용 하 여](https://channel9.msdn.com/Events/Connect/2017/E102)입니다. 샘플 코드에 액세스 합니다. [사용자 고유 앱 가져오기](https://github.com/JeremyLikness/bring-own-app-connect-17)합니다.

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>CSV 파일을 구문 분석 하 고 데이터베이스에 삽입

추출, 변환 및 로드 (ETL)는 서로 다른 시스템을 통합 하는 일반적인 비즈니스 함수입니다. 기존의 접근 방식에서는 전용된 FTP 서버를 설정한 다음 예약 된 작업을 파일을 구문 분석 하 고 사용 하 여 비즈니스에 맞게 변환 배포에 자주 포함 됩니다. 서버 리스 아키텍처 보다 쉽게 작업 트리거가 파일이 업로드 되 면 때문에 있습니다. Azure Functions 싯 작업 코드는 특정 문제에 중점을 둔 작은의 이상적인 해당 구성을 통해 ETL을 선호 합니다.

![Csv 구문 분석 프로세스를 보여 주는 스크린샷.](./media/serverless-business-scenarios/csv-parse-database-import.png)

소스 코드 및 실습 [CSV 가져오기 랩](https://github.com/JeremyLikness/azure-fn-file-process-hol)합니다.

## <a name="shorten-links-and-track-metrics"></a>링크를 줄이고 메트릭 추적

원래 즉 Url을 인코딩하는 데 도움이 되었습니다 링크 줄이기 도구 twitter 게시물 140 문자 제한에 맞게 합니다. 이러한 여러 용도로 사용, 가장 일반적으로 클릭 광고 분석을 위해 추적을 포함 하도록 증가 했습니다. 링크 shortener 시나리오에 대 한 링크를 관리 하 고 메트릭을 보고 하는 완전히 서버 리스 응용 프로그램입니다.

Azure Functions는 단일 페이지 응용 프로그램 (SPA) 긴 URL을 붙여넣고 짧은 Url을 생성할 수 있도록 제공 됩니다. 캠페인 (항목) 및 미디어 (예: 링크에 게시 되는 소셜 네트워크) 등을 추적 하는 Url의 태그가 지정 됩니다. 짧은 코드는 값으로 긴 URL 사용 하 여 키로 Azure Table Storage에 저장 됩니다. 짧은 링크를 클릭 하면 다른 함수 긴 URL을 조회는 리디렉션이 보내고 이벤트에 대 한 정보를 큐에 넣습니다. 다른 Azure 함수는 큐를 처리 하 고 Azure Cosmos DB로 정보를 저장 합니다.

![링크 shortener 아키텍처](./media/link-shortener-architecture.png)

그런 다음 수집 된 데이터에 대 한 정보를 수집 하는 Power BI 대시보드를 만들 수 있습니다. 백 엔드에서 Application Insights에는 중요 한 메트릭을 제공합니다. 원격 분석에는 평균 사용자 리디렉션에 걸리는 시간 및 Azure Table Storage에 액세스 하는 데 걸리는 포함 됩니다.

![Power BI 예제](./media/power-bi-example.png)

지침을 사용 하 여 전체 링크 shortener 리포지토리는 여기 제공 됩니다. [서버 리스 URL shortener](https://github.com/jeremylikness/serverless-url-shortener)합니다. 여기서는 간소화 된 버전에 대 한 읽을 수 있습니다. [몇 분 안에 서버 리스.NET 앱에 대 한 azure Storage](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/)합니다.

## <a name="verify-device-connectivity-using-a-ping"></a>Ping을 사용 하 여 장치 연결 확인

Azure IoT Hub 및 Azure Function의 샘플 구성 됩니다. IoT Hub에서 메시지를 새 Azure Function을 트리거합니다. 서버 리스 코드를 다시 전송 하는 장치에 콘텐츠 동일한 메시지를 보냅니다. 프로젝트에 솔루션에 필요한 모든 코드 및 배포 구성.

자세한 내용은 [Azure IoT Hub ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/)합니다.

## <a name="recommended-resources"></a>권장 되는 리소스

* [Azure Functions 사진 시스템 생성기](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/)
* [Azure IoT Hub ping](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/)
* [몇 분 안에 서버 리스.NET 앱에 대 한 azure Storage](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/)
* [사용자 고유 앱 가져오기](https://github.com/JeremyLikness/bring-own-app-connect-17)
* [CSV import lab](https://github.com/JeremyLikness/azure-fn-file-process-hol)
* [Event grid 붙이기](https://github.com/JeremyLikness/Event-Grid-Glue)
* [Xamarin.Forms 클라이언트를 사용 하 여 간단한 Azure 함수를 구현합니다.](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)
* [리프트 앤 시프트 서버 리스 Azure functions 사용 하 여](https://channel9.msdn.com/Events/Connect/2017/E102)
* [서버 리스 URL shortener](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
>[이전](orchestration-patterns.md)
>[다음](serverless-conclusion.md)