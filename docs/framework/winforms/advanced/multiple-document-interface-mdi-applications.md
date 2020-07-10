---
title: MDI(다중 문서 인터페이스) 애플리케이션
description: MDI (다중 문서 인터페이스) 응용 프로그램을 사용 하 여 각 문서를 자체 창에 표시 하는 여러 문서를 동시에 표시 하 Windows Forms는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 0912a989ac1710d72c9db1cceb0e695f0ca85dee
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174655"
---
# <a name="multiple-document-interface-mdi-applications"></a>MDI(다중 문서 인터페이스) 애플리케이션
MDI (다중 문서 인터페이스) 응용 프로그램을 사용 하면 여러 문서를 동시에 표시할 수 있으며 각 문서는 자체 창에 표시 됩니다. MDI 응용 프로그램에는 종종 창이 나 문서 간을 전환 하기 위한 하위 메뉴가 포함 된 창 메뉴 항목이 있습니다.  
  
> [!NOTE]
> Windows Forms의 MDI 폼과 SDI (단일 문서 인터페이스) 창 간에는 몇 가지 동작 차이가 있습니다. `Opacity`속성은 MDI 자식 폼의 모양에 영향을 주지 않습니다. 또한이 <xref:System.Windows.Forms.Form.CenterToParent%2A> 메서드는 MDI 자식 폼의 동작에 영향을 주지 않습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: MDI 부모 양식 만들기](how-to-create-mdi-parent-forms.md)  
 MDI 응용 프로그램 내에서 여러 문서에 대 한 컨테이너를 만들기 위한 지침을 제공 합니다.  
  
 [방법: MDI 자식 양식 만들기](how-to-create-mdi-child-forms.md)  
 MDI 부모 폼 내에서 작동 하는 하나 이상의 창을 만드는 방법에 대 한 지침을 제공 합니다.  
  
 [방법: 활성 MDI 자식 확인](how-to-determine-the-active-mdi-child.md)  
 포커스가 있는 자식 창을 확인 하 고 해당 콘텐츠를 클립보드로 보내는 방법을 설명 합니다.  
  
 [방법: 활성 MDI 자식으로 데이터 보내기](how-to-send-data-to-the-active-mdi-child.md)  
 활성 자식 창으로 정보를 전송 하는 방법을 설명 합니다.  
  
 [방법: MDI 자식 양식 정렬](how-to-arrange-mdi-child-forms.md)  
 MDI 응용 프로그램의 자식 창에 대 한 바둑판식 배열, 계단식 배열 또는 정렬에 대 한 지침을 제공 합니다.
