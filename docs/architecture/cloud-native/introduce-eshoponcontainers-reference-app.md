---
title: EShopOnContainers 참조 앱 소개
description: ASP.NET Core 및 Azure에 대 한 eShopOnContainers Cloud 기본 마이크로 서비스 참조 앱 소개
ms.date: 06/30/2019
ms.openlocfilehash: 8d4ad982716a07613ebbef6668afab69d5a8b4f6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895534"
---
# <a name="introducing-eshoponcontainers-reference-app"></a>EShopOnContainers 참조 앱 소개

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Microsoft는 업계 최고의 커뮤니티 전문가와 협력 하 여 완전 한 기능을 갖춘 클라우드 기본 마이크로 서비스 참조 응용 프로그램 eShopOnContainers를 만들었습니다. 이 응용 프로그램은 .NET Core 및 Docker를 사용 하 고 필요에 따라 Azure, Kubernetes 및 Visual Studio를 사용 하 여 온라인 storefront를 빌드하기 위한 것입니다.

![eShopOnContainers 샘플 앱 스크린샷.](./media/eshoponcontainers-sample-app-screenshot.png)

**그림 2-1**. eShopOnContainers 샘플 앱 스크린샷.

이 챕터를 시작 하기 전에 [eShopOnContainers 참조 응용 프로그램](https://github.com/dotnet-architecture/eShopOnContainers)을 다운로드 하는 것이 좋습니다. 이렇게 하는 경우 제공 된 정보를 따라 작업을 수행 하는 것이 더 쉽습니다.

## <a name="features-and-requirements"></a>기능 및 요구 사항

응용 프로그램의 기능 및 요구 사항에 대 한 검토를 시작 하겠습니다. EShopOnContainers 응용 프로그램은 t-shirts 및 커피 머그잔와 같은 다양 한 물리적 제품을 판매 하는 온라인 상점을 나타냅니다. 이전에 모든 항목을 구입한 경우 스토어를 사용 하는 환경은 상대적으로 익숙할 것입니다. 다음은 스토어에서 구현 하는 몇 가지 기본 기능입니다.

- 카탈로그 항목 나열
- 유형별로 항목 필터링
- 브랜드 별 항목 필터링
- 시장 바구니에 항목 추가
- 바구니에서 항목 편집 또는 제거
- 체크 아웃
- 계정 등록
- 로그인
- 로그아웃
- 주문 검토

응용 프로그램에는 다음과 같은 기능을 수행 하지 않는 요구 사항도 있습니다.

- 항상 사용 가능 해야 하며 증가 된 트래픽을 충족 하기 위해 자동으로 크기를 조정 해야 합니다 (그리고 트래픽 하위 면에서 한 번만 축소).
- 발생 한 문제를 해결 하는 데 도움이 되는 상태 및 진단 로그에 대 한 사용 하기 쉬운 모니터링을 제공 해야 합니다.
- CI/CD (연속 통합 및 배포) 지원을 포함 하 여 agile 개발 프로세스를 지원 해야 합니다.
- 응용 프로그램은 두 개의 웹 프런트 엔드 (기존 및 단일 페이지 응용 프로그램) 외에도 다양 한 종류의 운영 체제를 실행 하는 모바일 클라이언트 앱을 지원 해야 합니다.
- 플랫폼 간 호스팅 및 플랫폼 간 개발을 지원 해야 합니다.

![eShopOnContainers reference 응용 프로그램 개발 아키텍처.](./media/eshoponcontainers-development-architecture.png)

**그림 2-2**. eShopOnContainers reference 응용 프로그램 개발 아키텍처.

EShopOnContainers 응용 프로그램은 ASP.NET Core MVC 서버 응용 프로그램 또는 적절 한 API 게이트웨이를 대상으로 하는 HTTPS를 통해 응용 프로그램에 액세스 하는 웹 또는 모바일 클라이언트에서 액세스할 수 있습니다. API 게이트웨이는 개별 프런트 엔드 클라이언트에서 백 엔드 서비스를 분리 하 고 더 나은 보안을 제공 하는 것과 같은 여러 가지 이점을 제공 합니다. 또한 응용 프로그램은 각 프런트 엔드 클라이언트에 대해 별도의 API 게이트웨이를 만드는 것을 권장 하는 백 엔드-프런트 엔드 (BFF) 라는 관련 패턴을 사용 합니다. 참조 아키텍처는 요청이 웹 또는 모바일 클라이언트에서 발생 하는지 여부에 따라 API 게이트웨이를 분리 하는 방법을 보여 줍니다.

응용 프로그램의 기능은 다양 한 마이크로 서비스로 분할 됩니다. 인증 및 id를 담당 하 고, 제품 카탈로그에서 항목을 나열 하 고, 사용자의 쇼핑 바구니를 관리 하 고, 주문을 배치 하는 서비스가 있습니다. 이러한 각 개별 서비스에는 자체 영구 저장소가 있습니다. 모든 서비스가 상호 작용 하는 단일 마스터 데이터 저장소는 없습니다. 대신, 필요에 따라 서비스 간의 조정 및 통신이 수행 되며 메시지 버스를 사용 합니다.

각 마이크로 서비스는 개별 요구 사항에 따라 다르게 디자인 됩니다. 즉, 모두 .NET Core를 사용 하 여 구축 되 고 클라우드에 대해 설계 되었지만 기술 스택이 다를 수 있습니다. 간단한 서비스는 기본 데이터 저장소에 대 한 기본 CRUD (만들기-읽기-업데이트-삭제) 액세스를 제공 하는 반면, 고급 서비스는 도메인 기반 디자인 방법과 패턴을 사용 하 여 비즈니스 복잡성을 관리 합니다.

![다양 한 종류의 마이크로 서비스](./media/different-kinds-of-microservices.png)

**그림 2-3**. 다양 한 종류의 마이크로 서비스.

## <a name="overview-of-the-code"></a>코드 개요

마이크로 서비스를 활용 하기 때문에 eShopOnContainers 앱은 GitHub 리포지토리에서 매우 많은 개별 프로젝트와 솔루션을 포함 합니다. 별도의 솔루션 및 실행 파일 외에도 다양 한 서비스는 로컬 개발 및 프로덕션 환경에서 자체 컨테이너 내에서 실행 되도록 설계 되었습니다. 그림 2-4에는 다양 한 프로젝트를 구성 하는 전체 Visual Studio 솔루션이 나와 있습니다.

![Visual Studio 솔루션의 프로젝트](./media/projects-in-visual-studio-solution.png)

**그림 2-4**. Visual Studio 솔루션의 프로젝트

코드는 다양 한 마이크로 서비스를 지원 하도록 구성 되 고, 각 마이크로 서비스 내에서 코드는 도메인 논리, 인프라 문제, 사용자 인터페이스 또는 서비스 끝점으로 구분 됩니다. 대부분의 경우 각 서비스의 종속성은 프로덕션의 Azure 서비스 및 로컬 개발을 위한 대체 옵션으로 충족 될 수 있습니다. 응용 프로그램의 요구 사항이 Azure 서비스에 매핑되는 방식을 살펴보겠습니다.

## <a name="understanding-microservices"></a>마이크로서비스 이해

이 책에서는 Azure 기술을 사용 하 여 구축 된 클라우드 네이티브 응용 프로그램에 중점을 둘 것입니다. 마이크로 서비스 모범 사례 및 마이크로 서비스 기반 응용 프로그램을 설계 하는 방법에 대 한 자세한 내용은 부록 설명서 [.Net 마이크로 서비스: 컨테이너 화 된 .Net 응용 프로그램 아키텍처](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)를 참조 하세요.

>[!div class="step-by-step"]
>[이전](candidate-apps.md)
>[다음](map-eshoponcontainers-azure-services.md)
