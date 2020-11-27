---
title: 활동 클래스를 사용하여 워크플로 활동 제작
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 21f1c8b1249d41029fa7a19360e96ad866c823a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293847"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="4cf9c-102">활동 클래스를 사용하여 워크플로 활동 제작</span><span class="sxs-lookup"><span data-stu-id="4cf9c-102">Workflow Activity Authoring Using the Activity Class</span></span>

<span data-ttu-id="4cf9c-103">에서 WF (Windows Workflow Foundation)를 사용 하 여 활동을 만드는 가장 기본적인 방법은 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <xref:System.Activities.Activity> [기본 제공 활동 라이브러리](net-framework-4-5-built-in-activity-library.md)에서 사용자 지정 활동 또는 활동을 조합 하 여 기능을 만드는에서 상속 하는 클래스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-103">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="4cf9c-104">이 항목에서는 콘솔에 두 개의 메시지를 쓰는 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="4cf9c-105">활동 디자이너를 사용하여 사용자 지정 활동을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4cf9c-105">To create a custom Activity using the activity designer</span></span>

1. <span data-ttu-id="4cf9c-106">Visual Studio 2012을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-106">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="4cf9c-107">파일, 새로 만들기, 프로젝트를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-107">Select File, New, Project.</span></span> <span data-ttu-id="4cf9c-108">**프로젝트 형식** 창에서 **Visual c #** 아래에 있는 **Workflow 4.0** 을 선택 하 고 **v2010** 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="4cf9c-109">**템플릿** 창에서 **활동 라이브러리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="4cf9c-110">새 프로젝트의 이름을 HelloActivity로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-110">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="4cf9c-111">새 활동을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-111">Open the new activity.</span></span>  <span data-ttu-id="4cf9c-112">도구 상자의 <xref:System.Activities.Statements.Sequence> 활동을 디자이너 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>

4. <span data-ttu-id="4cf9c-113"><xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="4cf9c-114">`"Hello World"` **텍스트** 필드에 (따옴표 포함)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>

5. <span data-ttu-id="4cf9c-115">두 번째 <xref:System.Activities.Statements.WriteLine> 활동을 첫 번째 활동 아래의 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="4cf9c-116">`"Goodbye"` **텍스트** 필드에 (따옴표 포함)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf9c-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
