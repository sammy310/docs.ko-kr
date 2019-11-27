---
title: ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: 11181bacdb919693ffc82c48c061357463a6343b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336759"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의
`ShouldSerialize` 및 `Reset`은 속성에 대해 제공할 수 있는 선택적 메서드로, 속성에 단순 기본값이 없는 경우에 한 합니다. 속성에 단순 기본값이 있는 경우 <xref:System.ComponentModel.DefaultValueAttribute>를 적용 하 고 대신 특성 클래스 생성자에 기본값을 제공 해야 합니다. 이러한 메커니즘 중 하나를 통해 디자이너에서 다음 기능을 사용할 수 있습니다.

- 속성은 속성 브라우저가 기본값에서 수정 된 경우이를 시각적으로 표시 합니다.

- 사용자는 속성을 마우스 오른쪽 단추로 클릭 하 고 **다시 설정** 을 선택 하 여 속성을 기본값으로 복원할 수 있습니다.

- 디자이너가 보다 효율적인 코드를 생성 합니다.

    > [!NOTE]
    > <xref:System.ComponentModel.DefaultValueAttribute>를 적용 하거나 propertyname 및 `ShouldSerialize`*propertyname* *메서드를 `Reset`* 제공 합니다. 둘 다 사용 하지 마세요.

 `Reset`*PropertyName* 메서드는 다음 코드 조각에 표시 된 것 처럼 속성을 기본값으로 설정 합니다.

```vb
Public Sub ResetMyFont()
   MyFont = Nothing
End Sub
```

```csharp
public void ResetMyFont() {
   MyFont = null;
}
```

> [!NOTE]
> 속성에 `Reset` 메서드가 없고 <xref:System.ComponentModel.DefaultValueAttribute>으로 표시 되지 않고 해당 선언에 기본값이 제공 되지 않은 경우 Visual Studio의 Windows Forms 디자이너 **속성** 창에 있는 바로 가기 메뉴에서 해당 속성에 대 한 `Reset` 옵션을 사용할 수 없습니다.

 Visual Studio와 같은 디자이너는 `ShouldSerialize`*PropertyName* 메서드를 사용 하 여 속성이 기본값에서 변경 되었는지 여부를 확인 하 고, 속성이 변경 된 경우에만 폼에 코드를 작성 하 여 보다 효율적인 코드 생성을 허용 합니다. 예를 들어 다음과 같은 가치를 제공해야 합니다.

```vb
'Returns true if the font has changed; otherwise, returns false.
' The designer writes code to the form only if true is returned.
Public Function ShouldSerializeMyFont() As Boolean
   Return Not (thefont Is Nothing)
End Function
```

```csharp
// Returns true if the font has changed; otherwise, returns false.
// The designer writes code to the form only if true is returned.
public bool ShouldSerializeMyFont() {
   return thefont != null;
}
```

 전체 코드 예제는 다음과 같습니다.

```vb
Option Explicit
Option Strict

Imports System.Drawing
Imports System.Windows.Forms

Public Class MyControl
   Inherits Control

   ' Declare an instance of the Font class
   ' and set its default value to Nothing.
   Private thefont As Font = Nothing

   ' The MyFont property.
   Public Property MyFont() As Font
      ' Note that the Font property never
      ' returns null.
      Get
         If Not (thefont Is Nothing) Then
            Return thefont
         End If
         If Not (Parent Is Nothing) Then
            Return Parent.Font
         End If
         Return Control.DefaultFont
      End Get
      Set
         thefont = value
      End Set
   End Property

   Public Function ShouldSerializeMyFont() As Boolean
      Return Not (thefont Is Nothing)
   End Function

   Public Sub ResetMyFont()
      MyFont = Nothing
   End Sub
End Class
```

```csharp
using System;
using System.Drawing;
using System.Windows.Forms;

public class MyControl : Control {
   // Declare an instance of the Font class
   // and set its default value to null.
   private Font thefont = null;

   // The MyFont property.
   public Font MyFont {
      // Note that the MyFont property never
      // returns null.
      get {
         if (thefont != null) return thefont;
         if (Parent != null) return Parent.Font;
         return Control.DefaultFont;
      }
      set {
         thefont = value;
      }
   }

   public bool ShouldSerializeMyFont() {
      return thefont != null;
   }

   public void ResetMyFont() {
      MyFont = null;
   }
}
```

 이 경우 `MyFont` 속성에서 액세스 하는 private 변수의 값이 `null`경우에도 속성 브라우저는 `null`를 표시 하지 않습니다. 대신 부모의 <xref:System.Windows.Forms.Control.Font%2A> 속성 (`null`되지 않은 경우) 또는 <xref:System.Windows.Forms.Control>에 정의 된 기본 <xref:System.Windows.Forms.Control.Font%2A> 값을 표시 합니다. 따라서 `MyFont`의 기본값은 간단히 설정할 수 없으며 <xref:System.ComponentModel.DefaultValueAttribute>를이 속성에 적용할 수 없습니다. 대신 `MyFont` 속성에 대해 `ShouldSerialize` 및 `Reset` 메서드를 구현 해야 합니다.

## <a name="see-also"></a>참고자료

- [Windows Forms 컨트롤의 속성](properties-in-windows-forms-controls.md)
- [속성 정의](defining-a-property-in-windows-forms-controls.md)
- [속성 변경 이벤트](property-changed-events.md)
