---
title: Windows Form의 컨트롤에 내게 필요한 옵션 정보 제공
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 3067c90978e6ebd680d10c1c4f9db131f19c9e44
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614755"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a><span data-ttu-id="33e52-102">Windows Form의 컨트롤에 내게 필요한 옵션 정보 제공</span><span class="sxs-lookup"><span data-stu-id="33e52-102">Providing Accessibility Information for Controls on a Windows Form</span></span>
<span data-ttu-id="33e52-103">접근성 보조 기능은 장애가 있는 사용자가 컴퓨터를 보다 효율적으로 사용하도록 돕는 특수 프로그램 및 디바이스입니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-103">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="33e52-104">시력 장애가 있는 사용자를 위한 화면 판독기와 마우스나 키보드를 사용하지 않고 구두 명령을 제공하는 사용자를 위한 음성 입력 유틸리티를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-104">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="33e52-105">이러한 접근성 보조 기능은 Windows Forms 컨트롤에서 노출하는 접근성 속성을 조작합니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-105">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="33e52-106">이러한 속성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-106">These properties are:</span></span>  
  
- <span data-ttu-id="33e52-107">**AccessibilityObject**</span><span class="sxs-lookup"><span data-stu-id="33e52-107">**AccessibilityObject**</span></span>  
  
- <span data-ttu-id="33e52-108">**AccessibleDefaultActionDescription**</span><span class="sxs-lookup"><span data-stu-id="33e52-108">**AccessibleDefaultActionDescription**</span></span>  
  
- <span data-ttu-id="33e52-109">**AccessibleDescription**</span><span class="sxs-lookup"><span data-stu-id="33e52-109">**AccessibleDescription**</span></span>  
  
- <span data-ttu-id="33e52-110">**AccessibleName**</span><span class="sxs-lookup"><span data-stu-id="33e52-110">**AccessibleName**</span></span>  
  
- <span data-ttu-id="33e52-111">**AccessibleRole**</span><span class="sxs-lookup"><span data-stu-id="33e52-111">**AccessibleRole**</span></span>  
  
## <a name="accessibilityobject-property"></a><span data-ttu-id="33e52-112">AccessibilityObject 속성</span><span class="sxs-lookup"><span data-stu-id="33e52-112">AccessibilityObject Property</span></span>  
 <span data-ttu-id="33e52-113">이 읽기 전용 속성은 <xref:System.Windows.Forms.AccessibleObject> 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-113">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="33e52-114">**AccessibleObject** 는 컨트롤의 설명, 화면 위치, 탐색 기능 및 값 정보를 제공하는 <xref:Accessibility.IAccessible> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-114">The **AccessibleObject** implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="33e52-115">디자이너에서는 컨트롤이 폼에 추가될 때 이 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-115">The designer sets this value when the control is added to the form.</span></span>  
  
## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="33e52-116">AccessibleDefaultActionDescription 속성</span><span class="sxs-lookup"><span data-stu-id="33e52-116">AccessibleDefaultActionDescription Property</span></span>  
 <span data-ttu-id="33e52-117">이 문자열은 컨트롤의 동작을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-117">This string describes the action of the control.</span></span> <span data-ttu-id="33e52-118">이 문자열은 속성 창에는 나타나지 않고 코드로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-118">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="33e52-119">다음은 button 컨트롤에 이 속성을 설정하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-119">The following example sets this property for a button control:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
  
// C#  
Button1.AccessibleDefaultActionDescription =   
   "Closes the application.";  
  
// C++  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a><span data-ttu-id="33e52-120">AccessibleDescription 속성</span><span class="sxs-lookup"><span data-stu-id="33e52-120">AccessibleDescription Property</span></span>  
 <span data-ttu-id="33e52-121">이 문자열은 컨트롤을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-121">This string describes the control.</span></span> <span data-ttu-id="33e52-122">속성 창에서 설정할 수도 있고 다음과 같이 코드로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-122">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDescription = "A button with text 'Exit'."  
  
// C#  
Button1.AccessibleDescription = "A button with text 'Exit'";  
  
// C++  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a><span data-ttu-id="33e52-123">AccessibleName 속성</span><span class="sxs-lookup"><span data-stu-id="33e52-123">AccessibleName Property</span></span>  
 <span data-ttu-id="33e52-124">이 속성은 접근성 보조 기능에 보고되는 컨트롤의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-124">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="33e52-125">속성 창에서 설정할 수도 있고 다음과 같이 코드로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-125">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleName = "Order"  
  
// C#  
Button1.AccessibleName = "Order";  
  
// C++  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a><span data-ttu-id="33e52-126">AccessibleRole 속성</span><span class="sxs-lookup"><span data-stu-id="33e52-126">AccessibleRole Property</span></span>  
 <span data-ttu-id="33e52-127">이 속성을 포함 하는 <xref:System.Windows.Forms.AccessibleRole> 컨트롤의 사용자 인터페이스 역할을 설명 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-127">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="33e52-128">새 컨트롤에는 이 값이 `Default`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-128">A new control has the value set to `Default`.</span></span> <span data-ttu-id="33e52-129">이것은 기본적으로 **Button** 컨트롤이 **Button**으로 동작함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-129">This would mean that by default, a **Button** control acts as a **Button**.</span></span> <span data-ttu-id="33e52-130">컨트롤이 다른 역할을 수행할 경우에는 이 속성을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-130">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="33e52-131">예를 들어 **PictureBox** 컨트롤을 **Chart**로 사용할 수 있으며 이때 접근성 보조 기능에서 **PictureBox**가 아닌 **Chart**로 역할을 보고하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-131">For example, you may be using a **PictureBox** control as a **Chart**, and you may want accessibility aids to report the role as a **Chart**, not as a **PictureBox**.</span></span> <span data-ttu-id="33e52-132">또한 직접 개발한 사용자 지정 컨트롤에 이 속성을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-132">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="33e52-133">이 속성은 속성 창에서 설정하거나 다음과 같이 코드로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33e52-133">This property may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
PictureBox1.AccessibleRole = AccessibleRole.Chart  
  
// C#  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
  
// C++  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a><span data-ttu-id="33e52-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="33e52-134">See also</span></span>

- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
