---
description: '자세한 정보: 방법: 연결 문자열 정의'
title: '방법: 연결 문자열 정의'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 104264299e597bc142a689aa83f3207765d18c67
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650822"
---
# <a name="how-to-define-the-connection-string"></a>방법: 연결 문자열 정의

이 항목에서는 개념적 모델에 연결할 때 사용하는 연결 문자열을 정의하는 방법을 설명합니다. 이 항목은 [AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) 개념적 모델을 기반으로 합니다. AdventureWorks Sales 모델은 Entity Framework 설명서의 작업 관련 항목 전체에서 사용 됩니다. 이 항목에서는 Entity Framework 이미 구성 되었으며 AdventureWorks Sales 모델을 정의한 것으로 가정 합니다. 자세한 내용은 [방법: 수동으로 모델 및 매핑 파일 정의](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))를 참조 하세요. 이 항목의 절차는 [방법: Entity Framework 프로젝트 수동 구성](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))에도 포함 되어 있습니다.

> [!NOTE]
> Visual Studio 프로젝트에서 엔터티 데이터 모델 마법사를 사용 하는 경우 자동으로 .edmx 파일이 생성 되 고 Entity Framework을 사용 하도록 프로젝트가 구성 됩니다. 자세한 내용은 [방법: 엔터티 데이터 모델 마법사 사용](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))을 참조 하세요.

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

프로젝트에 응용 프로그램 구성 파일이 없는 경우 **프로젝트** 메뉴에서 **새 항목 추가** 를 선택 하 고 **일반** 범주를 선택한 다음 **응용 프로그램 구성 파일** 을 선택 하 고 **추가** 를 클릭 하 여 프로젝트를 추가할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [빠른 시작](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [방법: 새 .edmx 파일 만들기](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [ADO.NET 엔터티 데이터 모델 도구](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
