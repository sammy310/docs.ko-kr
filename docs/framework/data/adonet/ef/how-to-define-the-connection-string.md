---
title: '방법: 연결 문자열 정의'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 8386f93d0e80aa824b1e91a130812b9b3a2b3619
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306380"
---
# <a name="how-to-define-the-connection-string"></a>방법: 연결 문자열 정의

이 항목에서는 개념적 모델에 연결할 때 사용하는 연결 문자열을 정의하는 방법을 설명합니다. 이 항목에 기반 합니다 [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) 개념적 모델입니다. AdventureWorks Sales 모델은 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 문서의 작업 관련 항목 전체에서 사용됩니다. 이 항목에서는 이미 구성한 가정는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] AdventureWorks Sales 모델을 정의 합니다. 자세한 내용은 [방법: 수동으로 모델을 정의 및 매핑 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))합니다. 이 항목의에서 절차에 에서도 나와 [방법: Entity Framework 프로젝트 수동 구성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))합니다.

> [!NOTE]
> Visual Studio 프로젝트에서 엔터티 데이터 모델 마법사를 사용 하는 경우 자동으로.edmx 파일을 생성 하 고 사용 하도록 프로젝트를 구성 합니다 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다. 자세한 내용은 [방법: 엔터티 데이터 모델 마법사 사용](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))

## <a name="to-define-the-entity-framework-connection-string"></a>Entity Framework 연결 문자열을 정의하려면

- 프로젝트의 애플리케이션 구성 파일(app.config)을 열고 다음 연결 문자열을 추가합니다.

```xml
<connectionStrings>
    <add name="AdventureWorksEntities" 
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

프로젝트에 응용 프로그램 구성 파일을 선택 하 여 하나를 추가할 수 있습니다 **새 항목 추가** 에서 합니다 **프로젝트** 메뉴에서 선택 하는 **일반** 범주 선택 **응용 프로그램 구성 파일**를 클릭 한 다음 **추가**합니다.

## <a name="see-also"></a>참고자료

- [빠른 시작](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [방법: 새.edmx 파일 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [ADO.NET 엔터티 데이터 모델 도구](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
