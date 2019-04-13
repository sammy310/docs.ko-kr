---
title: '방법: BindingSource 구성 요소를 사용하여 양식 간에 바인딩된 데이터 공유'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: 19505c690728147d2a67c26371e1cea4c281ab08
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154872"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a>방법: BindingSource 구성 요소를 사용하여 양식 간에 바인딩된 데이터 공유
<xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 폼 간에 데이터를 쉽게 공유할 수 있습니다. 예를 들어 데이터 소스 데이터를 요약하는 하나의 읽기 전용 폼과 데이터 소스에서 현재 선택한 항목에 대한 세부 정보가 포함된 다른 편집 가능한 폼을 표시할 수 있습니다. 이 예제에서는 이 시나리오를 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.BindingSource> 및 바인딩된 데이터를 폼 간에 공유하는 방법을 보여 줍니다. 이 예제에서는 공유 <xref:System.Windows.Forms.BindingSource>는 자식 폼의 생성자에 전달됩니다. 자식 폼을 통해 사용자는 기본 폼에서 현재 선택한 항목에 대한 데이터를 편집할 수 있습니다.  
  
> [!NOTE]
>  예제에서는 <xref:System.Windows.Forms.BindingSource> 구성 요소에 대한 <xref:System.Windows.Forms.BindingSource.BindingComplete> 이벤트를 처리하여 두 폼을 동기화된 상태로 유지합니다. 내용은 이유에 대 한 자세한 내용은 이루어집니다 [방법: 여러 컨트롤을 확인 동일한 데이터 소스에 바인딩된 동기화 된 상태로 유지](../multiple-controls-bound-to-data-source-synchronized.md)합니다.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Windows.Forms, System.Drawing, System.Data 및 System.Xml 어셈블리에 대한 참조  
  
 Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다. 또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [BindingSource 구성 요소](bindingsource-component.md)
- [Windows Forms 데이터 바인딩](../windows-forms-data-binding.md)
- [방법: 데이터 바인딩에서 발생하는 오류 및 예외 처리](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
