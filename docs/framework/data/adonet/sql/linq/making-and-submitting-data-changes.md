---
description: '자세한 정보: 데이터 변경 설정 및 전송'
title: 데이터 변경 및 변경 내용 전송
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: 260dab911057b45250d44ded7c254dd903e2aed7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695574"
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="e8273-103">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="e8273-103">Making and Submitting Data Changes</span></span>

<span data-ttu-id="e8273-104">이 단원의 항목에서는 데이터베이스에 변경 내용을 만들고 전송하는 방법과 낙관적 동시성 충돌을 처리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8273-104">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>

> [!NOTE]
> <span data-ttu-id="e8273-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], `Insert` 및 `Update` 데이터베이스 작업에 대한 `Delete` 기본 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8273-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="e8273-106">자세한 내용은 [삽입, 업데이트 및 삭제 작업 사용자 지정](customizing-insert-update-and-delete-operations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8273-106">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="e8273-107">Visual Studio를 사용 하는 개발자는 개체 관계형 디자이너을 사용 하 여 동일한 목적으로 저장 프로시저를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8273-107">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e8273-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e8273-108">In This Section</span></span>

<span data-ttu-id="e8273-109">[방법: 데이터베이스에 행 삽입](how-to-insert-rows-into-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="e8273-109">[How to: Insert Rows Into the Database](how-to-insert-rows-into-the-database.md) </span></span>\
<span data-ttu-id="e8273-110">개체 모델에 개체를 추가하여 데이터베이스에 행을 삽입하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8273-110">Describes how to insert rows in the database by adding objects to the object model.</span></span>

<span data-ttu-id="e8273-111">[방법: 데이터베이스에서 행 업데이트](how-to-update-rows-in-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="e8273-111">[How to: Update Rows in the Database](how-to-update-rows-in-the-database.md) </span></span>\
<span data-ttu-id="e8273-112">개체 모델에 개체를 업데이트하여 데이터베이스에 행을 업데이트하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8273-112">Describes how to update rows in the database by updating objects in the object model.</span></span>

<span data-ttu-id="e8273-113">[방법: 데이터베이스에서 행 삭제](how-to-delete-rows-from-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="e8273-113">[How to: Delete Rows From the Database](how-to-delete-rows-from-the-database.md) </span></span>\
<span data-ttu-id="e8273-114">개체 모델에서 개체를 삭제하여 데이터베이스의 행을 삭제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8273-114">Describes how to delete rows in the database by deleting objects in the object model.</span></span>

<span data-ttu-id="e8273-115">[방법: 데이터베이스에 변경 내용 전송](how-to-submit-changes-to-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="e8273-115">[How to: Submit Changes to the Database](how-to-submit-changes-to-the-database.md) </span></span>\
<span data-ttu-id="e8273-116">데이터베이스에 개체 모델 변경 내용을 보내는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8273-116">Describes how to send object-model changes to the database.</span></span>

<span data-ttu-id="e8273-117">[방법: 트랜잭션을 사용 하 여 데이터의 괄호를 사용 하 여 데이터 전송](how-to-bracket-data-submissions-by-using-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="e8273-117">[How to: Bracket Data Submissions by Using Transactions](how-to-bracket-data-submissions-by-using-transactions.md) </span></span>\
<span data-ttu-id="e8273-118">트랜젝션에 작업을 포함시키는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8273-118">Describes how to include operations in a transaction.</span></span>

<span data-ttu-id="e8273-119">[방법: 동적으로 데이터베이스 만들기](how-to-dynamically-create-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="e8273-119">[How to: Dynamically Create a Database](how-to-dynamically-create-a-database.md) </span></span>\
<span data-ttu-id="e8273-120">동적으로 데이터베이스를 생성하고 이 방법에 대한 일반적인 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8273-120">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>

<span data-ttu-id="e8273-121">[방법: 변경 내용 충돌 관리](how-to-manage-change-conflicts.md) </span><span class="sxs-lookup"><span data-stu-id="e8273-121">[How to: Manage Change Conflicts](how-to-manage-change-conflicts.md) </span></span>\
<span data-ttu-id="e8273-122">낙관적 동시성 문제를 해결하는 기술에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8273-122">Describes techniques for addressing optimistic concurrency issues.</span></span>
