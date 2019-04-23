---
title: DomainUpDown 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: bfe3e7239f77c6f1a0d9bb46a96c704653b43364
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102858"
---
# <a name="domainupdown-control-overview-windows-forms"></a>DomainUpDown 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤은 한 쌍의 목록에서 위로 또는 아래로 이동 단추 및 텍스트 상자를 나열 하는 기본적으로 조합 합니다. 컨트롤이 표시 하 고 선택 목록에서 텍스트 문자열을 설정 합니다. 사용자 단추 목록에서 이동를 클릭 하 여, 위쪽 및 아래쪽 화살표 키를 눌러 또는 목록의 항목을 일치 하는 문자열을 입력 하 여 문자열을 선택할 수 있습니다. 이 컨트롤에 대 한 한 가지 가능한 용도 이름의 사전순으로 정렬된 된 목록에서 항목 선택입니다.  
  
> [!NOTE]
>  목록을 정렬 하려면 설정 합니다 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 속성을 `true`입니다.  
  
 이 컨트롤의 기능 목록 상자 또는 콤보 상자에 매우 유사 하지만 매우 작은 공간을 차지 합니다.  
  
## <a name="key-properties"></a>키 속성  
 컨트롤의 키 속성은 <xref:System.Windows.Forms.DomainUpDown.Items%2A>하십시오 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, 및 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>합니다. <xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성 컨트롤의 텍스트 값을 표시 하는 개체의 목록을 포함 합니다. 하는 경우 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 로 설정 된 `false`, 사용자 형식과 값 목록에 일치 하는 텍스트를 자동으로 완성 하는 컨트롤입니다. 하는 경우 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 로 설정 된 `true`, 마지막 항목을 지 나 스크롤 하면 첫 번째 항목 목록에서 이동 하 고 그 반대의 경우도 마찬가지입니다. 컨트롤의 주요 메서드는 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 고 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>입니다.  
  
 이 컨트롤에는 텍스트 문자열만 표시 됩니다. 숫자 값을 표시 하는 컨트롤을 사용 합니다 <xref:System.Windows.Forms.NumericUpDown> 제어 합니다. 자세한 내용은 [NumericUpDown 컨트롤 개요](numericupdown-control-overview-windows-forms.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.DomainUpDown>
- [DomainUpDown 컨트롤](domainupdown-control-windows-forms.md)
