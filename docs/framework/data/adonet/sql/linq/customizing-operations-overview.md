---
description: '자세한 정보: 작업 사용자 지정: 개요'
title: '작업 사용자 지정: 개요'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: bdcaf482f49b9c55fb7a1834b19b683ac2fa16bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729603"
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="a8e58-103">작업 사용자 지정: 개요</span><span class="sxs-lookup"><span data-stu-id="a8e58-103">Customizing Operations: Overview</span></span>

<span data-ttu-id="a8e58-104">기본적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 매핑을 기반으로 하는 삽입, 업데이트 및 삭제 작업을 위한 동적 SQL을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e58-104">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="a8e58-105">그러나 실제로는 사용자 고유의 비즈니스 논리를 추가하여 보안, 유효성 검사 등을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e58-105">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 <span data-ttu-id="a8e58-106">이러한 작업을 사용자 지정하는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8e58-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="a8e58-107">로드 옵션</span><span class="sxs-lookup"><span data-stu-id="a8e58-107">Loading Options</span></span>  

 <span data-ttu-id="a8e58-108">쿼리에서 데이터베이스에 연결할 때 검색되는 주 대상에 관련된 데이터의 양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8e58-108">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="a8e58-109">이 기능은 <xref:System.Data.Linq.DataLoadOptions>를 사용하여 대규모로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8e58-109">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="a8e58-110">자세한 내용은 [지연 된 로드 및 즉시 로드](deferred-versus-immediate-loading.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8e58-110">For more information, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="a8e58-111">부분 메서드</span><span class="sxs-lookup"><span data-stu-id="a8e58-111">Partial Methods</span></span>  

 <span data-ttu-id="a8e58-112">해당 기본 매핑에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 사용자 비즈니스 논리를 구현하는 데 도움이 되는 부분 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e58-112">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="a8e58-113">자세한 내용은 [부분 메서드를 사용 하 여 비즈니스 논리 추가](adding-business-logic-by-using-partial-methods.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8e58-113">For more information, see [Adding Business Logic By Using Partial Methods](adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="a8e58-114">저장 프로시저 및 사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="a8e58-114">Stored Procedures and User-Defined Functions</span></span>  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a8e58-115">에서는 저장 프로시저 및 사용자 정의 함수의 사용을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e58-115">supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="a8e58-116">저장 프로시저는 작업을 사용자 지정하는 데 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8e58-116">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="a8e58-117">자세한 내용은 [저장 프로시저](stored-procedures.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8e58-117">For more information, see [Stored Procedures](stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e58-118">참조</span><span class="sxs-lookup"><span data-stu-id="a8e58-118">See also</span></span>

- [<span data-ttu-id="a8e58-119">삽입, 업데이트 및 삭제 작업을 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a8e58-119">Customizing Insert, Update, and Delete Operations</span></span>](customizing-insert-update-and-delete-operations.md)
