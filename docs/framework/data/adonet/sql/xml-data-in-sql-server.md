---
title: SQL Server의 XML 데이터
ms.date: 03/30/2017
ms.assetid: 9849d319-f518-4e3d-a7cd-f8fdcaaa1d4d
ms.openlocfilehash: 8ad92334a2afd4791bb0b40378c49a0efa14fefd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147608"
---
# <a name="xml-data-in-sql-server"></a><span data-ttu-id="c361f-102">SQL Server의 XML 데이터</span><span class="sxs-lookup"><span data-stu-id="c361f-102">XML Data in SQL Server</span></span>

<span data-ttu-id="c361f-103">SQL Server에서는 .NET Framework 내에 SQLXML의 기능을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="c361f-103">SQL Server exposes the functionality of SQLXML inside the .NET Framework.</span></span> <span data-ttu-id="c361f-104">개발자는 SQL Server 인스턴스에서 XML 데이터에 액세스하고 데이터를 .NET Framework 환경으로 가져와 처리한 다음 업데이트를 다시 SQL Server로 보내는 애플리케이션을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c361f-104">Developers can write applications that access XML data from an instance of SQL Server, bring the data into the .NET Framework environment, process the data, and send the updates back to SQL Server.</span></span> <span data-ttu-id="c361f-105">SQL Server에서는 데이터 스토리지 및 데이터 검색을 위한 매개 변수 값을 비롯하여 여러 가지 방식으로 XML 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c361f-105">XML data can be used in several ways in SQL Server, including data storage, and as parameter values for retrieving data.</span></span> <span data-ttu-id="c361f-106">.NET Framework의 **SqlXml** 클래스는 SQL SERVER 내의 XML 열에 저장 된 데이터로 작업 하기 위한 클라이언트 쪽 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c361f-106">The **SqlXml** class in the .NET Framework provides the client-side support for working with data stored in an XML column within SQL Server.</span></span> <span data-ttu-id="c361f-107">자세한 내용은 SQL Server 온라인 설명서의 "SQLXML 관리되는 클래스"를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c361f-107">For more information, see "SQLXML Managed Classes" in SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c361f-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c361f-108">In This Section</span></span>  

 [<span data-ttu-id="c361f-109">SQL XML 열 값</span><span class="sxs-lookup"><span data-stu-id="c361f-109">SQL XML Column Values</span></span>](sql-xml-column-values.md)  
 <span data-ttu-id="c361f-110">SQL Server에서 XML 데이터를 검색하고 검색한 데이터로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c361f-110">Demonstrates how to retrieve and work with XML data retrieved from SQL Server.</span></span>  
  
 [<span data-ttu-id="c361f-111">XML 값을 매개 변수로 지정</span><span class="sxs-lookup"><span data-stu-id="c361f-111">Specifying XML Values as Parameters</span></span>](specifying-xml-values-as-parameters.md)  
 <span data-ttu-id="c361f-112">하나의 명령에 XML 데이터를 매개 변수로서 전달하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c361f-112">Demonstrates how to pass XML data as a parameter to a command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c361f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c361f-113">See also</span></span>

- [<span data-ttu-id="c361f-114">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c361f-114">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="c361f-115">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="c361f-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
