---
title: 팩터리 모델 개요
ms.date: 03/30/2017
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
ms.openlocfilehash: f344502453acbbb5c08e49b7c21a0f4e84a29ffa
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348395"
---
# <a name="factory-model-overview"></a><span data-ttu-id="f5282-102">팩터리 모델 개요</span><span class="sxs-lookup"><span data-stu-id="f5282-102">Factory Model Overview</span></span>
<span data-ttu-id="f5282-103">ADO.NET 2.0에서는 <xref:System.Data.Common> 네임스페이스에 새로운 기본 클래스가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5282-103">ADO.NET 2.0 introduced new base classes in the <xref:System.Data.Common> namespace.</span></span> <span data-ttu-id="f5282-104">이러한 기본 클래스는 추상적이기 때문에 직접 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5282-104">The base classes are abstract, which means that they can't be directly instantiated.</span></span> <span data-ttu-id="f5282-105">여기에는 <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand> 및 <xref:System.Data.Common.DbDataAdapter>가 포함되며 세 클래스 모두 <xref:System.Data.SqlClient> 및 <xref:System.Data.OleDb>와 같은 .NET Framework 데이터 공급자에서 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5282-105">They include <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand>, and <xref:System.Data.Common.DbDataAdapter> and are shared by the .NET Framework data providers, such as <xref:System.Data.SqlClient> and <xref:System.Data.OleDb>.</span></span> <span data-ttu-id="f5282-106">기본 클래스를 사용하면 새 인터페이스를 만들 필요 없이 .NET Framework 데이터 공급자에 기능을 간편하게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5282-106">The addition of base classes simplifies adding functionality to the .NET Framework data providers without having to create new interfaces.</span></span>  
  
 <span data-ttu-id="f5282-107">또한 ADO.NET 2.0에서는 추상 기본 클래스가 도입되어 개발자가 특정 데이터 공급자에 한정되지 않는 제네릭 데이터 액세스 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5282-107">ADO.NET 2.0 also introduced abstract base classes, which enable a developer to write generic data access code that does not depend on a specific data provider.</span></span>  
  
## <a name="the-factory-design-pattern"></a><span data-ttu-id="f5282-108">팩터리 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="f5282-108">The Factory Design Pattern</span></span>  
 <span data-ttu-id="f5282-109">공급자에 독립적인 코드를 작성하기 위한 프로그래밍 모델은 단일 API를 사용하여 여러 공급자의 데이터베이스에 액세스하는 "팩터리" 디자인 패턴을 기본적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f5282-109">The programming model for writing provider-independent code is based on the use of the "factory" design pattern, which uses a single API to access databases across multiple providers.</span></span> <span data-ttu-id="f5282-110">이 패턴은 이름에서 알 수 있듯이 실제 팩터리와 마찬가지로 다른 개체를 만들기 위해서만 특수 개체를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5282-110">This pattern is aptly named, as it calls for the use of a specialized object solely to create other objects, much like a real-world factory.</span></span> <span data-ttu-id="f5282-111">팩터리 디자인 패턴에 대 한 자세한 설명은 [ASP.NET 2.0 및 ADO.NET 2.0에서 일반 데이터 액세스 코드 작성](https://docs.microsoft.com/previous-versions/dotnet/articles/ms971499(v=msdn.10))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f5282-111">For a more detailed description of the factory design pattern, see [Writing Generic Data Access Code in ASP.NET 2.0 and ADO.NET 2.0](https://docs.microsoft.com/previous-versions/dotnet/articles/ms971499(v=msdn.10)).</span></span>
  
 <span data-ttu-id="f5282-112">ADO.NET 2.0부터 <xref:System.Data.Common.DbProviderFactories> 클래스는 `static` 인스턴스를 만드는 `Shared`(Visual Basic의 경우 <xref:System.Data.Common.DbProviderFactory>) 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f5282-112">Starting with ADO.NET 2.0, the <xref:System.Data.Common.DbProviderFactories> class provides `static` (or `Shared` in Visual Basic) methods for creating a <xref:System.Data.Common.DbProviderFactory> instance.</span></span> <span data-ttu-id="f5282-113">그러면 이 인스턴스는 런타임에 제공되는 공급자 정보와 연결 문자열을 기반으로 강력한 형식의 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f5282-113">The instance then returns a correct strongly typed object based on provider information and the connection string supplied at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5282-114">참조</span><span class="sxs-lookup"><span data-stu-id="f5282-114">See also</span></span>

- [<span data-ttu-id="f5282-115">DbProviderFactory 가져오기</span><span class="sxs-lookup"><span data-stu-id="f5282-115">Obtaining a DbProviderFactory</span></span>](obtaining-a-dbproviderfactory.md)
- [<span data-ttu-id="f5282-116">DbConnection, DbCommand 및 DbException</span><span class="sxs-lookup"><span data-stu-id="f5282-116">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="f5282-117">DbDataAdapter로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="f5282-117">Modifying Data with a DbDataAdapter</span></span>](modifying-data-with-a-dbdataadapter.md)
- [<span data-ttu-id="f5282-118">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="f5282-118">ADO.NET Overview</span></span>](ado-net-overview.md)
