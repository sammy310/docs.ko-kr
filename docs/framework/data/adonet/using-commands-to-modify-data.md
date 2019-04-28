---
title: 명령을 사용하여 데이터 수정
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: f2e3d162bfbdcb79cfecefa4ddc8e6a0dc46ee3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61875955"
---
# <a name="using-commands-to-modify-data"></a>명령을 사용하여 데이터 수정
.NET Framework 데이터 공급자를 사용하여 저장 프로시저나 CREATE TABLE 및 ALTER COLUMN과 같은 데이터 정의 언어 문을 실행하여 데이터베이스 또는 카탈로그의 스키마를 조작할 수 있습니다. 이러한 명령에서는 쿼리에서와 같이 행을 반환 하지 않습니다 때문 **명령** 개체를 제공는 **ExecuteNonQuery** 처리 하도록 합니다.  
  
 사용 하는 것 외에도 **ExecuteNonQuery** 프로세스 SQL 문에 데이터를 수정 하지만 INSERT, UPDATE와 같은 행을 반환 하지 않으며 삭제는이 메서드를 이용할 수 있습니다 스키마를 수정 합니다.  
  
 행으로 반환 되지 않습니다 하지만 합니다 **ExecuteNonQuery** 메서드, 입력 및 출력 매개 변수 및 반환 값 전달 하거나 통해 반환할 수 있습니다는 **매개 변수** 의 컬렉션을 **명령**  개체입니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [데이터 원본에서 데이터 업데이트](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 데이터베이스의 데이터를 수정하는 명령 또는 저장 프로시저를 실행하는 방법을 설명합니다.  
  
 [카탈로그 작업 수행](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 데이터베이스 스키마를 수정하는 명령을 실행하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고자료

- [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
