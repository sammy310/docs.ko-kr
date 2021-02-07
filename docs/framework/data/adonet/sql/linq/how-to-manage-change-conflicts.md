---
description: '자세한 정보: 방법: 변경 내용 충돌 관리'
title: '방법: 변경 충돌 관리'
ms.date: 03/30/2017
ms.assetid: cd292c51-a3d1-4c6f-8d8e-04323c36054e
ms.openlocfilehash: 9b4afe5538d74dea574451d8678c07e0aa50198c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672064"
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="8c8f1-103">방법: 변경 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="8c8f1-103">How to: Manage Change Conflicts</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="8c8f1-104">동시성 충돌을 검색 하 고, 평가 하 고, 해결 하는 데 도움이 되는 Api 컬렉션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8f1-104">provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c8f1-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="8c8f1-105">In This Section</span></span>  

 [<span data-ttu-id="8c8f1-106">방법: 충돌하는 전송 검색 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8c8f1-106">How to: Detect and Resolve Conflicting Submissions</span></span>](how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="8c8f1-107">동시성 충돌을 검색하고 해결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8f1-107">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="8c8f1-108">방법: 동시성 예외가 throw되는 시기 지정</span><span class="sxs-lookup"><span data-stu-id="8c8f1-108">How to: Specify When Concurrency Exceptions are Thrown</span></span>](how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="8c8f1-109">동시성 충돌에 대해 알림을 받아야 할 경우를 지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8f1-109">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="8c8f1-110">방법: 동시성 충돌을 테스트할 멤버 지정</span><span class="sxs-lookup"><span data-stu-id="8c8f1-110">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="8c8f1-111">동시성 충돌 확인 여부를 지정하기 위해 멤버에 특성을 부여하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8f1-111">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="8c8f1-112">방법: 엔터티 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="8c8f1-112">How to: Retrieve Entity Conflict Information</span></span>](how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="8c8f1-113">엔터티 충돌에 대한 정보를 수집하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8f1-113">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="8c8f1-114">방법: 멤버 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="8c8f1-114">How to: Retrieve Member Conflict Information</span></span>](how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="8c8f1-115">멤버 충돌에 대한 정보를 수집하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8f1-115">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="8c8f1-116">방법: 데이터베이스 값을 유지하여 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="8c8f1-116">How to: Resolve Conflicts by Retaining Database Values</span></span>](how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="8c8f1-117">현재 값을 데이터베이스 값에 덮어쓰는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8f1-117">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="8c8f1-118">방법: 데이터베이스 값을 덮어써서 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="8c8f1-118">How to: Resolve Conflicts by Overwriting Database Values</span></span>](how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="8c8f1-119">데이터베이스 값을 덮어써 현재 값을 유지하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8f1-119">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="8c8f1-120">방법: 데이터베이스 값을 병합하여 충돌 해결</span><span class="sxs-lookup"><span data-stu-id="8c8f1-120">How to: Resolve Conflicts by Merging with Database Values</span></span>](how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="8c8f1-121">데이터베이스와 현재 값을 병합하여 충돌을 해결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8f1-121">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8c8f1-122">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="8c8f1-122">Related Sections</span></span>  

 [<span data-ttu-id="8c8f1-123">낙관적 동시성: 개요</span><span class="sxs-lookup"><span data-stu-id="8c8f1-123">Optimistic Concurrency: Overview</span></span>](optimistic-concurrency-overview.md)  
 <span data-ttu-id="8c8f1-124">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 낙관적 동시성에 적용하는 용어를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c8f1-124">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
