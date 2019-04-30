---
title: '방법: BindingSource 및 INotifyPropertyChanged 인터페이스를 사용하여 변경 알림 발생'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: 71fb0a09387c77dbc792180dac1b8594d11b3642
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948046"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a>방법: BindingSource 및 INotifyPropertyChanged 인터페이스를 사용하여 변경 알림 발생
데이터 소스에 포함된 형식이 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하고 속성 값이 변경될 때 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 발생시키는 경우 <xref:System.Windows.Forms.BindingSource> 구성 요소가 데이터 소스의 변경 내용을 자동으로 검색합니다. 이 기능은 데이터 소스 값이 변경될 때 <xref:System.Windows.Forms.BindingSource>에 바인딩된 컨트롤이 자동으로 업데이트되므로 유용합니다.  
  
> [!NOTE]
>  데이터 소스가 <xref:System.ComponentModel.INotifyPropertyChanged>를 구현하고 비동기 작업을 수행하는 경우 백그라운드 스레드에서 데이터 소스를 변경하면 안 됩니다. 대신, 백그라운드 스레드에서 데이터를 읽은 다음 UI 스레드의 목록에 데이터를 병합해야 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스의 간단한 구현을 보여 줍니다. 또한 <xref:System.Windows.Forms.BindingSource>가 <xref:System.ComponentModel.INotifyPropertyChanged> 형식 목록에 바인딩된 경우 <xref:System.Windows.Forms.BindingSource>가 자동으로 데이터 소스 변경 내용을 바인딩된 컨트롤에 전달하는 방법을 보여 줍니다.  
  
 `CallerMemberName` 특성을 사용하는 경우 `NotifyPropertyChanged` 메서드 호출에서 속성 이름을 문자열 인수로 지정할 필요가 없습니다. 자세한 내용은 [호출자 정보 (C#)](../../../csharp/programming-guide/concepts/caller-information.md) 하거나 [호출자 정보 (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md)합니다.  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다. 또한 참조 [방법: 컴파일 및 Visual Studio를 사용 하 여 전체 Windows Forms 코드 예제를 실행](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb129228(v=vs.100))합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [BindingSource 구성 요소](bindingsource-component.md)
- [방법: BindingSource ResetItem 메서드를 사용 하 여 변경 알림 발생](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
