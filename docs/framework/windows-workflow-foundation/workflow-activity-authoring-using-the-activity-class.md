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
# <a name="workflow-activity-authoring-using-the-activity-class"></a>활동 클래스를 사용하여 워크플로 활동 제작

에서 WF (Windows Workflow Foundation)를 사용 하 여 활동을 만드는 가장 기본적인 방법은 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <xref:System.Activities.Activity> [기본 제공 활동 라이브러리](net-framework-4-5-built-in-activity-library.md)에서 사용자 지정 활동 또는 활동을 조합 하 여 기능을 만드는에서 상속 하는 클래스를 만드는 것입니다. 이 항목에서는 콘솔에 두 개의 메시지를 쓰는 활동을 만드는 방법을 보여 줍니다.

### <a name="to-create-a-custom-activity-using-the-activity-designer"></a>활동 디자이너를 사용하여 사용자 지정 활동을 만들려면

1. Visual Studio 2012을 엽니다.

2. 파일, 새로 만들기, 프로젝트를 차례로 선택합니다. **프로젝트 형식** 창에서 **Visual c #** 아래에 있는 **Workflow 4.0** 을 선택 하 고 **v2010** 노드를 선택 합니다. **템플릿** 창에서 **활동 라이브러리** 를 선택 합니다. 새 프로젝트의 이름을 HelloActivity로 지정합니다.

3. 새 활동을 엽니다.  도구 상자의 <xref:System.Activities.Statements.Sequence> 활동을 디자이너 화면으로 끌어 옵니다.

4. <xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다. `"Hello World"` **텍스트** 필드에 (따옴표 포함)를 입력 합니다.

5. 두 번째 <xref:System.Activities.Statements.WriteLine> 활동을 첫 번째 활동 아래의 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다. `"Goodbye"` **텍스트** 필드에 (따옴표 포함)를 입력 합니다.
