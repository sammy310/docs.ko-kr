---
ms.openlocfilehash: 687118157020ede200f97a0125c4740a06bf4b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620306"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a><span data-ttu-id="68257-101">ObjectContext.CreateDatabase 및 DbProviderServices.CreateDatabase 메서드를 처리하는 다른 예외</span><span class="sxs-lookup"><span data-stu-id="68257-101">Different exception handling for ObjectContext.CreateDatabase and DbProviderServices.CreateDatabase methods</span></span>

#### <a name="details"></a><span data-ttu-id="68257-102">설명</span><span class="sxs-lookup"><span data-stu-id="68257-102">Details</span></span>

<span data-ttu-id="68257-103">.NET Framework 4.5부터 데이터베이스 만들기에 실패하면 <code>CreateDatabase</code> 메서드는 빈 데이터베이스를 삭제하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="68257-103">Beginning in .NET Framework 4.5, if database creation fails, <code>CreateDatabase</code> methods will attempt to drop the empty database.</span></span> <span data-ttu-id="68257-104">해당 작업에 성공하면 원래의 <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>이 전파됩니다(항상 .NET Framework 4.0에서 throw된 <xref:System.InvalidOperationException?displayProperty=fullName> 대신).</span><span class="sxs-lookup"><span data-stu-id="68257-104">If that operation succeeds, the original <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> will be propagated (instead of the <xref:System.InvalidOperationException?displayProperty=fullName> that was always thrown in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="68257-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="68257-105">Suggestion</span></span>

<span data-ttu-id="68257-106"><xref:System.Data.Objects.ObjectContext.CreateDatabase> 또는 <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>를 실행하는 동안 <xref:System.InvalidOperationException?displayProperty=fullName>을 catch하는 경우, 이제 SQLExceptions도 catch됩니다.</span><span class="sxs-lookup"><span data-stu-id="68257-106">When catching an <xref:System.InvalidOperationException?displayProperty=fullName> while executing <xref:System.Data.Objects.ObjectContext.CreateDatabase> or <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, SQLExceptions should now also be caught.</span></span>

| <span data-ttu-id="68257-107">이름</span><span class="sxs-lookup"><span data-stu-id="68257-107">Name</span></span>    | <span data-ttu-id="68257-108">값</span><span class="sxs-lookup"><span data-stu-id="68257-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="68257-109">Scope</span><span class="sxs-lookup"><span data-stu-id="68257-109">Scope</span></span>   |<span data-ttu-id="68257-110">부</span><span class="sxs-lookup"><span data-stu-id="68257-110">Minor</span></span>|
|<span data-ttu-id="68257-111">버전</span><span class="sxs-lookup"><span data-stu-id="68257-111">Version</span></span>|<span data-ttu-id="68257-112">4.5</span><span class="sxs-lookup"><span data-stu-id="68257-112">4.5</span></span>|
|<span data-ttu-id="68257-113">형식</span><span class="sxs-lookup"><span data-stu-id="68257-113">Type</span></span>|<span data-ttu-id="68257-114">런타임</span><span class="sxs-lookup"><span data-stu-id="68257-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="68257-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="68257-115">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
