---
description: '다음에 대 한 자세한 정보: 이진 파일 및 Large-Value 데이터 SQL Server'
title: SQL Server 이진 및 큰 값 데이터
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 8c7da5d504af0bc1beeea7e210a6fff4157fb090
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767442"
---
# <a name="sql-server-binary-and-large-value-data"></a><span data-ttu-id="ab597-103">SQL Server 이진 및 큰 값 데이터</span><span class="sxs-lookup"><span data-stu-id="ab597-103">SQL Server Binary and Large-Value Data</span></span>

<span data-ttu-id="ab597-104">SQL Server에서는 `varchar`, `nvarchar` 및 `varbinary` 데이터 형식의 스토리지 용량을 확장하는 `max` 지정자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab597-104">SQL Server provides the `max` specifier, which expands the storage capacity of the `varchar`, `nvarchar`, and `varbinary` data types.</span></span> <span data-ttu-id="ab597-105">`varchar(max)`, `nvarchar(max)` 및 `varbinary(max)`를 통칭하여 *큰 값 데이터 형식* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab597-105">`varchar(max)`, `nvarchar(max)`, and `varbinary(max)` are collectively called *large-value data types*.</span></span> <span data-ttu-id="ab597-106">큰 값 데이터 형식을 사용하여 최대 2^31-1바이트의 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab597-106">You can use the large-value data types to store up to 2^31-1 bytes of data.</span></span>  
  
 <span data-ttu-id="ab597-107">SQL Server 2008에서는 데이터 형식이 아닌 하나의 열에서 정의될 수 있는 특성인 FILESTREAM 특성을 소개하고 있으며, 이를 통해 데이터베이스 대신 파일 시스템에 큰 값 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab597-107">SQL Server 2008 introduces the FILESTREAM attribute, which is not a data type, but rather an attribute that can be defined on a column, allowing large-value data to be stored on the file system instead of in the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab597-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ab597-108">In This Section</span></span>  

 [<span data-ttu-id="ab597-109">ADO.NET에서 Large-Value (max) 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="ab597-109">Modifying Large-Value (max) Data in ADO.NET</span></span>](modifying-large-value-max-data.md)  
 <span data-ttu-id="ab597-110">큰 값 데이터 형식을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab597-110">Describes how to work with the large-value data types.</span></span>  
  
 [<span data-ttu-id="ab597-111">FILESTREAM 데이터</span><span class="sxs-lookup"><span data-stu-id="ab597-111">FILESTREAM Data</span></span>](filestream-data.md)  
 <span data-ttu-id="ab597-112">FILESTREAM 특성을 사용하여 SQL Server 2008에 저장된 큰 값 데이터를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab597-112">Describes how to work with large-value data stored in SQL Server 2008 with the FILESTREAM attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab597-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab597-113">See also</span></span>

- [<span data-ttu-id="ab597-114">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ab597-114">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="ab597-115">ADO.NET의 SQL Server 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="ab597-115">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="ab597-116">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="ab597-116">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="ab597-117">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="ab597-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
