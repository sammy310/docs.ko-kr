---
title: LINQ to SQL을 사용한 N 계층 및 원격 애플리케이션
ms.date: 03/30/2017
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
ms.openlocfilehash: 295be0157c260c05a2e4a7dbbfcd7e5cecbc85de
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548002"
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a><span data-ttu-id="3881f-102">LINQ to SQL을 사용한 N 계층 및 원격 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="3881f-102">N-Tier and Remote Applications with LINQ to SQL</span></span>
<span data-ttu-id="3881f-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 n 계층 또는 다계층 애플리케이션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3881f-103">You can create n-tier or multitier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="3881f-104">일반적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 데이터 컨텍스트, 엔터티 클래스 및 쿼리 생성 논리는 중간 계층에서 DAL (데이터 액세스 계층)로 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3881f-104">Typically, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] data context, entity classes, and query construction logic are located on the middle tier as the data access layer (DAL).</span></span> <span data-ttu-id="3881f-105">비즈니스 논리와 모든 비지속적 데이터는 엔터티와 데이터 컨텍스트의 부분 클래스와 메서드에 완전하게 구현되거나 별도의 클래스에 구현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3881f-105">Business logic and any non-persistent data can be implemented completely in partial classes and methods of entities and the data context, or it can be implemented in separate classes.</span></span>

 <span data-ttu-id="3881f-106">클라이언트 또는 프레젠테이션 계층에서 중간 계층의 원격 인터페이스에 있는 메서드를 호출하면 중간 계층의 DAL에서는 <xref:System.Data.Linq.DataContext> 메서드에 매핑된 쿼리나 저장 프로시저를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3881f-106">The client or presentation layer calls methods on the middle-tier's remote interface, and the DAL on that tier will execute queries or stored procedures that are mapped to <xref:System.Data.Linq.DataContext> methods.</span></span> <span data-ttu-id="3881f-107">중간 계층에서는 일반적으로 프록시 개체 또는 엔터티의 XML 표현으로 클라이언트에 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3881f-107">The middle tier returns the data to clients typically as XML representations of entities or proxy objects.</span></span>

 <span data-ttu-id="3881f-108">중간 계층에서 엔터티는 엔터티의 상태를 추적하는 데이터 컨텍스트에 의해 만들어지며, 데이터베이스로부터의 지연된 로드 및 데이터베이스로의 변경 내용 전송을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="3881f-108">On the middle tier, entities are created by the data context, which tracks their state, and manages deferred loading from and submission of changes to the database.</span></span> <span data-ttu-id="3881f-109">이러한 엔터티는 `DataContext`에 "연결"됩니다.</span><span class="sxs-lookup"><span data-stu-id="3881f-109">These entities are "attached" to the `DataContext`.</span></span> <span data-ttu-id="3881f-110">그러나 serialization을 통해 엔터티를 다른 계층으로 보내면 엔터티가 분리되어 `DataContext`에서 해당 엔터티의 상태를 더 이상 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3881f-110">However, after the entities are sent to another tier through serialization, they become detached, which means the `DataContext` is no longer tracking their state.</span></span> <span data-ttu-id="3881f-111">업데이트를 위해 클라이언트에서 다시 보내는 엔터티는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 변경 내용을 데이터베이스에 전송하기 전에 데이터 컨텍스트에 다시 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3881f-111">Entities that the client sends back for updates must be reattached to the data context before [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can submit the changes to the database.</span></span> <span data-ttu-id="3881f-112">낙관적 동시성 검사에 원래 값 및/또는 타임스탬프가 필요한 경우 클라이언트에서는 이러한 정보를 중간 계층에 다시 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3881f-112">The client is responsible for providing original values and/or timestamps back to the middle tier if those are required for optimistic concurrency checks.</span></span>

 <span data-ttu-id="3881f-113">ASP.NET 애플리케이션에서는 이러한 복잡한 작업을 <xref:System.Web.UI.WebControls.LinqDataSource>에서 대부분 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3881f-113">In ASP.NET applications, the <xref:System.Web.UI.WebControls.LinqDataSource> manages most of this complexity.</span></span> <span data-ttu-id="3881f-114">자세한 내용은 [LinqDataSource 웹 서버 컨트롤 개요](/previous-versions/aspnet/bb547113(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3881f-114">For more information, see [LinqDataSource Web Server Control Overview](/previous-versions/aspnet/bb547113(v=vs.100)).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3881f-115">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="3881f-115">Additional Resources</span></span>
 <span data-ttu-id="3881f-116">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 n 계층 애플리케이션을 구현하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3881f-116">For more information about how to implement n-tier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], see the following topics:</span></span>

- [<span data-ttu-id="3881f-117">ASP.NET을 사용하는 LINQ to SQL N 계층</span><span class="sxs-lookup"><span data-stu-id="3881f-117">LINQ to SQL N-Tier with ASP.NET</span></span>](linq-to-sql-n-tier-with-aspnet.md)

- [<span data-ttu-id="3881f-118">웹 서비스를 사용하는 LINQ to SQL N 계층</span><span class="sxs-lookup"><span data-stu-id="3881f-118">LINQ to SQL N-Tier with Web Services</span></span>](linq-to-sql-n-tier-with-web-services.md)

- [<span data-ttu-id="3881f-119">N 계층 비즈니스 논리 구현</span><span class="sxs-lookup"><span data-stu-id="3881f-119">Implementing N-Tier Business Logic</span></span>](implementing-business-logic-linq-to-sql.md)

- [<span data-ttu-id="3881f-120">N 계층 애플리케이션에서 데이터 검색 및 CUD 작업(LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="3881f-120">Data Retrieval and CUD Operations in N-Tier Applications (LINQ to SQL)</span></span>](data-retrieval-and-cud-operations-in-n-tier-applications.md)

 <span data-ttu-id="3881f-121">ADO.NET 데이터 집합을 사용 하는 n 계층 응용 프로그램에 대 한 자세한 내용은 [n 계층 응용 프로그램에서 데이터 집합 작업](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3881f-121">For more information about n-tier applications that use ADO.NET DataSets, see [Work with datasets in n-tier applications](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications).</span></span>

## <a name="see-also"></a><span data-ttu-id="3881f-122">참조</span><span class="sxs-lookup"><span data-stu-id="3881f-122">See also</span></span>

- [<span data-ttu-id="3881f-123">배경 정보</span><span class="sxs-lookup"><span data-stu-id="3881f-123">Background Information</span></span>](background-information.md)
