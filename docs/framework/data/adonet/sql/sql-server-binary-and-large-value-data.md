---
title: SQL Server 이진 및 큰 값 데이터
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 4d941ad6b7865112b45fd8c20ad89e9236e17b9d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791678"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="f7f87-102">SQL Server 이진 및 큰 값 데이터</span><span class="sxs-lookup"><span data-stu-id="f7f87-102">SQL Server Binary and Large-Value Data</span></span>
<span data-ttu-id="f7f87-103">SQL Server에서는 `max`, `varchar` 및 `nvarchar` 데이터 형식의 스토리지 용량을 확장하는 `varbinary` 지정자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f87-103">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="f7f87-104">`varchar(max)`, `nvarchar(max)`및를 `varbinary(max)` 통칭 하 여 *대량 값 데이터 형식*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f87-104">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="f7f87-105">큰 값 데이터 형식을 사용하면 데이터를 최대 2^31-1바이트까지 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f87-105">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="f7f87-106">SQL Server 2008에서는 데이터 형식은 아니고 열에 정의할 수 있는 특성인 FILESTREAM 특성을 지원합니다. 이 특성을 사용하면 큰 값 데이터를 데이터베이스가 아니라 파일 시스템에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f87-106">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7f87-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f7f87-107">In This Section</span></span>  
 [<span data-ttu-id="f7f87-108">ADO.NET에서 큰 값(최대값) 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="f7f87-108">Modifying Large-Value (max) Data in ADO.NET</span></span>](modifying-large-value-max-data.md)  
 <span data-ttu-id="f7f87-109">큰 값 데이터 형식을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f87-109">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="f7f87-110">FILESTREAM 데이터</span><span class="sxs-lookup"><span data-stu-id="f7f87-110">FILESTREAM Data</span></span>](filestream-data.md)  
 <span data-ttu-id="f7f87-111">FILESTREAM 특성을 사용하여 SQL Server 2008에 저장된 큰 값 데이터로 작업하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f87-111">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f87-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="f7f87-112">See also</span></span>

- [<span data-ttu-id="f7f87-113">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7f87-113">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="f7f87-114">ADO.NET에서 SQL Server 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="f7f87-114">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="f7f87-115">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="f7f87-115">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="f7f87-116">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="f7f87-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
