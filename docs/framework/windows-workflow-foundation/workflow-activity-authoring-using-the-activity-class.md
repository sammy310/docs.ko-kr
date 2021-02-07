---
description: '자세한 정보: 활동 클래스를 사용 하 여 워크플로 활동 제작'
title: 활동 클래스를 사용하여 워크플로 활동 제작
ms.date: 03/30/2017
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
ms.openlocfilehash: 0d3ffc88bacfd941dfa0c853991bf72045468323
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754942"
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="90068-103">활동 클래스를 사용하여 워크플로 활동 제작</span><span class="sxs-lookup"><span data-stu-id="90068-103">Workflow Activity Authoring Using the Activity Class</span></span>

<span data-ttu-id="90068-104">에서 WF (Windows Workflow Foundation)를 사용 하 여 활동을 만드는 가장 기본적인 방법은 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <xref:System.Activities.Activity> [기본 제공 활동 라이브러리](net-framework-4-5-built-in-activity-library.md)에서 사용자 지정 활동 또는 활동을 조합 하 여 기능을 만드는에서 상속 하는 클래스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="90068-104">The most basic way to create an activity using Windows Workflow Foundation (WF) in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="90068-105">이 항목에서는 콘솔에 두 개의 메시지를 쓰는 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90068-105">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="90068-106">활동 디자이너를 사용하여 사용자 지정 활동을 만들려면</span><span class="sxs-lookup"><span data-stu-id="90068-106">To create a custom Activity using the activity designer</span></span>

1. <span data-ttu-id="90068-107">Visual Studio 2012을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="90068-107">Open Visual Studio 2012.</span></span>

2. <span data-ttu-id="90068-108">파일, 새로 만들기, 프로젝트를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="90068-108">Select File, New, Project.</span></span> <span data-ttu-id="90068-109">**프로젝트 형식** 창에서 **Visual c #** 아래에 있는 **Workflow 4.0** 을 선택 하 고 **v2010** 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="90068-109">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="90068-110">**템플릿** 창에서 **활동 라이브러리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="90068-110">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="90068-111">새 프로젝트의 이름을 HelloActivity로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90068-111">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="90068-112">새 활동을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="90068-112">Open the new activity.</span></span>  <span data-ttu-id="90068-113">도구 상자의 <xref:System.Activities.Statements.Sequence> 활동을 디자이너 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="90068-113">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>

4. <span data-ttu-id="90068-114"><xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="90068-114">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="90068-115">`"Hello World"` **텍스트** 필드에 (따옴표 포함)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="90068-115">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>

5. <span data-ttu-id="90068-116">두 번째 <xref:System.Activities.Statements.WriteLine> 활동을 첫 번째 활동 아래의 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="90068-116">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="90068-117">`"Goodbye"` **텍스트** 필드에 (따옴표 포함)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="90068-117">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
