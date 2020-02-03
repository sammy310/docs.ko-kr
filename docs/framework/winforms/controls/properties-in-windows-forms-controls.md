---
title: 컨트롤의 속성
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: 82bfab15cef4946661a37d2d88fbe1b797f3d816
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741175"
---
# <a name="properties-in-windows-forms-controls"></a><span data-ttu-id="26025-102">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="26025-102">Properties in Windows Forms Controls</span></span>
<span data-ttu-id="26025-103">Windows Forms 컨트롤은 기본 클래스 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>의 많은 속성을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="26025-103">A Windows Forms control inherits many properties form the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="26025-104">여기에는 <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>등의 속성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26025-104">These include properties such as <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, and many others.</span></span> <span data-ttu-id="26025-105">상속 된 속성에 대 한 자세한 내용은 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26025-105">For details about inherited properties, see <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="26025-106">컨트롤에서 상속된 속성을 재정의하고 새 속성을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26025-106">You can override inherited properties in your control as well as define new properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="26025-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="26025-107">In This Section</span></span>  
 [<span data-ttu-id="26025-108">속성 정의</span><span class="sxs-lookup"><span data-stu-id="26025-108">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)  
 <span data-ttu-id="26025-109">사용자 지정 컨트롤 또는 구성 요소에 대한 속성을 구현하는 방법 및 속성을 디자인 환경으로 통합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26025-109">Shows how to implement a property for a custom control or component and shows how to integrate the property into the design environment.</span></span>  
  
 [<span data-ttu-id="26025-110">ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의</span><span class="sxs-lookup"><span data-stu-id="26025-110">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 <span data-ttu-id="26025-111">사용자 지정 컨트롤 또는 구성 요소에 대한 기본 속성 값을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26025-111">Shows how to define default property values for a custom control or component.</span></span>  
  
 [<span data-ttu-id="26025-112">속성 변경 이벤트</span><span class="sxs-lookup"><span data-stu-id="26025-112">Property-Changed Events</span></span>](property-changed-events.md)  
 <span data-ttu-id="26025-113">속성 값이 변경될 때 속성 변경 알림을 활성화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26025-113">Describes how to enable property-change notifications when a property value changes.</span></span>  
  
 [<span data-ttu-id="26025-114">방법: 구성 요소 컨트롤의 속성 노출</span><span class="sxs-lookup"><span data-stu-id="26025-114">How to: Expose Properties of Constituent Controls</span></span>](how-to-expose-properties-of-constituent-controls.md)  
 <span data-ttu-id="26025-115">사용자 지정 복합 컨트롤에서 구성 요소 컨트롤의 속성을 노출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26025-115">Shows how to expose properties of constituent controls in a custom composite control.</span></span>  
  
 [<span data-ttu-id="26025-116">사용자 지정 컨트롤에서 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="26025-116">Method Implementation in Custom Controls</span></span>](method-implementation-in-custom-controls.md)  
 <span data-ttu-id="26025-117">사용자 지정 컨트롤 및 구성 요소에서 메서드를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26025-117">Describes how to implement methods in custom controls and components.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="26025-118">참조</span><span class="sxs-lookup"><span data-stu-id="26025-118">Reference</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="26025-119">복합 컨트롤을 구현하기 위한 기본 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26025-119">Documents the base class for implementing composite controls.</span></span>  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 <span data-ttu-id="26025-120">사용자 지정 속성 형식에 사용할 <xref:System.ComponentModel.TypeConverter>를 지정 하는 특성을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="26025-120">Documents the attribute that specifies the <xref:System.ComponentModel.TypeConverter> to use for a custom property type.</span></span>  
  
 <xref:System.ComponentModel.EditorAttribute>  
 <span data-ttu-id="26025-121">사용자 지정 속성에 사용할 <xref:System.Drawing.Design.UITypeEditor>를 지정 하는 특성을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="26025-121">Documents the attribute that specifies the <xref:System.Drawing.Design.UITypeEditor> to use for a custom property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="26025-122">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="26025-122">Related Sections</span></span>  
 [<span data-ttu-id="26025-123">Windows Forms 컨트롤의 특성</span><span class="sxs-lookup"><span data-stu-id="26025-123">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="26025-124">사용자 지정 컨트롤 및 구성 요소의 속성이나 다른 멤버에 적용할 수 있는 특성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26025-124">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 <span data-ttu-id="26025-125">[구성 요소의 디자인 타임 특성](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="26025-125">[Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="26025-126">비주얼 디자이너에서 디자인 타임에 올바르게 표시되도록 구성 요소 및 컨트롤에 적용할 메타데이터 특성을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="26025-126">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="26025-127">[디자인 타임 지원 확장](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="26025-127">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="26025-128">디자인 타임 지원을 제공하는 편집기 및 디자이너와 같은 클래스를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26025-128">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>
