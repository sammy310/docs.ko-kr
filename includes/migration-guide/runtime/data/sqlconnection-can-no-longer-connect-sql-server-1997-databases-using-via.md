---
ms.openlocfilehash: e65ba0edb132f5cded244a69d58e43ffea76a039
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606516"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection은 더 이상 VIA 어댑터를 사용하여 SQL Server 1997 또는 데이터베이스에 연결할 수 없습니다.

#### <a name="details"></a>설명

[VIA(Virtual Interface Adapter) 프로토콜](/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105))을 사용하는 SQL Server 데이터베이스에 대한 연결은 더 이상 지원되지 않습니다. SQL Server 데이터베이스에 연결하는 데 사용되는 프로토콜은 연결 문자열에 표시됩니다. VIA 연결은 &lt;servername&gt;을 통해 포함됩니다. 이 앱이 VIA가 아닌 프로토콜(예: tcp: 또는 np:)을 통해 SQL에 연결하는 경우에는 호환성이 손상되는 변경이 발생하지 않습니다. 또한 SQL Server 7(1997) 연결은 더 이상 지원되지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

VIA 프로토콜은 사용되지 않으므로 대체 프로토콜을 사용하여 SQL 데이터베이스에 연결해야 합니다. 가장 일반적으로 사용되는 프로토콜은 TCP/IP입니다. TCP/IP를 통한 연결에 대한 자세한 내용은 [데이터베이스 인스턴스에 대해 TCP/IP 프로토콜 사용](/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90))을 참조하세요. 데이터베이스가 인트라넷 내에서만 액세스되는 경우에 네트워크가 느린 경우 공유 파이프 프로토콜이 더 나은 성능을 제공할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)>
- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String)`
- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String,System.Data.SqlClient.SqlCredential)`

-->
