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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941377"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="9cecc-102">방법: Constituent 컨트롤의 속성 공개</span><span class="sxs-lookup"><span data-stu-id="9cecc-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="9cecc-103">복합 컨트롤을 구성 하는 컨트롤 이라고 *구성 요소 컨트롤*합니다.</span><span class="sxs-lookup"><span data-stu-id="9cecc-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="9cecc-104">이러한 컨트롤은 일반적으로 전용으로 선언 및 하므로 개발자가 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9cecc-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="9cecc-105">미래의 사용자에 게 이러한 컨트롤의 속성을 제공 하려는 경우에 사용자에 게 노출 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cecc-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="9cecc-106">사용자 컨트롤에서 속성을 만들고 사용 하 여 구성 요소 컨트롤의 속성을 노출 합니다 `get` 및 `set` 구성 요소 컨트롤의 개인 속성에 변경 내용을 적용 하려면 해당 속성의 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="9cecc-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>  
  
 <span data-ttu-id="9cecc-107">구성 요소 라는 단추를 사용 하 여 가상의 사용자 컨트롤을 가정 `MyButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="9cecc-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="9cecc-108">이 예제에서는 사용자가 요청할 때를 `ConstituentButtonBackColor` 속성에 저장 된 값을 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 `MyButton` 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cecc-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="9cecc-109">사용자 값이이 속성에 할당 하는 경우 해당 값이 자동으로 전달 합니다 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 `MyButton` 및 `set` 코드는 실행의 색을 변경 `MyButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="9cecc-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>  
  
 <span data-ttu-id="9cecc-110">다음 예제에서는 노출 하는 방법을 보여 줍니다는 <xref:System.Windows.Forms.Control.BackColor%2A> 속성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cecc-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>  
  
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
  
### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="9cecc-111">구성 요소 컨트롤의 속성을 노출 하려면</span><span class="sxs-lookup"><span data-stu-id="9cecc-111">To expose a property of a constituent control</span></span>  
  
1. <span data-ttu-id="9cecc-112">사용자 정의 컨트롤에 대 한 공용 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9cecc-112">Create a public property for your user control.</span></span>  
  
2. <span data-ttu-id="9cecc-113">에 `get` 섹션의 속성을 노출 하려는 속성의 값을 검색 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cecc-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>  
  
3. <span data-ttu-id="9cecc-114">에 `set` 섹션 속성의 구성 요소 컨트롤 노출 된 속성에 속성의 값을 전달 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cecc-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cecc-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="9cecc-115">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="9cecc-116">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="9cecc-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="9cecc-117">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="9cecc-117">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
