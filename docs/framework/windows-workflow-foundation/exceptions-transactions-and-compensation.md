---
description: '에 대 한 자세한 정보: 예외, 트랜잭션 및 보정'
title: 예외, 트랜잭션 및 보정
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: 3188b0238b1909847c289bb56274671ff4b307b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720191"
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="bf2c9-103">예외, 트랜잭션 및 보정</span><span class="sxs-lookup"><span data-stu-id="bf2c9-103">Exceptions, Transactions, and Compensation</span></span>

[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="bf2c9-104">에서는 워크플로에서 런타임 오류 조건을 처리하는 다양한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2c9-104">provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="bf2c9-105">워크플로에서는 예외 처리기, 트랜잭션, 취소 및 보정을 함께 사용하여 오류 조건을 정상적으로 처리 및 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf2c9-105">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bf2c9-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="bf2c9-106">In This Section</span></span>  

 [<span data-ttu-id="bf2c9-107">예외</span><span class="sxs-lookup"><span data-stu-id="bf2c9-107">Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="bf2c9-108"><xref:System.Activities.Statements.TryCatch> 활동을 사용하여 워크플로에서 예외를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf2c9-108">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="bf2c9-109">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="bf2c9-109">Transactions</span></span>](workflow-transactions.md)  
 <span data-ttu-id="bf2c9-110"><xref:System.Activities.Statements.TransactionScope> 활동을 사용하여 워크플로에서 트랜잭션을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf2c9-110">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="bf2c9-111">보정</span><span class="sxs-lookup"><span data-stu-id="bf2c9-111">Compensation</span></span>](compensation.md)  
 <span data-ttu-id="bf2c9-112">워크플로의 보정에 대해 설명하고 <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, <xref:System.Activities.Statements.Confirm> 등과 같은 보정 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf2c9-112">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="bf2c9-113">취소</span><span class="sxs-lookup"><span data-stu-id="bf2c9-113">Cancellation</span></span>](modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="bf2c9-114">기본 제공 활동과 사용자 지정 활동을 사용하여 워크플로에서 취소를 처리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2c9-114">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="bf2c9-115">워크플로 디버깅</span><span class="sxs-lookup"><span data-stu-id="bf2c9-115">Debugging Workflows</span></span>](debugging-workflows.md)  
 <span data-ttu-id="bf2c9-116">워크플로를 디버깅하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2c9-116">Describes how to debug workflows.</span></span>
