---
title: Docker 컨테이너, 이미지 및 레지스트리
description: 레지스트리에 Docker 방식으로 응용 프로그램 배포의 전체 재생는 중요 한 역할에 알아봅니다.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: e69490734a03cf58bf8534bc9e31110a11d44c58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795327"
---
# <a name="docker-containers-images-and-registries"></a>Docker 컨테이너, 이미지 및 레지스트리

Docker를 사용 하는 경우 만든 앱 또는 서비스 및 패키지를 하 고 컨테이너 이미지에 종속 됩니다. 이미지는 앱 또는 서비스와 그 구성 및 종속성을 정적으로 표현합니다.

앱 또는 서비스를 실행하려면 앱의 이미지가 인스턴스화되어 Docker 호스트에서 실행되는 컨테이너를 만듭니다. 컨테이너는 개발 환경 또는 PC에서 초기에 테스트됩니다.

레지스트리에 이미지 라이브러리로 사용 되는 이미지를 저장 합니다. 프로덕션 오 케 스트레이 터에 배포할 때 레지스트리를 해야 합니다. Docker는 [Docker 허브](https://hub.docker.com/)를 통해 공용 레지스트리를 관리합니다. 다른 공급업체는 다른 이미지 컬렉션을 위한 [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) 등의 레지스트리를 제공합니다. 또는 기업에서는 자체 Docker 이미지를 위해 개인 레지스트리 온-프레미스를 가질 수 있습니다.

그림 1-4의 Docker 이미지와 레지스트리가 다른 구성 요소에 연결 하는 방법을 보여 줍니다. 그것은 또한 공급업체로부터 제공되는 여러 레지스트리를 보여줍니다.

![Docker에서 기본 분류: 이미지 저장 및 서비스 또는 웹 앱을 실행할 컨테이너를 빌드하기 위한 가져올 수 있게 되는 관련 서적 등 레지스트리는. 개인 Docker 레지스트리 온-프레미스 및 공용 클라우드입니다. Docker 허브는 엔터프라이즈급 솔루션인 Docker Trusted Registry와 함께 Docker에서 유지 관리되는 공용 레지스트리이며, Azure는 Azure Container Registry를 제공합니다. AWS, Google 등에도 컨테이너 레지스트리가 있습니다.](./media/image4.png)

**그림 1-4**. Docker 용어 및 개념의 분류

레지스트리에 이미지를 배치 하 여 모든 프레임 워크 수준 종속성을 포함 하 여 정적 및 변경할 수 없는 응용 프로그램 비트를 저장할 수 있습니다. 하면 다음 버전 및 여러 환경에서 이미지를 배포한 따라서 일관 된 배포 단위를 제공 합니다.

온-프레미스 또는 클라우드에서 호스팅되는 개인 이미지 레지스티리는 다음과 같은 경우에 권장됩니다.

- 기밀로 인해 이미지를 공개적으로 공유해서는 안됩니다.

- 이미지와 선택한 배포 환경 사이에는 최소 네트워크 대기 시간이 요구됩니다. 예를 들어 프로덕션 환경의 Azure 인 경우 아마도 하려는에서 이미지를 저장할 [Azure Container Registry](https://azure.microsoft.com/services/container-registry/) 네트워크 대기 시간이 최소화 되도록 합니다. 프로덕션 환경이 동일한 로컬 네트워크 내에서 사용 가능한 온-프레미스 Docker Trusted Registry인 경우에도 마찬가지입니다.

>[!div class="step-by-step"]
>[이전](docker-terminology.md)
>[다음](road-to-modern-applications-based-on-containers.md)
