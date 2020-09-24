---
title: 명령을 사용하여 데이터 수정
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: e2f61dbf74f28d026ae91a2bc8f5bb78530ffeac
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177256"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="0a0fe-102">명령을 사용하여 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="0a0fe-102">Using Commands to Modify Data</span></span>

<span data-ttu-id="0a0fe-103">.NET Framework 데이터 공급자를 사용하여 저장 프로시저나 CREATE TABLE 및 ALTER COLUMN과 같은 데이터 정의 언어 문을 실행하여 데이터베이스 또는 카탈로그의 스키마를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0fe-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="0a0fe-104">이러한 명령은 행을 쿼리로 반환 하지 않으므로 **Command** 개체는이를 처리 하는 **ExecuteNonQuery** 을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0fe-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="0a0fe-105">**ExecuteNonQuery** 를 사용 하 여 스키마를 수정 하는 것 외에도이 메서드를 사용 하 여 데이터를 수정 하지만 행을 반환 하지 않는 SQL 문 (예: 삽입, 업데이트 및 삭제)을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0fe-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="0a0fe-106">**ExecuteNonQuery** 메서드는 행을 반환 하지 않지만 **Command** 개체의 **parameters** 컬렉션을 통해 입력 및 출력 매개 변수와 반환 값을 전달 하 고 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a0fe-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a0fe-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0a0fe-107">In This Section</span></span>  

 [<span data-ttu-id="0a0fe-108">데이터 원본에서 데이터 업데이트</span><span class="sxs-lookup"><span data-stu-id="0a0fe-108">Updating Data in a Data Source</span></span>](updating-data-in-a-data-source.md)  
 <span data-ttu-id="0a0fe-109">데이터베이스의 데이터를 수정하는 명령 또는 저장 프로시저를 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0fe-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="0a0fe-110">카탈로그 작업 수행</span><span class="sxs-lookup"><span data-stu-id="0a0fe-110">Performing Catalog Operations</span></span>](performing-catalog-operations.md)  
 <span data-ttu-id="0a0fe-111">데이터베이스 스키마를 수정하는 명령을 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a0fe-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a0fe-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a0fe-112">See also</span></span>

- [<span data-ttu-id="0a0fe-113">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="0a0fe-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="0a0fe-114">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a0fe-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="0a0fe-115">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="0a0fe-115">ADO.NET Overview</span></span>](ado-net-overview.md)
