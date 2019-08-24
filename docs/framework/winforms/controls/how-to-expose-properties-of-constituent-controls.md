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
ms.openlocfilehash: f006e42771a5ecc71f6a508fd78d0e2dd8f2d2f2
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015860"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="809b3-102">방법: Constituent 컨트롤의 속성 공개</span><span class="sxs-lookup"><span data-stu-id="809b3-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="809b3-103">복합 컨트롤을 구성 하는 컨트롤을 *구성 요소 컨트롤*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="809b3-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="809b3-104">이러한 컨트롤은 일반적으로 private으로 선언 되므로 개발자가 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="809b3-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="809b3-105">이러한 컨트롤의 속성을 이후 사용자가 사용할 수 있게 하려면 사용자에 게 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="809b3-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="809b3-106">구성 컨트롤의 속성은 사용자 정의 컨트롤에서 속성을 만들고 해당 속성의 `get` 및 `set` 접근자를 사용 하 여 구성 요소 컨트롤의 private 속성에 변경 내용을 적용 하 여 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="809b3-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>

 <span data-ttu-id="809b3-107">이라는 `MyButton`구성 단추가 있는 가상의 사용자 정의 컨트롤을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="809b3-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="809b3-108">이 예제에서 사용자가 `ConstituentButtonBackColor` 속성을 요청 하면의 <xref:System.Windows.Forms.Control.BackColor%2A> `MyButton` 속성에 저장 된 값이 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="809b3-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="809b3-109">사용자가이 속성에 값을 할당 하면 <xref:System.Windows.Forms.Control.BackColor%2A> 해당 값이의 `MyButton` 속성에 자동으로 전달 되 고 `set` `MyButton`코드가 실행 되어 색이 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="809b3-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>

 <span data-ttu-id="809b3-110">다음 예제에서는 구성 단추의 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 노출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="809b3-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>

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

### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="809b3-111">구성 컨트롤의 속성을 노출 하려면</span><span class="sxs-lookup"><span data-stu-id="809b3-111">To expose a property of a constituent control</span></span>

1. <span data-ttu-id="809b3-112">사용자 정의 컨트롤에 대 한 공용 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="809b3-112">Create a public property for your user control.</span></span>

2. <span data-ttu-id="809b3-113">속성의 `get` 섹션에서 노출 하려는 속성의 값을 검색 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="809b3-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>

3. <span data-ttu-id="809b3-114">속성의 `set` 섹션에서 속성의 값을 구성 요소 컨트롤의 노출 된 속성에 전달 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="809b3-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>

## <a name="see-also"></a><span data-ttu-id="809b3-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="809b3-115">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="809b3-116">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="809b3-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="809b3-117">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="809b3-117">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
