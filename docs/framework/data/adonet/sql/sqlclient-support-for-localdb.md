---
title: LocalDB에 대한 SqlClient 지원
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 55ab1346de6f5c14f15d01344a984c18edf30e02
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824482"
---
# <a name="sqlclient-support-for-localdb"></a>LocalDB에 대한 SqlClient 지원

이 문서에서는 LocalDB 데이터베이스에 연결 하는 방법을 설명 합니다. LocalDB는 SQL Server의 경량 버전입니다.
  
## <a name="remarks"></a>설명
  
 LocalDB로 수행할 수 있는 작업을 요약하면 다음과 같습니다.  
  
- sqllocaldb.exe 또는 app.config 파일을 사용하여 LocalDB 인스턴스를 만들고 시작합니다.  
  
- sqlcmd.exe를 사용하여 LocalDB 인스턴스에서 데이터베이스를 추가하고 수정할 수 있습니다. 예: `sqlcmd -S (localdb)\myinst`.  
  
- `AttachDBFilename` 연결 문자열 키워드를 사용하여 데이터베이스를 LocalDB 인스턴스에 추가합니다. `AttachDBFilename`을 사용할 때 `Database` 연결 문자열 키워드를 사용하여 데이터베이스 이름을 지정하지 않으면 애플리케이션이 닫힐 때 LocalDB 인스턴스에서 데이터베이스가 제거됩니다.  
  
- 연결 문자열에 LocalDB 인스턴스를 지정합니다. 예를 들어 인스턴스 이름이 `myInstance`인 경우 연결 문자열에는 다음이 포함됩니다.  
  
    `server=(localdb)\\myInstance`  
  
 `User Instance=True`는 LocalDB 데이터베이스에 연결할 때 허용되지 않습니다.  
  
LocalDB 설치에 대 한 자세한 내용은 [SQL Server Express localdb](/sql/database-engine/configure-windows/sql-server-express-localdb)를 참조 하세요.
  
## <a name="programmatically-create-a-named-instance"></a>프로그래밍 방식으로 명명된 인스턴스 만들기  

 애플리케이션에서는 명명된 인스턴스를 만들고 다음과 같이 데이터베이스를 지정할 수 있습니다.  
  
- 다음과 같이 app.config 파일에 만들 LocalDB 인스턴스를 지정합니다.  인스턴스의 버전 번호는 LocalDB 설치의 버전 번호와 동일해야 합니다.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
- `server` 연결 문자열 키워드를 사용하여 인스턴스의 이름을 지정합니다.  `server` 연결 문자열 키워드에 지정된 인스턴스 이름은 app.config 파일에 지정된 이름과 일치해야 합니다.  
  
- `AttachDBFilename` 연결 문자열 키워드를 사용하여 .MDF 파일을 지정합니다.  
  
## <a name="see-also"></a>참고 항목

- [SQL Server 기능 및 ADO.NET](sql-server-features-and-adonet.md)
- [ADO.NET 개요](../ado-net-overview.md)
