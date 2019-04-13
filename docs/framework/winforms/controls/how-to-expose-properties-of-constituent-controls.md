---
title: '방법: Constituent 컨트롤의 속성 공개'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
ms.openlocfilehash: 44b96218e674c754a1985f2f22a36707cd1776b6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59294914"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>방법: Constituent 컨트롤의 속성 공개
복합 컨트롤을 구성 하는 컨트롤 이라고 *구성 요소 컨트롤*합니다. 이러한 컨트롤은 일반적으로 전용으로 선언 및 하므로 개발자가 액세스할 수 없습니다. 미래의 사용자에 게 이러한 컨트롤의 속성을 제공 하려는 경우에 사용자에 게 노출 해야 있습니다. 사용자 컨트롤에서 속성을 만들고 사용 하 여 구성 요소 컨트롤의 속성을 노출 합니다 `get` 및 `set` 구성 요소 컨트롤의 개인 속성에 변경 내용을 적용 하려면 해당 속성의 접근자입니다.  
  
 구성 요소 라는 단추를 사용 하 여 가상의 사용자 컨트롤을 가정 `MyButton`합니다. 이 예제에서는 사용자가 요청할 때를 `ConstituentButtonBackColor` 속성에 저장 된 값을 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 `MyButton` 전달 됩니다. 사용자 값이이 속성에 할당 하는 경우 해당 값이 자동으로 전달 합니다 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 `MyButton` 및 `set` 코드는 실행의 색을 변경 `MyButton`합니다.  
  
 다음 예제에서는 노출 하는 방법을 보여 줍니다는 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 구성 합니다.  
  
```vb  
Public Property ButtonColor() as System.Drawing.Color  
   Get  
      Return MyButton.BackColor  
   End Get  
   Set(Value as System.Drawing.Color)  
      MyButton.BackColor = Value  
   End Set  
End Property  
```  
  
```csharp  
public Color ButtonColor  
{  
   get  
   {  
      return(myButton.BackColor);  
   }  
   set  
   {  
      myButton.BackColor = value;  
   }  
}  
```  
  
### <a name="to-expose-a-property-of-a-constituent-control"></a>구성 요소 컨트롤의 속성을 노출 하려면  
  
1. 사용자 정의 컨트롤에 대 한 공용 속성을 만듭니다.  
  
2. 에 `get` 섹션의 속성을 노출 하려는 속성의 값을 검색 하는 코드를 작성 합니다.  
  
3. 에 `set` 섹션 속성의 구성 요소 컨트롤 노출 된 속성에 속성의 값을 전달 하는 코드를 작성 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.UserControl>
- [Windows Forms 컨트롤의 속성](properties-in-windows-forms-controls.md)
- [사용자 지정 컨트롤의 종류](varieties-of-custom-controls.md)
