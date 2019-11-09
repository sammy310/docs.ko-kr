---
title: 중앙 집중식 구성
description: Azure Key Vault를 사용 하 여 중앙 집중식으로 구성 하면 클라우드 네이티브 앱을 보다 쉽게 관리할 수 있습니다.
ms.date: 06/30/2019
ms.openlocfilehash: 4c516b6773d913acd71ff06742302e9766a141e2
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841140"
---
# <a name="centralized-configuration"></a>중앙 집중식 구성

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

클라우드 네이티브 응용 프로그램에는 기존의 단일 인스턴스 모놀리식 앱 보다 실행 중인 서비스가 많이 포함 되어 있습니다. 여러 개의 상호 의존적인 서비스에 대 한 구성 설정을 관리 하는 것은 어려울 수 있으므로 중앙 집중화 된 구성 저장소가 분산 응용 프로그램에 대해 구현 되는 경우가 많습니다.

[1 장](introduction.md)에서 설명한 바와 같이 12 단계 앱 권장 사항은 코드와 구성 사이에 엄격한 분리가 필요 합니다. 즉, 코드의 상수 또는 리터럴 값으로 구성 설정을 저장 하는 것은 위반입니다. 이러한 권장 사항은 개발, 테스트, 스테이징 및 프로덕션을 포함 하 여 여러 환경에서 동일한 코드를 사용 해야 하기 때문에 존재 합니다. 그러나 구성 값은 이러한 환경 마다 다를 수 있습니다. 따라서 환경 자체에 구성 값을 저장 하거나 환경에서 중앙 집중식 구성 저장소에 자격 증명을 저장 해야 합니다.

EShopOnContainers 응용 프로그램에는 각 마이크로 서비스를 사용 하는 로컬 응용 프로그램 설정 파일이 포함 됩니다. 이러한 파일은 소스 제어에 체크 인 되지만 연결 문자열 또는 API 키와 같은 프로덕션 암호는 포함 되지 않습니다. 프로덕션에서 개별 설정은 서비스별 환경 변수를 사용 하 여 덮어쓸 수 있습니다. 이 방법은 호스팅된 응용 프로그램의 경우 일반적인 방법 이지만 중앙 구성 저장소는 제공 하지 않습니다. 구성 설정에 대 한 중앙 집중식 관리를 지원 하기 위해 각 마이크로 서비스에는 로컬 설정 사용 또는 Azure Key Vault 설정 사이를 전환 하는 설정이 포함 됩니다.

## <a name="azure-key-vault"></a>Azure Key Vault

Azure Key Vault는 토큰, 암호, 인증서, API 키 및 기타 중요 한 암호의 안전한 저장소를 제공 합니다. Key Vault에 액세스 하려면 적절 한 호출자 인증 및 권한 부여가 필요 합니다 .이는 eShopOnContainers 마이크로 서비스의 경우에는 ClientId/ClientSecret 조합을 사용 하는 것을 의미 합니다. 이러한 자격 증명을 소스 제어에 체크 인 하지 말고 응용 프로그램 환경에서 설정 합니다. AKS에서의 Key Vault에 대 한 직접 액세스는 [Key Vault의 볼륨](https://github.com/Azure/kubernetes-keyvault-flexvol)을 사용 하 여 달성할 수 있습니다.

중앙 집중식 구성에서 중앙 집중식 로깅 끝점과 같은 전체 응용 프로그램에 적용 되는 설정은 한 번 설정 하 여 배포 응용 프로그램의 모든 부분에서 사용할 수 있습니다. 마이크로 서비스는 서로 독립적 이어야 하지만 일반적으로 구성 세부 정보가 중앙 집중식 구성 저장소를 활용할 수 있는 몇 가지 공유 종속성이 있습니다.

>[!div class="step-by-step"]
>[이전](deploy-eshoponcontainers-azure.md)
>[다음](scale-applications.md)
