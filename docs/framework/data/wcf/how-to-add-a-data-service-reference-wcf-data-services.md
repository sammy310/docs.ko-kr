---
title: '방법: (WCF Data Services)는 데이터 서비스 참조 추가'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 8bf623ec74c3bd165f63f60e883bfcb532d6900b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633951"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>방법: (WCF Data Services)는 데이터 서비스 참조 추가

사용할 수는 **서비스 참조 추가** WCF Data Services에 대 한 참조를 추가 하려면 Visual Studio에서 대화 합니다. 이렇게 하면 Visual Studio에서 개발하는 클라이언트 애플리케이션에서 데이터 서비스에 보다 쉽게 액세스할 수 있습니다. 이 절차를 완료하면 데이터 서비스에서 가져온 메타데이터를 기준으로 데이터 클래스가 생성됩니다. 자세한 내용은 [데이터 서비스 클라이언트 라이브러리 생성](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)합니다.

## <a name="add-a-data-service-reference"></a>데이터 서비스 참조 추가

1. (선택 사항) 데이터 서비스가 솔루션에 포함되어 있지 않고 실행 중이 아닌 경우 데이터 서비스를 시작하고 데이터 서비스의 URI를 적어 둡니다.

2. Visual Studio에서의 **솔루션 탐색기**를 클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 선택 **추가** > **서비스 참조**합니다.

3. 데이터 서비스는 현재 솔루션의 일부 이면 클릭 **Discover**합니다.

     또는

     에 **주소** 텍스트 상자에 입력 데이터 서비스의 기본 URL 같은 `http://localhost:1234/Northwind.svc`를 클릭 하 고 **이동**합니다.

4. **확인**을 선택합니다.

     에 액세스 하 고 데이터 서비스 리소스와 상호 작용할 수 있는 데이터 클래스를 포함 하는 새 코드 파일을 프로젝트에 추가 됩니다.

## <a name="see-also"></a>참고자료

- [빠른 시작](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
