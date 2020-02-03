---
title: 컨트롤의 내게 필요한 옵션 속성
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: 73d81f5b5f656ed5ef90bdd9b6fe1b3293123f97
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743430"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>내게 필요한 옵션 지침을 지원하는 Windows Forms 컨트롤의 속성
Windows Forms에 대 한 표준 도구 상자의 컨트롤은 키보드 포커스를 표시 하 고 화면 요소를 표시 하는 등 많은 내게 필요한 옵션 지침을 지원 합니다.  
  
## <a name="planning-ahead-for-accessibility"></a>접근성에 대 한 미리 계획  
 컨트롤의 속성을 사용 하 여 다음 표에 나와 있는 것 처럼 다른 접근성 지침을 지원할 수 있습니다. 또한 메뉴를 사용 하 여 프로그램 기능에 대 한 액세스를 제공 해야 합니다.  
  
|컨트롤 속성|내게 필요한 옵션에 대 한 고려 사항|  
|----------------------|--------------------------------------|  
|AccessibleDescription|설명은 화면 판독기와 같은 내게 필요한 옵션 지원 기능에 보고 됩니다. 접근성 보조 기능은 장애가 있는 사용자가 컴퓨터를 보다 효율적으로 사용하도록 돕는 특수 프로그램 및 디바이스입니다.|  
|AccessibleName|내게 필요한 옵션 지원 기능에 보고 되는 이름입니다.|  
|AccessibleRole|사용자 인터페이스에서 요소를 사용 하는 방법을 설명 합니다.|  
|TabIndex|폼을 통해 합리적인 탐색 경로를 만듭니다. 텍스트 상자와 같은 내장 레이블이 없는 컨트롤은 탭 순서에서 연결 된 레이블을 바로 앞에 오도록 하는 것이 중요 합니다.|  
|Text|"&" 문자를 사용 하 여 액세스 키를 만듭니다. 액세스 키 사용은 설명서 키보드의 기능 액세스를 제공 하는 데 포함 됩니다.|  
|글꼴 크기|글꼴 크기를 조정할 수 없는 경우 10 점으로 설정 해야 합니다. 폼의 글꼴 크기를 설정 하면 이후에 폼에 추가 된 모든 컨트롤의 크기가 동일 하 게 됩니다.|  
|Forecolor|이 속성을 기본값으로 설정 하면 사용자의 색 기본 설정이 폼에 사용 됩니다.|  
|Backcolor|이 속성을 기본값으로 설정 하면 사용자의 색 기본 설정이 폼에 사용 됩니다.|  
|BackgroundImage|텍스트를 더 쉽게 읽을 수 있도록 하려면이 속성을 비워 둡니다.|  
  
## <a name="see-also"></a>참고 항목

- [연습: 내게 필요한 옵션이 지원되는 Windows 기반 애플리케이션 만들기](walkthrough-creating-an-accessible-windows-based-application.md)
