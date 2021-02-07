---
description: '자세한 정보: CLR User-Defined 형식'
title: CLR 사용자 정의 형식
ms.date: 03/30/2017
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
ms.openlocfilehash: f1732c254d3bf3cb8aa4ba727c420c46ef55c2cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663367"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="dcbd0-103">CLR 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="dcbd0-103">CLR User-Defined Types</span></span>

<span data-ttu-id="dcbd0-104">Microsoft SQL Server에서는 Microsoft .NET Framework CLR(공용 언어 런타임)로 구현된 UDT(사용자 정의 형식)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbd0-104">Microsoft SQL Server provides support for user-defined types (UDTs) implemented with the Microsoft .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="dcbd0-105">CLR은 SQL Server에 통합되어 있으며 이 메커니즘을 통해 데이터베이스의 형식 시스템을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbd0-105">The CLR is integrated into SQL Server, and this mechanism enables you to extend the type system of the database.</span></span> <span data-ttu-id="dcbd0-106">UDT는 SQL Server 데이터 형식 시스템에 대한 사용자 확장성 및 구조적 복합 형식을 정의할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbd0-106">UDTs provide user extensibility of the SQL Server data type system, and also the ability to define complex structured types.</span></span>  
  
 <span data-ttu-id="dcbd0-107">UDT는 애플리케이션 아키텍처 측면에서 다음과 같은 두 가지 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbd0-107">UDTs can provide two key benefits from an application architecture perspective:</span></span>  
  
- <span data-ttu-id="dcbd0-108">클라이언트와 서버에서 내부 상태 및 외부 동작 간의 강력한 캡슐화</span><span class="sxs-lookup"><span data-stu-id="dcbd0-108">Strong encapsulation (both in the client and the server) between the internal state and the external behaviors.</span></span>  
  
- <span data-ttu-id="dcbd0-109">다른 관련 서버 기능과의 밀접한 통합.</span><span class="sxs-lookup"><span data-stu-id="dcbd0-109">Deep integration with other related server features.</span></span> <span data-ttu-id="dcbd0-110">고유한 UDT를 정의하고 나면 열 정의를 포함한 SQL Server에 시스템 형식을 사용할 수 있는 경우 모든 컨텍스트에 사용할 수 있으며 변수, 매개 변수, 함수 결과, 커서, 트리거 및 복제로도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbd0-110">Once you define your own UDT, you can use it in all contexts where you can use a system type in SQL Server, including column definitions, and as variables, parameters, function results, cursors, triggers, and replication.</span></span>  
  
 <span data-ttu-id="dcbd0-111">자세한 내용은 사용 중인 SQL Server 버전에 대 한 [SQL Server 설명서](/sql) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dcbd0-111">For more detailed information, see the [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="dcbd0-112">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="dcbd0-112">**SQL Server documentation**</span></span>
  
1. [<span data-ttu-id="dcbd0-113">CLR 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="dcbd0-113">CLR User-Defined Types</span></span>](/sql/relational-databases/clr-integration-database-objects-user-defined-types/clr-user-defined-types)  
  
## <a name="see-also"></a><span data-ttu-id="dcbd0-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcbd0-114">See also</span></span>

- [<span data-ttu-id="dcbd0-115">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="dcbd0-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
