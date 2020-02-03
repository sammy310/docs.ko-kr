---
title: 컨트롤의 특성
ms.date: 03/30/2017
helpviewer_keywords:
- attributes [Windows Forms]
- attributes [Windows Forms], data binding properties
- attributes [Windows Forms], control properties
- attributes [Windows Forms], classes
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
ms.openlocfilehash: b32e4f87e953438a3bb11569445a9270e11c7922
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732131"
---
# <a name="attributes-in-windows-forms-controls"></a><span data-ttu-id="a3280-102">Windows Forms 컨트롤의 특성</span><span class="sxs-lookup"><span data-stu-id="a3280-102">Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="a3280-103">.NET Framework는 사용자 지정 컨트롤 및 구성 요소의 멤버에 적용할 수 있는 다양한 특성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-103">The .NET Framework provides a variety of attributes you can apply to the members of your custom controls and components.</span></span> <span data-ttu-id="a3280-104">이러한 특성 중 일부는 클래스의 런타임 동작에 영향을 주고, 다른 일부는 디자인 타임 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-104">Some of these attributes affect the run-time behavior of a class, and others affect the design-time behavior.</span></span>  
  
## <a name="attributes-for-control-and-component-properties"></a><span data-ttu-id="a3280-105">컨트롤 및 구성 요소 속성의 특성</span><span class="sxs-lookup"><span data-stu-id="a3280-105">Attributes for Control and Component Properties</span></span>  
 <span data-ttu-id="a3280-106">다음 표에서는 사용자 지정 컨트롤 및 구성 요소의 속성이나 다른 멤버에 적용할 수 있는 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-106">The following table shows the attributes you can apply to properties or other members of your custom controls and components.</span></span> <span data-ttu-id="a3280-107">이러한 특성 중 많은 부분을 사용하는 예제는 [방법: Windows Forms 컨트롤에서 특성 적용](how-to-apply-attributes-in-windows-forms-controls.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3280-107">For an example that uses many of these attributes, see [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
|<span data-ttu-id="a3280-108">attribute</span><span class="sxs-lookup"><span data-stu-id="a3280-108">Attribute</span></span>|<span data-ttu-id="a3280-109">Description</span><span class="sxs-lookup"><span data-stu-id="a3280-109">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|<span data-ttu-id="a3280-110">속성이 다른 소스에서 값을 가져오도록 속성에 전달할 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-110">Specifies the value to pass to a property to cause the property to get its value from another source.</span></span> <span data-ttu-id="a3280-111">이를 *앰비언스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-111">This is known as *ambience*.</span></span>|  
|<xref:System.ComponentModel.BrowsableAttribute>|<span data-ttu-id="a3280-112">속성 또는 이벤트를 **속성** 창에 표시할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-112">Specifies whether a property or event should be displayed in a **Properties** window.</span></span>|  
|<xref:System.ComponentModel.CategoryAttribute>|<span data-ttu-id="a3280-113"><xref:System.Windows.Forms.PropertySort.Categorized> 모드로 설정 된 <xref:System.Windows.Forms.PropertyGrid> 컨트롤에 표시 될 때 속성 또는 이벤트를 그룹화 할 범주의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-113">Specifies the name of the category in which to group the property or event when displayed in a <xref:System.Windows.Forms.PropertyGrid> control set to <xref:System.Windows.Forms.PropertySort.Categorized> mode.</span></span>|  
|<xref:System.ComponentModel.DefaultValueAttribute>|<span data-ttu-id="a3280-114">속성의 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-114">Specifies the default value for a property.</span></span>|  
|<xref:System.ComponentModel.DescriptionAttribute>|<span data-ttu-id="a3280-115">속성 또는 이벤트에 대한 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-115">Specifies a description for a property or event.</span></span>|  
|<xref:System.ComponentModel.DisplayNameAttribute>|<span data-ttu-id="a3280-116">인수를 사용하지 않는 속성, 이벤트 또는 `public void` 메서드에 대한 표시 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-116">Specifies the display name for a property, event, or `public void` method that takes no arguments.</span></span>|  
|<xref:System.ComponentModel.EditorAttribute>|<span data-ttu-id="a3280-117">속성을 변경하는 데 사용할 편집기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-117">Specifies the editor to use to change a property.</span></span>|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|<span data-ttu-id="a3280-118">속성 또는 메서드를 편집기에서 볼 수 있도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-118">Specifies that a property or method is viewable in an editor.</span></span>|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|<span data-ttu-id="a3280-119">클래스나 멤버의 컨텍스트 키워드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-119">Specifies the context keyword for a class or member.</span></span>|  
|<xref:System.ComponentModel.LocalizableAttribute>|<span data-ttu-id="a3280-120">속성을 지역화해야 하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-120">Specifies whether a property should be localized.</span></span>|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|<span data-ttu-id="a3280-121">개체의 텍스트 표현이 별표와 같은 문자로 가려져 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-121">Indicates that an object's text representation is obscured by characters such as asterisks.</span></span>|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|<span data-ttu-id="a3280-122">이 특성이 바인딩되는 속성이 디자인 타임에 읽기 전용인지 또는 읽기/쓰기인지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-122">Specifies whether the property this attribute is bound to is read-only or read/write at design time.</span></span>|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|<span data-ttu-id="a3280-123">연결된 속성 값이 변경될 때 속성 그리드를 새로 고쳐야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-123">Indicates that the property grid should refresh when the associated property value changes.</span></span>|  
|<xref:System.ComponentModel.TypeConverterAttribute>|<span data-ttu-id="a3280-124">이 특성이 바인딩되는 개체에 대한 변환기로 사용할 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-124">Specifies what type to use as a converter for the object this attribute is bound to.</span></span>|  
  
## <a name="attributes-for-data-binding-properties"></a><span data-ttu-id="a3280-125">데이터 바인딩 속성의 특성</span><span class="sxs-lookup"><span data-stu-id="a3280-125">Attributes for Data Binding Properties</span></span>  
 <span data-ttu-id="a3280-126">다음 표에서는 사용자 지정 컨트롤과 구성 요소가 데이터 바인딩과 상호 작용하는 방법을 지정하는 데 적용할 수 있는 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-126">The following table shows the attributes you can apply to specify how your custom controls and components interact with data binding.</span></span>  
  
|<span data-ttu-id="a3280-127">attribute</span><span class="sxs-lookup"><span data-stu-id="a3280-127">Attribute</span></span>|<span data-ttu-id="a3280-128">Description</span><span class="sxs-lookup"><span data-stu-id="a3280-128">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.BindableAttribute>|<span data-ttu-id="a3280-129">속성이 일반적으로 바인딩에 사용되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-129">Specifies whether a property is typically used for binding.</span></span>|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|<span data-ttu-id="a3280-130">구성 요소의 데이터 소스와 데이터 멤버 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-130">Specifies the data source and data member properties for a component.</span></span>|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|<span data-ttu-id="a3280-131">구성 요소의 기본 바인딩 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-131">Specifies the default binding property for a component.</span></span>|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|<span data-ttu-id="a3280-132">구성 요소의 데이터 소스와 데이터 멤버 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-132">Specifies the data source and data member properties for a component.</span></span>|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|<span data-ttu-id="a3280-133">특성 리디렉션을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-133">Enables attribute redirection.</span></span>|  
  
## <a name="attributes-for-classes"></a><span data-ttu-id="a3280-134">클래스의 특성</span><span class="sxs-lookup"><span data-stu-id="a3280-134">Attributes for Classes</span></span>  
 <span data-ttu-id="a3280-135">다음 표에서는 디자인 타임에 사용자 지정 컨트롤 및 구성 요소의 동작을 지정하는 데 적용할 수 있는 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-135">The following table shows the attributes you can apply to specify the behavior of your custom controls and components at design time.</span></span>  
  
|<span data-ttu-id="a3280-136">attribute</span><span class="sxs-lookup"><span data-stu-id="a3280-136">Attribute</span></span>|<span data-ttu-id="a3280-137">Description</span><span class="sxs-lookup"><span data-stu-id="a3280-137">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|<span data-ttu-id="a3280-138">구성 요소의 기본 이벤트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-138">Specifies the default event for a component.</span></span>|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|<span data-ttu-id="a3280-139">구성 요소의 기본 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-139">Specifies the default property for a component.</span></span>|  
|<xref:System.ComponentModel.DesignerAttribute>|<span data-ttu-id="a3280-140">구성 요소에 대한 디자인 타임 서비스를 구현하는 데 사용되는 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-140">Specifies the class used to implement design-time services for a component.</span></span>|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|<span data-ttu-id="a3280-141">클래스의 디자이너가 특정 범주에 속하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-141">Specifies that the designer for a class belongs to a certain category.</span></span>|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|<span data-ttu-id="a3280-142">도구 상자 항목의 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-142">Represents an attribute of a toolbox item.</span></span>|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|<span data-ttu-id="a3280-143">도구 상자 항목에 사용할 필터 문자열과 필터 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3280-143">Specifies the filter string and filter type to use for a Toolbox item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3280-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3280-144">See also</span></span>

- <xref:System.Attribute>
- [<span data-ttu-id="a3280-145">방법: Windows Forms 컨트롤에서 특성 적용</span><span class="sxs-lookup"><span data-stu-id="a3280-145">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- <span data-ttu-id="a3280-146">[디자인 타임 지원 확장](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="a3280-146">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- [<span data-ttu-id="a3280-147">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="a3280-147">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
