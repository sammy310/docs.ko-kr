---
title: Entity FrameworkTypes용 SqlClient
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: d132583bba2520d37693be6c4b085cfa514003e0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737853"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>Entity FrameworkTypes용 SqlClient
.NET Framework Data Provider for SQL Server(SqlClient) 공급자 매니페스트 파일에는 공급자 기본 형식의 목록, 각 형식의 패싯, 개념적 모델과 스토리지 모델 기본 형식 간의 매핑, 개념적 모델과 스토리지 모델 기본 형식 간의 승격과 변환 규칙이 포함되어 있습니다.  
  
 다음 표에서는 SQL Server 2008, SQL Server 2005 및 SQL Server 2000 데이터베이스의 형식과 이러한 형식을 개념적 모델 형식에 매핑하는 방법에 대해 설명 합니다. 이후 버전의 SQL Server에서 도입된 몇 가지 새로운 형식은 이전 버전의 SQL Server에서는 지원되지 않습니다. 해당 형식은 다음 표에 나와 있습니다.  
  
|공급자 형식<br /><br /> name|공급자 형식<br /><br /> 특성|`EDMSimpleType`<br /><br /> name|패싯|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|N/A|`Edm.Boolean`|N/A|  
|`tinyint`|N/A|`Edm.Byte`|N/A|  
|`smallint`|N/A|`Edm.Int16`|N/A|  
|`int`|N/A|`Edm.Int32`|N/A|  
|`bigint`|N/A|`Edm.Int64`|N/A|  
|`float`|N/A|`Edm.Double`|N/A|  
|`real`|N/A|`Edm.Double`|N/A|  
|`decimal`|N/A|`Edm.Decimal`|소수<br /><br /> -최소: 1<br /><br /> -최대: 38<br /><br /> -기본값: 18<br /><br /> -상수: False<br /><br /> 배율을<br /><br /> -최소: 0<br /><br /> -최대: 38<br /><br /> -기본값: 0<br /><br /> -상수: False|  
|`numeric`|N/A|`Edm.Decimal`|소수<br /><br /> -최소: 1<br /><br /> -최대: 38<br /><br /> -기본값: 18<br /><br /> -상수: False<br /><br /> 배율을<br /><br /> -최소: 0<br /><br /> -최대: 38<br /><br /> -기본값: 0<br /><br /> -상수: False|  
|`smallmoney`|N/A|`Edm.Decimal`|소수<br /><br /> -기본값: 10<br /><br /> -상수: True<br /><br /> 배율을<br /><br /> -기본값: 4<br /><br /> -상수: True|  
|`money`|N/A|`Edm.Decimal`|소수<br /><br /> -기본값: 19<br /><br /> -상수: True<br /><br /> 배율을<br /><br /> -기본값: 4<br /><br /> -상수: True|  
|`binary`|N/A|`Edm.Binary`|MaxLength<br /><br /> -최소: 1<br /><br /> -최대: 8000<br /><br /> -기본값: 8000<br /><br /> -상수: False<br /><br /> FixedLength:<br /><br /> -기본값: True<br /><br /> -상수: True|  
|`varbinary`|N/A|`Edm.Binary`|MaxLength<br /><br /> -최소: 1<br /><br /> -최대: 8000<br /><br /> -기본값: 8000<br /><br /> -상수: False<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`varbinary(max)`<br /><br /> 참고: SQL Server 2000에서는이 형식이 지원 되지 않습니다.|N/A|`Edm.Binary`|MaxLength<br /><br /> -기본값: 214748364780<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`image`|N/A|`Edm.Binary`|MaxLength<br /><br /> -기본값: 2147483647<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`timestamp`|N/A|`Edm.Binary`|MaxLength<br /><br /> -기본값: 8<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: True<br /><br /> -상수: True|  
|`rowversion`|N/A|`Edm.Binary`|MaxLength<br /><br /> -기본값: 8<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: True<br /><br /> -상수: True|  
|`smalldatetime`|N/A|`Edm.DateTime`|소수<br /><br /> -기본값: 0<br /><br /> -상수: True|  
|`datetime`|N/A|`Edm.DateTime`|소수<br /><br /> -기본값: 3<br /><br /> -상수: True|  
|`date`<br /><br /> 참고: SQL Server 2005 및 SQL Server 2000에서는이 형식이 지원 되지 않습니다.|N/A|`Edm.DateTime`|소수<br /><br /> -기본값: 0<br /><br /> -상수: False|  
|`time`<br /><br /> 참고: SQL Server 2005 및 SQL Server 2000에서는이 형식이 지원 되지 않습니다.|N/A|`Edm.Time`|소수<br /><br /> -기본값: 7<br /><br /> -상수: False|  
|`datetime2`<br /><br /> 참고: SQL Server 2005 및 SQL Server 2000에서는이 형식이 지원 되지 않습니다.|N/A|`Edm.DateTime`|소수<br /><br /> -기본값: 7<br /><br /> -상수: False|  
|`datetimeoffset`<br /><br /> 참고: SQL Server 2005 및 SQL Server 2000에서는이 형식이 지원 되지 않습니다.|N/A|`Edm.DateTimeOffset`|소수<br /><br /> -기본값: 7<br /><br /> -상수: False|  
|`nvarchar`<br /><br /> 참고: SQL Server 2000에서는이 형식이 지원 되지 않습니다.|N/A|`Edm.String`|MaxLength<br /><br /> -최소: 1<br /><br /> -최대: 4000<br /><br /> -기본값: 4000<br /><br /> -상수: False<br /><br /> 유니코드:<br /><br /> -기본값: True<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`varchar`<br /><br /> 참고: SQL Server 2000에서는이 형식이 지원 되지 않습니다.|N/A|`Edm.String`|MaxLength<br /><br /> -최소: 1<br /><br /> -최대: 8000<br /><br /> -기본값: 8000<br /><br /> -상수: False<br /><br /> 유니코드:<br /><br /> -기본값: False<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`char`|N/A|`Edm.String`|MaxLength<br /><br /> -최소: 1<br /><br /> -최대: 8000<br /><br /> -기본값: 8000<br /><br /> -상수: False<br /><br /> 유니코드:<br /><br /> -기본값: False<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: True<br /><br /> -상수: True|  
|`nchar`|N/A|`Edm.String`|MaxLength<br /><br /> -최소: 1<br /><br /> -최대: 4000<br /><br /> -기본값: 4000<br /><br /> -상수: False<br /><br /> 유니코드:<br /><br /> -기본값: True<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: True<br /><br /> -상수: True|  
|`varchar`(`max`)|N/A|`Edm.String`|MaxLength<br /><br /> -기본값: 2147483647<br /><br /> -상수: True<br /><br /> 유니코드:<br /><br /> -기본값: False<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`nvarchar`(`max`)|N/A|`Edm.String`|MaxLength<br /><br /> -기본값: 1073741823<br /><br /> -상수: True<br /><br /> 유니코드:<br /><br /> -기본값: True<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`ntext`|같음 비교 가능: False<br /><br /> 순서 비교 가능: False|`Edm.String`|MaxLength<br /><br /> -기본값: 1073741823<br /><br /> -상수: True<br /><br /> 유니코드:<br /><br /> -기본값: False<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`text`|같음 비교 가능: False<br /><br /> 순서 비교 가능: False|`Edm.String`|MaxLength<br /><br /> -기본값: 2147483647<br /><br /> -상수: True<br /><br /> 유니코드:<br /><br /> -기본값: False<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
|`Unique`<br /><br /> `identifier`|같음 비교 가능: True<br /><br /> 순서 비교 가능: True|`Edm.Guid`|N/A|  
|`xml`|같음 비교 가능: False<br /><br /> 순서 비교 가능: False|`Edm.String`|MaxLength<br /><br /> -기본값: 1073741823<br /><br /> -상수: True<br /><br /> 유니코드:<br /><br /> -기본값: True<br /><br /> -상수: True<br /><br /> FixedLength:<br /><br /> -기본값: False<br /><br /> -상수: True|  
  
## <a name="see-also"></a>참조

- [CSDL, SSDL 및 MSL 사양](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
