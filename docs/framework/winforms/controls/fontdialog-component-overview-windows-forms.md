---
title: FontDialog 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745696"
---
# <a name="fontdialog-component-overview-windows-forms"></a>FontDialog 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.FontDialog> 구성 요소는 시스템에 현재 설치 되어 있는 글꼴을 표시 하는 데 사용 되는 표준 Windows **글꼴** 대화 상자 인 미리 구성 된 대화 상자입니다. 사용자 고유의 대화 상자를 구성 하는 대신 글꼴 선택을 위한 간단한 솔루션인 Windows 기반 응용 프로그램 내에서이 기능을 사용 합니다.  
  
 기본적으로 대화 상자에는 글꼴, 글꼴 스타일 및 크기에 대 한 목록 상자가 표시 됩니다. 취소선, 밑줄 등의 효과에 대 한 확인란 스크립트에 대 한 드롭다운 목록 그리고 글꼴이 표시 되는 방법에 대 한 샘플입니다. 스크립트는 지정 된 글꼴에 사용할 수 있는 다른 문자 스크립트 (예: 히브리어 또는 일본어)를 참조 합니다. 글꼴 대화 상자를 표시 하려면 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 호출 합니다.  
  
## <a name="key-properties"></a>키 속성  
 구성 요소에는 모양을 구성 하는 다양 한 속성이 있습니다. 대화 상자 선택 항목을 설정 하는 속성은 <xref:System.Windows.Forms.FontDialog.Font%2A> <xref:System.Windows.Forms.FontDialog.Color%2A>됩니다. <xref:System.Windows.Forms.FontDialog.Font%2A> 속성은 글꼴, 스타일, 크기, 스크립트 및 효과를 설정 합니다. 예를 들어 `Arial, 10pt, style=Italic, Strikeout`합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.FontDialog>
- [FontDialog 구성 요소](fontdialog-component-windows-forms.md)
