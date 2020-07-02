---
ms.openlocfilehash: 23ba6064a283b47312a66f3636c2834a7d58106e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620186"
---
### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a><span data-ttu-id="f3db4-101">ADO.NET가 이제 끊어진 SQL 연결을 자동으로 다시 연결 시도</span><span class="sxs-lookup"><span data-stu-id="f3db4-101">ADO.NET now attempts to automatically reconnect broken SQL connections</span></span>

#### <a name="details"></a><span data-ttu-id="f3db4-102">설명</span><span class="sxs-lookup"><span data-stu-id="f3db4-102">Details</span></span>

<span data-ttu-id="f3db4-103">.NET Framework 4.5.1부터는 .NET Framework가 끊어진 SQL 연결을 자동으로 다시 연결하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="f3db4-103">Beginning in the .NET Framework 4.5.1, the .NET Framework will attempt to automatically reconnect broken SQL connections.</span></span> <span data-ttu-id="f3db4-104">이것은 일반적으로 응용 프로그램을 보다 안정적으로 만들지만, 연결이 끊어져서 다시 연결될 때 어떤 조치를 취할 수 있다는 것을 앱이 알아야 할 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3db4-104">Although this will typically make apps more reliable, there are edge cases in which an app needs to know that the connection was lost so that it can take some action upon reconnection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f3db4-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="f3db4-105">Suggestion</span></span>

<span data-ttu-id="f3db4-106">이 기능이 호환성 문제로 인해 사용하지 않을 경우, 연결 문자열(또는 <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>)의 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> 속성을 0으로 설정하여 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3db4-106">If this feature is undesirable due to compatibility concerns, it can be disabled by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> property of a connection string (or <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) to 0.</span></span>

| <span data-ttu-id="f3db4-107">이름</span><span class="sxs-lookup"><span data-stu-id="f3db4-107">Name</span></span>    | <span data-ttu-id="f3db4-108">값</span><span class="sxs-lookup"><span data-stu-id="f3db4-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f3db4-109">Scope</span><span class="sxs-lookup"><span data-stu-id="f3db4-109">Scope</span></span>   |<span data-ttu-id="f3db4-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f3db4-110">Edge</span></span>|
|<span data-ttu-id="f3db4-111">버전</span><span class="sxs-lookup"><span data-stu-id="f3db4-111">Version</span></span>|<span data-ttu-id="f3db4-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="f3db4-112">4.5.1</span></span>|
|<span data-ttu-id="f3db4-113">형식</span><span class="sxs-lookup"><span data-stu-id="f3db4-113">Type</span></span>|<span data-ttu-id="f3db4-114">런타임</span><span class="sxs-lookup"><span data-stu-id="f3db4-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f3db4-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f3db4-115">Affected APIs</span></span>

-<xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)></li></ul>|
