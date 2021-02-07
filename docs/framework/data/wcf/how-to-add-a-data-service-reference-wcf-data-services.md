---
description: '자세히 알아보기: 방법: 데이터 서비스 참조 추가 (WCF Data Services)'
title: '방법: 데이터 서비스 참조 추가(WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 907ad9a7dc3710a6e565de55c74a0d279d20e159
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765753"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>방법: 데이터 서비스 참조 추가 (WCF Data Services)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Visual Studio의 **서비스 참조 추가** 대화 상자를 사용 하 여 WCF Data Services에 대 한 참조를 추가할 수 있습니다. 이렇게 하면 Visual Studio에서 개발하는 클라이언트 애플리케이션에서 데이터 서비스에 보다 쉽게 액세스할 수 있습니다. 이 절차를 완료하면 데이터 서비스에서 가져온 메타데이터를 기준으로 데이터 클래스가 생성됩니다. 자세한 내용은 [데이터 서비스 클라이언트 라이브러리 생성](generating-the-data-service-client-library-wcf-data-services.md)을 참조 하십시오.

## <a name="add-a-data-service-reference"></a>데이터 서비스 참조 추가

1. (선택 사항) 데이터 서비스가 솔루션에 포함되어 있지 않고 실행 중이 아닌 경우 데이터 서비스를 시작하고 데이터 서비스의 URI를 적어 둡니다.

2. Visual Studio의 **솔루션 탐색기** 에서 클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음   >  **서비스 참조** 추가를 선택 합니다.

3. 데이터 서비스가 현재 솔루션의 일부인 경우 **검색** 을 클릭 합니다.

     또는

     **주소** 텍스트 상자에 데이터 서비스의 기본 URL (예:)을 입력 한 `http://localhost:1234/Northwind.svc` 다음 **이동** 을 클릭 합니다.

4. **확인** 을 선택합니다.

     데이터 서비스 리소스에 액세스 하 고 상호 작용할 수 있는 데이터 클래스가 포함 된 새 코드 파일이 프로젝트에 추가 됩니다.

## <a name="see-also"></a>참고 항목

- [빠른 시작](quickstart-wcf-data-services.md)
