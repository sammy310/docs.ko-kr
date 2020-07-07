---
ms.openlocfilehash: 241184d61d718fedfea396260e739d2dbc05c305
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620286"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a><span data-ttu-id="fd25f-101">SqlConnection은 더 이상 VIA 어댑터를 사용하여 SQL Server 1997 또는 데이터베이스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd25f-101">SqlConnection can no longer connect to SQL Server 1997 or databases using the VIA adapter</span></span>

#### <a name="details"></a><span data-ttu-id="fd25f-102">설명</span><span class="sxs-lookup"><span data-stu-id="fd25f-102">Details</span></span>

<span data-ttu-id="fd25f-103">[VIA(Virtual Interface Adapter) 프로토콜](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105))을 사용하는 SQL Server 데이터베이스에 대한 연결은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd25f-103">Connections to SQL Server databases using the [Virtual Interface Adapter (VIA) protocol](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) are no longer supported.</span></span> <span data-ttu-id="fd25f-104">SQL Server 데이터베이스에 연결하는 데 사용되는 프로토콜은 연결 문자열에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd25f-104">The protocol used to connect to a SQL Server database is visible in the connection string.</span></span> <span data-ttu-id="fd25f-105">VIA 연결은 &lt;servername&gt;을 통해 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd25f-105">A VIA connection will contain via:&lt;servername&gt;.</span></span> <span data-ttu-id="fd25f-106">이 앱이 VIA가 아닌 프로토콜(예: tcp: 또는 np:)을 통해 SQL에 연결하는 경우에는 호환성이 손상되는 변경이 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd25f-106">If this app is connecting to SQL via a protocol other than VIA (tcp: or np: for example), then no breaking change will be encountered.</span></span> <span data-ttu-id="fd25f-107">또한 SQL Server 7(1997) 연결은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd25f-107">Also, connections to SQL Server 7 (1997) are no longer supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fd25f-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="fd25f-108">Suggestion</span></span>

<span data-ttu-id="fd25f-109">VIA 프로토콜은 사용되지 않으므로 대체 프로토콜을 사용하여 SQL 데이터베이스에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd25f-109">The VIA protocol is deprecated, so an alternative protocol should be used to connect to SQL databases.</span></span> <span data-ttu-id="fd25f-110">가장 일반적으로 사용되는 프로토콜은 TCP/IP입니다.</span><span class="sxs-lookup"><span data-stu-id="fd25f-110">The most common protocol used is TCP/IP.</span></span> <span data-ttu-id="fd25f-111">TCP/IP를 통한 연결에 대한 자세한 내용은 [데이터베이스 인스턴스에 대해 TCP/IP 프로토콜 사용](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd25f-111">For more information about connecting through TCP/IP, see [Enable the TCP/IP protocol for a database instance](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span></span> <span data-ttu-id="fd25f-112">데이터베이스가 인트라넷 내에서만 액세스되는 경우에 네트워크가 느린 경우 공유 파이프 프로토콜이 더 나은 성능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd25f-112">If the database is only accessed from within an intranet, the shared pipes protocol may provide better performance if the network is slow.</span></span>

| <span data-ttu-id="fd25f-113">이름</span><span class="sxs-lookup"><span data-stu-id="fd25f-113">Name</span></span>    | <span data-ttu-id="fd25f-114">값</span><span class="sxs-lookup"><span data-stu-id="fd25f-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fd25f-115">Scope</span><span class="sxs-lookup"><span data-stu-id="fd25f-115">Scope</span></span>   |<span data-ttu-id="fd25f-116">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fd25f-116">Edge</span></span>|
|<span data-ttu-id="fd25f-117">버전</span><span class="sxs-lookup"><span data-stu-id="fd25f-117">Version</span></span>|<span data-ttu-id="fd25f-118">4.5</span><span class="sxs-lookup"><span data-stu-id="fd25f-118">4.5</span></span>|
|<span data-ttu-id="fd25f-119">형식</span><span class="sxs-lookup"><span data-stu-id="fd25f-119">Type</span></span>|<span data-ttu-id="fd25f-120">런타임</span><span class="sxs-lookup"><span data-stu-id="fd25f-120">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fd25f-121">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="fd25f-121">Affected APIs</span></span>

-<xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)></li></ul>|
