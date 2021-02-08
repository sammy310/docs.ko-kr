---
description: '자세히 알아보기: 상속 지원'
title: 상속 지원
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: ff6956441ab72f720151e42bd9358c8df1170e09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803869"
---
# <a name="inheritance-support"></a>상속 지원

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]*단일 테이블 매핑을* 지원 합니다. 즉, 완전한 상속 계층이 단일 데이터베이스 테이블에 저장되어 있습니다. 테이블에는 계층 전체에 대한 모든 가능한 데이터 열의 결합된 공용 구조체가 포함됩니다. Union은 두 테이블을 원본 테이블 중 하나에 있는 행을 포함 하는 하나의 테이블로 결합 한 결과입니다. 각 행의 열에는 행이 나타내는 인스턴스의 형식에 적용 되지 않는 null이 있습니다.  
  
 단일 테이블 매핑 전략은 상속을 나타내는 가장 간단한 방법이며 여러 다른 쿼리 범주에 대한 탁월한 성능 특징을 제공합니다.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 이 매핑을 구현하려면 상속 계층의 루트 클래스에서 특성 및 특성 속성을 지정해야 합니다. 자세한 내용은 [방법: 상속 계층 구조 매핑](how-to-map-inheritance-hierarchies.md)을 참조 하세요.  
  
 Visual Studio를 사용 하는 개발자는 개체 관계형 디자이너을 사용 하 여 상속 계층 구조를 매핑할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [배경 정보](background-information.md)
