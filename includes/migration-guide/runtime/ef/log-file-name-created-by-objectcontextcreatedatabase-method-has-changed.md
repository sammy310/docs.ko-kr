---
ms.openlocfilehash: e77e37156de759856c8a6f2e0c009caf9e1fe826
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497628"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>ObjectContext.CreateDatabase 메서드로 만든 로그 파일 이름이 SQL Server 사양에 맞게 변경됩니다.

#### <a name="details"></a>설명

<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> 메서드를 직접 호출하거나 SqlClient 공급자로 Code First를 사용하고 연결 문자열의 AttachDBFilename 값을 사용하여 호출하면 filename.ldf 대신 filename_log.ldf라는 로그 파일이 생성됩니다(filename이 AttachDBFilename 값으로 지정한 파일 이름인 경우). 이 변경을 통해 SQL Server 사양에 따라 명명된 로그 파일을 제공하여 디버깅을 개선합니다.

#### <a name="suggestion"></a>제안 해결 방법

로그 파일 이름이 응용 프로그램에서 중요한 경우 응용 프로그램은 표준 _log.ldf 파일 이름 형식을 사용하도록 업데이트되어야 합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Data.Objects.ObjectContext.CreateDatabase`

-->
