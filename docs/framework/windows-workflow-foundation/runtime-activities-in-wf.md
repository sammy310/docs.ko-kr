---
description: '자세한 정보: WF의 런타임 작업'
title: WF의 런타임 활동
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: 5ff164539b9efd7b2b8a4e7cffd5239eae6145fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792637"
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="2fea6-103">WF의 런타임 활동</span><span class="sxs-lookup"><span data-stu-id="2fea6-103">Runtime Activities in WF</span></span>

[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<span data-ttu-id="2fea6-104">는 지속성 및 종료와 같이 워크플로 런타임의 기능에 액세스하기 위한 여러 시스템 제공 활동을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2fea6-104">provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="2fea6-105">작업</span><span class="sxs-lookup"><span data-stu-id="2fea6-105">Activity</span></span>|<span data-ttu-id="2fea6-106">Description</span><span class="sxs-lookup"><span data-stu-id="2fea6-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="2fea6-107">워크플로가 상태를 유지하도록 명시적으로 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="2fea6-107">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="2fea6-108">실행 중인 워크플로 인스턴스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="2fea6-108">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="2fea6-109">자식 활동이 유지되지 않도록 하는 컨테이너 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="2fea6-109">A container activity that prevents child activities from persisting.</span></span>|
