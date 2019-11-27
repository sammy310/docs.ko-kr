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
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="fa015-102">ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의</span><span class="sxs-lookup"><span data-stu-id="fa015-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="fa015-103">`ShouldSerialize` 및 `Reset`은 속성에 대해 제공할 수 있는 선택적 메서드로, 속성에 단순 기본값이 없는 경우에 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="fa015-104">속성에 단순 기본값이 있는 경우 <xref:System.ComponentModel.DefaultValueAttribute>를 적용 하 고 대신 특성 클래스 생성자에 기본값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="fa015-105">이러한 메커니즘 중 하나를 통해 디자이너에서 다음 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-105">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="fa015-106">속성은 속성 브라우저가 기본값에서 수정 된 경우이를 시각적으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="fa015-107">사용자는 속성을 마우스 오른쪽 단추로 클릭 하 고 **다시 설정** 을 선택 하 여 속성을 기본값으로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="fa015-108">디자이너가 보다 효율적인 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-108">The designer generates more efficient code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fa015-109"><xref:System.ComponentModel.DefaultValueAttribute>를 적용 하거나 propertyname 및 `ShouldSerialize`*propertyname* *메서드를 `Reset`* 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="fa015-110">둘 다 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fa015-110">Do not use both.</span></span>

 <span data-ttu-id="fa015-111">`Reset`*PropertyName* 메서드는 다음 코드 조각에 표시 된 것 처럼 속성을 기본값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

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
> <span data-ttu-id="fa015-112">속성에 `Reset` 메서드가 없고 <xref:System.ComponentModel.DefaultValueAttribute>으로 표시 되지 않고 해당 선언에 기본값이 제공 되지 않은 경우 Visual Studio의 Windows Forms 디자이너 **속성** 창에 있는 바로 가기 메뉴에서 해당 속성에 대 한 `Reset` 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="fa015-113">Visual Studio와 같은 디자이너는 `ShouldSerialize`*PropertyName* 메서드를 사용 하 여 속성이 기본값에서 변경 되었는지 여부를 확인 하 고, 속성이 변경 된 경우에만 폼에 코드를 작성 하 여 보다 효율적인 코드 생성을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="fa015-114">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-114">For example:</span></span>

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

 <span data-ttu-id="fa015-115">전체 코드 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-115">A complete code example follows.</span></span>

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

 <span data-ttu-id="fa015-116">이 경우 `MyFont` 속성에서 액세스 하는 private 변수의 값이 `null`경우에도 속성 브라우저는 `null`를 표시 하지 않습니다. 대신 부모의 <xref:System.Windows.Forms.Control.Font%2A> 속성 (`null`되지 않은 경우) 또는 <xref:System.Windows.Forms.Control>에 정의 된 기본 <xref:System.Windows.Forms.Control.Font%2A> 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="fa015-117">따라서 `MyFont`의 기본값은 간단히 설정할 수 없으며 <xref:System.ComponentModel.DefaultValueAttribute>를이 속성에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="fa015-118">대신 `MyFont` 속성에 대해 `ShouldSerialize` 및 `Reset` 메서드를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa015-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa015-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="fa015-119">See also</span></span>

- [<span data-ttu-id="fa015-120">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="fa015-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="fa015-121">속성 정의</span><span class="sxs-lookup"><span data-stu-id="fa015-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="fa015-122">속성 변경 이벤트</span><span class="sxs-lookup"><span data-stu-id="fa015-122">Property-Changed Events</span></span>](property-changed-events.md)
