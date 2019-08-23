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
ms.openlocfilehash: 609fe4896a2b01b8a69ff8a3d0854c85ddbd6a26
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969087"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="b4659-102">ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의</span><span class="sxs-lookup"><span data-stu-id="b4659-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="b4659-103">`ShouldSerialize`및 `Reset` 는 속성에 단순 기본값이 없는 경우 속성에 대해 제공할 수 있는 선택적 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="b4659-104">속성에 단순 기본값이 있는 경우를 적용 <xref:System.ComponentModel.DefaultValueAttribute> 하 고 대신 특성 클래스 생성자에 기본값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="b4659-105">이러한 메커니즘 중 하나를 통해 디자이너에서 다음 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-105">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="b4659-106">속성은 속성 브라우저가 기본값에서 수정 된 경우이를 시각적으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="b4659-107">사용자는 속성을 마우스 오른쪽 단추로 클릭 하 고 **다시 설정** 을 선택 하 여 속성을 기본값으로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="b4659-108">디자이너가 보다 효율적인 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-108">The designer generates more efficient code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4659-109">를 <xref:System.ComponentModel.DefaultValueAttribute> 적용 하거나 *propertyname* 및 `Reset` `ShouldSerialize` *propertyname* 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="b4659-110">둘 다 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b4659-110">Do not use both.</span></span>

 <span data-ttu-id="b4659-111">`Reset` *PropertyName* 메서드는 다음 코드 조각에 표시 된 것 처럼 속성을 기본값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

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
> <span data-ttu-id="b4659-112">속성 `Reset` 에 메서드가 없고로 표시 <xref:System.ComponentModel.DefaultValueAttribute>되어 있지 않고 해당 선언 `Reset` 에 기본값이 제공 되지 않은 경우 속성 창의 바로 가기 메뉴에서 해당 속성에 대 한 옵션을 사용할 수 없습니다. Visual Studio의 Windows Forms 디자이너입니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="b4659-113">Visual Studio와 같은 디자이너는 `ShouldSerialize` *PropertyName* 메서드를 사용 하 여 속성이 기본값에서 변경 되었는지 여부를 확인 하 고, 속성이 변경 된 경우에만 폼에 코드를 작성 하 여 보다 효율적인 코드 생성을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="b4659-114">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="b4659-114">For example:</span></span>

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

 <span data-ttu-id="b4659-115">전체 코드 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-115">A complete code example follows.</span></span>

```vb
Option Explicit
Option Strict

Imports System
Imports System.Windows.Forms
Imports System.Drawing

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
using System.Windows.Forms;
using System.Drawing;

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

 <span data-ttu-id="b4659-116">이 `MyFont` 경우 속성에서 액세스 하는 private 변수의 값이 인 `null`경우에도 속성 브라우저는 표시 `null`되지 않습니다. 대신 부모의 <xref:System.Windows.Forms.Control.Font%2A> `null`속성을 표시 합니다. 또는에 <xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.Control>정의 된 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="b4659-117">따라서의 `MyFont` 기본값은 간단히 설정할 수 없으며이 속성에를 <xref:System.ComponentModel.DefaultValueAttribute> 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4659-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="b4659-118">대신 속성에 대해 `Reset` 및메서드를구현해야합니다.`ShouldSerialize` `MyFont`</span><span class="sxs-lookup"><span data-stu-id="b4659-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4659-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="b4659-119">See also</span></span>

- [<span data-ttu-id="b4659-120">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="b4659-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="b4659-121">속성 정의</span><span class="sxs-lookup"><span data-stu-id="b4659-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="b4659-122">속성 변경 이벤트</span><span class="sxs-lookup"><span data-stu-id="b4659-122">Property-Changed Events</span></span>](property-changed-events.md)
