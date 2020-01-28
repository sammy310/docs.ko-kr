---
title: NumericUpDown 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- NumericUpDown
helpviewer_keywords:
- numeric spin button control [Windows Forms], Windows Forms
- NumericUpDown control [Windows Forms], about NumericUpDown control
- spin button control [Windows Forms], Windows Forms
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
ms.openlocfilehash: 3e24fa543df9028e9866d91ec60c3cf88578ac56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740807"
---
# <a name="numericupdown-control-overview-windows-forms"></a>NumericUpDown 컨트롤 개요(Windows Forms)
<xref:System.Windows.Forms.NumericUpDown> 컨트롤은 사용자가 클릭 하 여 값을 조정할 수 있는 텍스트 상자와 화살표 쌍의 조합 처럼 보입니다. 컨트롤은 고정 된 숫자 값 선택 목록에서 단일 숫자 값을 표시 하 고 설정 합니다. 사용자는 위쪽 및 아래쪽 화살표 키를 누르거나 컨트롤의 텍스트 상자 부분에 숫자를 입력 하 여 위쪽 및 아래쪽 화살표를 클릭 하 여이 수를 늘리거나 줄일 수 있습니다. 위쪽 화살표 키를 클릭 하면 숫자가 최대로 이동 합니다. 아래쪽 화살표 키를 클릭 하면 숫자가 최소 쪽으로 이동 합니다.  
  
 다양 한 기능으로 인해이 컨트롤은 음악 플레이어 응용 프로그램에 대 한 볼륨 컨트롤을 만들려는 경우와 같이 선택 하는 것이 좋습니다. <xref:System.Windows.Forms.NumericUpDown> 컨트롤은 많은 Windows 제어판 응용 프로그램에서 사용 됩니다.  
  
## <a name="key-properties-and-methods"></a>키 속성 및 메서드  
 컨트롤의 텍스트 상자에 표시 되는 숫자는 16 진수를 포함 하 여 다양 한 형식으로 표시 될 수 있습니다. 자세한 내용은 [방법: Windows Forms NumericUpDown 컨트롤의 형식 설정](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)을 참조 하세요. 컨트롤의 키 속성은 <xref:System.Windows.Forms.NumericUpDown.Value%2A><xref:System.Windows.Forms.NumericUpDown.Maximum%2A> (기본값 100), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> (기본값 0) 및 <xref:System.Windows.Forms.NumericUpDown.Increment%2A> (기본값 1)입니다. <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성은 컨트롤에서 선택 된 현재 숫자를 설정 합니다. <xref:System.Windows.Forms.NumericUpDown.Increment%2A> 속성은 사용자가 위쪽 또는 아래쪽 화살표를 클릭할 때 숫자를 조정 하는 크기를 설정 합니다. 포커스가 컨트롤을 벗어나면 형식화 된 모든 입력의 유효성은 최소 및 최대 숫자 값에 대해 유효성 검사가 수행 됩니다. 사용자가 <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> 속성을 사용 하 여 위로 또는 아래로 화살표를 지속적으로 누를 때 컨트롤이 숫자 간을 이동 하는 속도를 높일 수 있습니다. 컨트롤의 주요 메서드는 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> 하 고 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown 컨트롤](numericupdown-control-windows-forms.md)
- [방법: Windows Forms NumericUpDown 컨트롤의 형식 설정](how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)
- [TextBox 컨트롤](textbox-control-windows-forms.md)
