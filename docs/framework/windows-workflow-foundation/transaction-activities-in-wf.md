---
description: '자세한 정보: WF의 트랜잭션 활동'
title: WF의 트랜잭션 활동
ms.date: 03/30/2017
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
ms.openlocfilehash: f088c586998d3dbec8b94dcf0f02603a68b55a40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755137"
---
# <a name="transaction-activities-in-wf"></a><span data-ttu-id="487df-103">WF의 트랜잭션 활동</span><span class="sxs-lookup"><span data-stu-id="487df-103">Transaction Activities in WF</span></span>

<span data-ttu-id="487df-104">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]에는 모델링 트랜잭션, 보정 및 취소에 대한 여러 가지 시스템 제공 활동이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487df-104">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] has several system-provided activities for modeling transactions, compensation, and cancellation.</span></span> <span data-ttu-id="487df-105">이러한 프로그래밍 모델을 사용하면 워크플로가 비즈니스 논리 및 오류 처리에 변경이 있는 경우 프로세스를 계속 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487df-105">These programming models allow the workflow to continue forward progress in the event of changes in business logic and error handling.</span></span> <span data-ttu-id="487df-106">트랜잭션, 보정 및 취소에 대 한 자세한 내용은 [트랜잭션](workflow-transactions.md), [보정](compensation.md)및 [취소](modeling-cancellation-behavior-in-workflows.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="487df-106">For more information about transactions, compensation, and cancellation, see [Transactions](workflow-transactions.md), [Compensation](compensation.md), and [Cancellation](modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
## <a name="transaction-activities"></a><span data-ttu-id="487df-107">트랜잭션 활동</span><span class="sxs-lookup"><span data-stu-id="487df-107">Transaction Activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|<span data-ttu-id="487df-108">활동 형식의 취소 논리를 역시 활동으로 표현되는 주 실행 경로와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="487df-108">Associates cancellation logic, in the form of an activity, with a main path of execution, also expressed as an activity.</span></span>|  
|<xref:System.Activities.Statements.CompensableActivity>|<span data-ttu-id="487df-109">자식 활동의 보정을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="487df-109">Supports compensation of its child activities.</span></span>|  
|<xref:System.Activities.Statements.Compensate>|<span data-ttu-id="487df-110"><xref:System.Activities.Statements.CompensableActivity>의 보정 처리기를 명시적으로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="487df-110">Explicitly invokes the compensation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.Confirm>|<span data-ttu-id="487df-111"><xref:System.Activities.Statements.CompensableActivity>의 확인 처리기를 명시적으로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="487df-111">Explicitly invokes the confirmation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.TransactionScope>|<span data-ttu-id="487df-112">트랜잭션 경계를 정합니다.</span><span class="sxs-lookup"><span data-stu-id="487df-112">Demarcates a transaction boundary.</span></span>|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|<span data-ttu-id="487df-113">수신한 메시지로 시작되는 트랜잭션 수명의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="487df-113">Scopes the lifetime of a transaction that is initiated by a received message.</span></span> <span data-ttu-id="487df-114">트랜잭션은 시작 메시지의 워크플로로 이동하거나 메시지를 수신했을 때 디스패처로 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487df-114">The transaction may be flowed into the workflow on the initiating message, or created by the dispatcher when the message is received.</span></span> <span data-ttu-id="487df-115">**참고:**  는 <xref:System.ServiceModel.Activities.TransactedReceiveScope> **도구 상자** 의 **메시징** 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487df-115">**Note:**  The <xref:System.ServiceModel.Activities.TransactedReceiveScope> is located in the **Messaging** section of the **Toolbox**.</span></span>|
