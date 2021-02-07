---
description: '자세히 알아보기: 명령을 사용 하 여 데이터 수정'
title: 명령을 사용하여 데이터 수정
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: 3addcb93850aa8e26fe441b5c859502779433bfb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766558"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="c948f-103">명령을 사용하여 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="c948f-103">Using Commands to Modify Data</span></span>

<span data-ttu-id="c948f-104">.NET Framework 데이터 공급자를 사용하여 저장 프로시저나 CREATE TABLE 및 ALTER COLUMN과 같은 데이터 정의 언어 문을 실행하여 데이터베이스 또는 카탈로그의 스키마를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c948f-104">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="c948f-105">이러한 명령은 행을 쿼리로 반환 하지 않으므로 **Command** 개체는이를 처리 하는 **ExecuteNonQuery** 을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c948f-105">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="c948f-106">**ExecuteNonQuery** 메서드를 사용하면 스키마를 수정하는 것 외에, 데이터를 수정하지만 행을 반환하지 않는 INSERT, UPDATE, DELETE 등의 SQL 문을 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c948f-106">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="c948f-107">**ExecuteNonQuery** 메서드는 행을 반환하지 않지만 **Command** 개체의 **Parameters** 컬렉션을 통해 입력 및 출력 매개 변수와 반환 값을 전달하고 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c948f-107">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c948f-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c948f-108">In This Section</span></span>  

 [<span data-ttu-id="c948f-109">데이터 원본에서 데이터 업데이트</span><span class="sxs-lookup"><span data-stu-id="c948f-109">Updating Data in a Data Source</span></span>](updating-data-in-a-data-source.md)  
 <span data-ttu-id="c948f-110">데이터베이스의 데이터를 수정하는 명령 또는 저장 프로시저를 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c948f-110">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="c948f-111">카탈로그 작업 수행</span><span class="sxs-lookup"><span data-stu-id="c948f-111">Performing Catalog Operations</span></span>](performing-catalog-operations.md)  
 <span data-ttu-id="c948f-112">데이터베이스 스키마를 수정하는 명령을 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c948f-112">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c948f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c948f-113">See also</span></span>

- [<span data-ttu-id="c948f-114">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="c948f-114">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="c948f-115">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c948f-115">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="c948f-116">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="c948f-116">ADO.NET Overview</span></span>](ado-net-overview.md)
