---
title: 예외, 트랜잭션 및 보정
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: 2d8574c0f0f6bd3f66214367c1ed15292adc24a9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280249"
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="3dd28-102">예외, 트랜잭션 및 보정</span><span class="sxs-lookup"><span data-stu-id="3dd28-102">Exceptions, Transactions, and Compensation</span></span>

[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="3dd28-103">에서는 워크플로에서 런타임 오류 조건을 처리하는 다양한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3dd28-103">provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="3dd28-104">워크플로에서는 예외 처리기, 트랜잭션, 취소 및 보정을 함께 사용하여 오류 조건을 정상적으로 처리 및 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dd28-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3dd28-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="3dd28-105">In This Section</span></span>  

 [<span data-ttu-id="3dd28-106">예외</span><span class="sxs-lookup"><span data-stu-id="3dd28-106">Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="3dd28-107"><xref:System.Activities.Statements.TryCatch> 활동을 사용하여 워크플로에서 예외를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3dd28-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="3dd28-108">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="3dd28-108">Transactions</span></span>](workflow-transactions.md)  
 <span data-ttu-id="3dd28-109"><xref:System.Activities.Statements.TransactionScope> 활동을 사용하여 워크플로에서 트랜잭션을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3dd28-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="3dd28-110">보정</span><span class="sxs-lookup"><span data-stu-id="3dd28-110">Compensation</span></span>](compensation.md)  
 <span data-ttu-id="3dd28-111">워크플로의 보정에 대해 설명하고 <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, <xref:System.Activities.Statements.Confirm> 등과 같은 보정 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3dd28-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="3dd28-112">취소</span><span class="sxs-lookup"><span data-stu-id="3dd28-112">Cancellation</span></span>](modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="3dd28-113">기본 제공 활동과 사용자 지정 활동을 사용하여 워크플로에서 취소를 처리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3dd28-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="3dd28-114">워크플로 디버깅</span><span class="sxs-lookup"><span data-stu-id="3dd28-114">Debugging Workflows</span></span>](debugging-workflows.md)  
 <span data-ttu-id="3dd28-115">워크플로를 디버깅하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3dd28-115">Describes how to debug workflows.</span></span>
