---
description: '방법에 대 한 자세한 정보: 방법: 동적으로 데이터베이스 만들기'
title: '방법: 동적으로 데이터베이스 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb7f23c4-4572-4c38-9898-a287807d070c
ms.openlocfilehash: b9addce6befc63f91358d6ecae57e40d6123b200
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738977"
---
# <a name="how-to-dynamically-create-a-database"></a><span data-ttu-id="9d506-103">방법: 동적으로 데이터베이스 만들기</span><span class="sxs-lookup"><span data-stu-id="9d506-103">How to: Dynamically Create a Database</span></span>

<span data-ttu-id="9d506-104">LINQ to SQL에서 개체 모델은 관계형 데이터베이스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-104">In LINQ to SQL, an object model is mapped to a relational database.</span></span> <span data-ttu-id="9d506-105">매핑은 특성 기반 매핑 또는 외부 매핑 파일을 사용하여 설정되며 이러한 매핑을 통해 관계형 데이터베이스의 구조를 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-105">Mapping is enabled by using attribute-based mapping or an external mapping file to describe the structure of the relational database.</span></span> <span data-ttu-id="9d506-106">두 경우 모두 관계형 데이터베이스에 대한 정보가 충분하므로 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 메서드를 사용하여 데이터베이스의 새 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-106">In both scenarios, there is enough information about the relational database that you can create a new instance of the database using the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="9d506-107"><xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 메서드는 개체 모델에 인코딩된 정보의 범위 내에서만 데이터베이스 복제본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-107">The <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method creates a replica of the database only to the extent of the information encoded in the object model.</span></span> <span data-ttu-id="9d506-108">개체 모델의 특성 및 매핑 파일이 기존 데이터베이스 구조에 대한 모든 사항을 인코딩하지는 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-108">Mapping files and attributes from your object model might not encode everything about the structure of an existing database.</span></span> <span data-ttu-id="9d506-109">매핑 정보는 사용자 정의 함수, 저장 프로시저, 트리거 또는 CHECK 제약 조건의 내용을 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-109">Mapping information does not represent the contents of user-defined functions, stored procedures, triggers, or check constraints.</span></span> <span data-ttu-id="9d506-110">다양한 데이터베이스에서 이 동작으로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-110">This behavior is sufficient for a variety of databases.</span></span>  
  
 <span data-ttu-id="9d506-111">Microsoft SQL Server 2008과 같은 데이터 공급자를 사용할 수 있는 경우에는 특히 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 메서드를 다양한 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-111">You can use the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method in any number of scenarios, especially if a known data provider like Microsoft SQL Server 2008 is available.</span></span> <span data-ttu-id="9d506-112">일반적인 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-112">Typical scenarios include the following:</span></span>  
  
- <span data-ttu-id="9d506-113">고객 시스템에 자동으로 설치되는 애플리케이션을 빌드하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-113">You are building an application that automatically installs itself on a customer system.</span></span>  
  
- <span data-ttu-id="9d506-114">오프라인 상태를 저장하기 위해 로컬 데이터베이스가 필요한 클라이언트 애플리케이션을 빌드하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-114">You are building a client application that needs a local database to save its offline state.</span></span>  
  
 <span data-ttu-id="9d506-115">또한 연결 문자열에 따라 .mdf 파일을 사용하거나 카탈로그 이름을 사용하여 SQL Server에서 <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-115">You can also use the <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType> method with SQL Server by using an .mdf file or a catalog name, depending on your connection string.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="9d506-116">에서는 연결 문자열을 사용하여 만들려는 데이터베이스와 해당 데이터베이스를 만들 대상 서버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-116">uses the connection string to define the database to be created and on which server the database is to be created.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d506-117">가능한 경우 연결 문자열에 암호를 사용할 필요가 없도록 Windows 통합 보안을 사용하여 데이터베이스에 연결하세요.</span><span class="sxs-lookup"><span data-stu-id="9d506-117">Whenever possible, use Windows Integrated Security to connect to the database so that passwords are not required in the connection string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d506-118">예제</span><span class="sxs-lookup"><span data-stu-id="9d506-118">Example</span></span>  

 <span data-ttu-id="9d506-119">다음 코드에서는 MyDVDs.mdf라는 새 데이터베이스를 만드는 방법에 대한 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-119">The following code provides an example of how to create a new database named MyDVDs.mdf.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#5)]
 [!code-vb[DLinqSubmittingChanges#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="9d506-120">예제</span><span class="sxs-lookup"><span data-stu-id="9d506-120">Example</span></span>  

 <span data-ttu-id="9d506-121">다음과 같이 개체 모델을 사용하여 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-121">You can use the object model to create a database by doing the following:</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#6)]
 [!code-vb[DLinqSubmittingChanges#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="9d506-122">예제</span><span class="sxs-lookup"><span data-stu-id="9d506-122">Example</span></span>  

 <span data-ttu-id="9d506-123">고객 시스템에 자동으로 설치되는 애플리케이션을 빌드하는 경우에는 해당 데이터베이스가 이미 있는지 확인하여 새 데이터베이스를 만들기 전에 이를 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-123">When building an application that automatically installs itself on a  customer system, see if the database already exists and drop it before creating a new one.</span></span> <span data-ttu-id="9d506-124"><xref:System.Data.Linq.DataContext> 클래스는 이 프로세스를 구현하는 데 도움이 되는 <xref:System.Data.Linq.DataContext.DatabaseExists%2A> 메서드와 <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-124">The <xref:System.Data.Linq.DataContext> class provides the <xref:System.Data.Linq.DataContext.DatabaseExists%2A> and <xref:System.Data.Linq.DataContext.DeleteDatabase%2A> methods to help you with this process.</span></span>  
  
 <span data-ttu-id="9d506-125">다음 예제에서는 이러한 메서드를 사용하여 이를 구현하는 한 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d506-125">The following example shows one way these methods can be used to implement this approach:</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#7)]
 [!code-vb[DLinqSubmittingChanges#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="9d506-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d506-126">See also</span></span>

- [<span data-ttu-id="9d506-127">특성 기반 매핑</span><span class="sxs-lookup"><span data-stu-id="9d506-127">Attribute-Based Mapping</span></span>](attribute-based-mapping.md)
- [<span data-ttu-id="9d506-128">외부 매핑</span><span class="sxs-lookup"><span data-stu-id="9d506-128">External Mapping</span></span>](external-mapping.md)
- [<span data-ttu-id="9d506-129">SQL-CLR 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="9d506-129">SQL-CLR Type Mapping</span></span>](sql-clr-type-mapping.md)
- [<span data-ttu-id="9d506-130">배경 정보</span><span class="sxs-lookup"><span data-stu-id="9d506-130">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="9d506-131">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="9d506-131">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
