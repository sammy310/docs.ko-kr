---
title: SQL Server 이진 및 큰 값 데이터
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: a9296e83b0f4e4352423470433670bb2cbe5a248
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183041"
---
# <a name="sql-server-binary-and-large-value-data"></a>SQL Server 이진 및 큰 값 데이터

SQL Server에서는 `varchar`, `nvarchar` 및 `varbinary` 데이터 형식의 스토리지 용량을 확장하는 `max` 지정자를 제공합니다. `varchar(max)`, `nvarchar(max)` 및 `varbinary(max)`를 통칭하여 *큰 값 데이터 형식*이라고 합니다. 큰 값 데이터 형식을 사용하여 최대 2^31-1바이트의 데이터를 저장할 수 있습니다.  
  
 SQL Server 2008에서는 데이터 형식이 아닌 하나의 열에서 정의될 수 있는 특성인 FILESTREAM 특성을 소개하고 있으며, 이를 통해 데이터베이스 대신 파일 시스템에 큰 값 데이터를 저장할 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  

 [ADO.NET에서 대량 값 (max) 데이터 수정](modifying-large-value-max-data.md)  
 큰 값 데이터 형식을 사용하는 방법을 설명합니다.  
  
 [FILESTREAM 데이터](filestream-data.md)  
 FILESTREAM 특성을 사용하여 SQL Server 2008에 저장된 큰 값 데이터를 사용하는 방법을 설명합니다.  
  
## <a name="see-also"></a>참고 항목

- [SQL Server 데이터 형식 및 ADO.NET](sql-server-data-types.md)
- [ADO.NET의 SQL Server 데이터 작업](sql-server-data-operations.md)
- [ADO.NET에서 데이터 검색 및 수정](../retrieving-and-modifying-data.md)
- [ADO.NET 개요](../ado-net-overview.md)
