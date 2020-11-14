---
title: 구성 요소 만들기 및 사용
ms.date: 07/20/2015
helpviewer_keywords:
- components [Visual Basic]
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
ms.openlocfilehash: 106b8791ee5cb3db95759ccca2fddd799661ef3c
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282070"
---
# <a name="creating-and-using-components-in-visual-basic"></a><span data-ttu-id="ca7e8-102">Visual Basic에서 구성 요소 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="ca7e8-102">Creating and Using Components in Visual Basic</span></span>

<span data-ttu-id="ca7e8-103">*구성 요소* 는 <xref:System.ComponentModel.IComponent?displayProperty=nameWithType> 인터페이스를 구현하는 클래스이거나 <xref:System.ComponentModel.IComponent>를 구현하는 클래스에서 직접 또는 간접적으로 파생되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-103">A *component* is a class that implements the <xref:System.ComponentModel.IComponent?displayProperty=nameWithType> interface or that derives directly or indirectly from a class that implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="ca7e8-104">.NET 구성 요소는 재사용 가능한 개체이고, 다른 개체와 상호 작용할 수 있으며, 외부 리소스 및 디자인 타임 지원에 대한 제어를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-104">A .NET component is an object that is reusable, can interact with other objects, and provides control over external resources and design-time support.</span></span>  
  
 <span data-ttu-id="ca7e8-105">구성 요소의 중요한 기능은 디자인할 수 있다는 것입니다. 즉, Visual Studio 통합 개발 환경에서 구성 요소인 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-105">An important feature of components is that they are designable, which means that a class that is a component can be used in the Visual Studio Integrated Development Environment.</span></span> <span data-ttu-id="ca7e8-106">구성 요소는 도구 상자에 추가하고, 양식에 끌어서 놓고, 디자인 화면에서 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-106">A component can be added to the Toolbox, dragged and dropped onto a form, and manipulated on a design surface.</span></span> <span data-ttu-id="ca7e8-107">구성 요소에 대한 기본 디자인 타임 지원은 .NET에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-107">Base design-time support for components is built into .NET.</span></span> <span data-ttu-id="ca7e8-108">구성 요소 개발자는 기본 디자인 타임 기능을 이용하기 위해 추가 작업을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-108">A component developer does not have to do any additional work to take advantage of the base design-time functionality.</span></span>  
  
 <span data-ttu-id="ca7e8-109">*컨트롤* 과 구성 요소는 둘 다 디자인 가능하다는 점에서 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-109">A *control* is similar to a component, as both are designable.</span></span> <span data-ttu-id="ca7e8-110">그러나 컨트롤은 사용자 인터페이스를 제공하지만 구성 요소는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-110">However, a control provides a user interface, while a component does not.</span></span> <span data-ttu-id="ca7e8-111">컨트롤은 기본 컨트롤 클래스인 <xref:System.Windows.Forms.Control> 또는 <xref:System.Web.UI.Control> 중 하나에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-111">A control must derive from one of the base control classes: <xref:System.Windows.Forms.Control> or <xref:System.Web.UI.Control>.</span></span>  
  
## <a name="when-to-create-a-component"></a><span data-ttu-id="ca7e8-112">구성 요소를 만들어야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="ca7e8-112">When to Create a Component</span></span>  

 <span data-ttu-id="ca7e8-113">클래스가 Design Surface(예: Windows Forms 또는 Web Forms 디자이너)에서 사용되지만 사용자 인터페이스가 없는 경우 클래스는 구성 요소로서, <xref:System.ComponentModel.IComponent>를 구현하거나 <xref:System.ComponentModel.IComponent>를 직접 또는 간접적으로 구현하는 클래스에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-113">If your class will be used on a design surface (such as the Windows Forms or Web Forms Designer) but has no user interface, it should be a component and implement <xref:System.ComponentModel.IComponent>, or derive from a class that directly or indirectly implements <xref:System.ComponentModel.IComponent>.</span></span>  
  
 <span data-ttu-id="ca7e8-114"><xref:System.ComponentModel.Component> 및 <xref:System.ComponentModel.MarshalByValueComponent> 클래스는 <xref:System.ComponentModel.IComponent> 인터페이스의 기본 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-114">The <xref:System.ComponentModel.Component> and <xref:System.ComponentModel.MarshalByValueComponent> classes are base implementations of the <xref:System.ComponentModel.IComponent> interface.</span></span> <span data-ttu-id="ca7e8-115">이러한 클래스 간의 기본 차이점은 <xref:System.ComponentModel.Component> 클래스는 참조에 의해 마샬링되지만 <xref:System.ComponentModel.IComponent>는 값에 의해 마샬링된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-115">The main difference between these classes is that the <xref:System.ComponentModel.Component> class is marshaled by reference, while <xref:System.ComponentModel.IComponent> is marshaled by value.</span></span> <span data-ttu-id="ca7e8-116">다음 목록에서는 구현에 대한 다양한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-116">The following list provides broad guidelines for implementers.</span></span>  
  
- <span data-ttu-id="ca7e8-117">구성 요소가 참조에 의해 마샬링되어야 하는 경우 <xref:System.ComponentModel.Component>에서 파생합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-117">If your component needs to be marshaled by reference, derive from <xref:System.ComponentModel.Component>.</span></span>  
  
- <span data-ttu-id="ca7e8-118">구성 요소가 값에 의해 마샬링되어야 하는 경우 <xref:System.ComponentModel.MarshalByValueComponent>에서 파생합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-118">If your component needs to be marshaled by value, derive from <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
- <span data-ttu-id="ca7e8-119">단일 상속으로 인해 구성 요소가 기본 구현 중 하나에서 파생될 수 없는 경우 <xref:System.ComponentModel.IComponent>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-119">If your component cannot derive from one of the base implementations due to single inheritance, implement <xref:System.ComponentModel.IComponent>.</span></span>  
  
## <a name="component-classes"></a><span data-ttu-id="ca7e8-120">구성 요소 클래스</span><span class="sxs-lookup"><span data-stu-id="ca7e8-120">Component Classes</span></span>  

 <span data-ttu-id="ca7e8-121"><xref:System.ComponentModel> 네임스페이스는 구성 요소와 컨트롤의 런타임 및 디자인 타임 동작을 구현하는 데 사용되는 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-121">The <xref:System.ComponentModel> namespace provides classes that are used to implement the run-time and design-time behavior of components and controls.</span></span> <span data-ttu-id="ca7e8-122">이 네임스페이스에는 특성 및 형식 변환기를 구현하고, 데이터 소스에 바인딩하고, 구성 요소 사용을 허가하기 위한 기본 클래스 및 인터페이스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-122">This namespace includes the base classes and interfaces for implementing attributes and type converters, binding to data sources, and licensing components.</span></span>  
  
 <span data-ttu-id="ca7e8-123">핵심 구성 요소 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-123">The core component classes are:</span></span>  
  
- <span data-ttu-id="ca7e8-124"><xref:System.ComponentModel.Component>.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-124"><xref:System.ComponentModel.Component>.</span></span> <span data-ttu-id="ca7e8-125"><xref:System.ComponentModel.IComponent> 인터페이스에 대한 기본 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-125">A base implementation for the <xref:System.ComponentModel.IComponent> interface.</span></span> <span data-ttu-id="ca7e8-126">이 클래스를 통해 애플리케이션 간에 개체를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-126">This class enables object sharing between applications.</span></span>  
  
- <span data-ttu-id="ca7e8-127"><xref:System.ComponentModel.MarshalByValueComponent>.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-127"><xref:System.ComponentModel.MarshalByValueComponent>.</span></span> <span data-ttu-id="ca7e8-128"><xref:System.ComponentModel.IComponent> 인터페이스에 대한 기본 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-128">A base implementation for the <xref:System.ComponentModel.IComponent> interface.</span></span>  
  
- <span data-ttu-id="ca7e8-129"><xref:System.ComponentModel.Container>.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-129"><xref:System.ComponentModel.Container>.</span></span> <span data-ttu-id="ca7e8-130"><xref:System.ComponentModel.IContainer> 인터페이스에 대한 기본 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-130">The base implementation for the <xref:System.ComponentModel.IContainer> interface.</span></span> <span data-ttu-id="ca7e8-131">이 클래스는 0 또는 추가 구성 요소를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-131">This class encapsulates zero or more components.</span></span>  
  
 <span data-ttu-id="ca7e8-132">구성 요소 라이선싱에 사용되는 일부 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-132">Some of the classes used for component licensing are:</span></span>  
  
- <span data-ttu-id="ca7e8-133"><xref:System.ComponentModel.License>.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-133"><xref:System.ComponentModel.License>.</span></span> <span data-ttu-id="ca7e8-134">모든 라이선스에 대한 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-134">The abstract base class for all licenses.</span></span> <span data-ttu-id="ca7e8-135">라이선스는 구성 요소의 특정 인스턴스에 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-135">A license is granted to a specific instance of a component.</span></span>  
  
- <span data-ttu-id="ca7e8-136"><xref:System.ComponentModel.LicenseManager>.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-136"><xref:System.ComponentModel.LicenseManager>.</span></span> <span data-ttu-id="ca7e8-137">라이선스를 구성 요소에 추가하고 <xref:System.ComponentModel.LicenseProvider>를 관리하기 위한 속성과 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-137">Provides properties and methods to add a license to a component and to manage a <xref:System.ComponentModel.LicenseProvider>.</span></span>  
  
- <span data-ttu-id="ca7e8-138"><xref:System.ComponentModel.LicenseProvider>.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-138"><xref:System.ComponentModel.LicenseProvider>.</span></span> <span data-ttu-id="ca7e8-139">라이선스 공급자를 구현하기 위한 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-139">The abstract base class for implementing a license provider.</span></span>  
  
- <span data-ttu-id="ca7e8-140"><xref:System.ComponentModel.LicenseProviderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-140"><xref:System.ComponentModel.LicenseProviderAttribute>.</span></span> <span data-ttu-id="ca7e8-141">클래스와 함께 사용할 <xref:System.ComponentModel.LicenseProvider> 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-141">Specifies the <xref:System.ComponentModel.LicenseProvider> class to use with a class.</span></span>  
  
 <span data-ttu-id="ca7e8-142">구성 요소를 설명 및 유지하는 데 일반적으로 사용되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-142">Classes commonly used for describing and persisting components.</span></span>  
  
- <span data-ttu-id="ca7e8-143"><xref:System.ComponentModel.TypeDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-143"><xref:System.ComponentModel.TypeDescriptor>.</span></span> <span data-ttu-id="ca7e8-144">구성 요소의 특성, 속성 및 이벤트와 같이, 구성 요소의 특성에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-144">Provides information about the characteristics for a component, such as its attributes, properties, and events.</span></span>  
  
- <span data-ttu-id="ca7e8-145"><xref:System.ComponentModel.EventDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-145"><xref:System.ComponentModel.EventDescriptor>.</span></span> <span data-ttu-id="ca7e8-146">이벤트에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-146">Provides information about an event.</span></span>  
  
- <span data-ttu-id="ca7e8-147"><xref:System.ComponentModel.PropertyDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-147"><xref:System.ComponentModel.PropertyDescriptor>.</span></span> <span data-ttu-id="ca7e8-148">속성에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-148">Provides information about a property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ca7e8-149">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ca7e8-149">Related Sections</span></span>  

 [<span data-ttu-id="ca7e8-150">컨트롤 및 구성 요소 제작 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ca7e8-150">Troubleshooting Control and Component Authoring</span></span>](/dotnet/desktop/winforms/controls/troubleshooting-control-and-component-authoring)  
 <span data-ttu-id="ca7e8-151">일반적인 문제 해결 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca7e8-151">Explains how to fix common problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7e8-152">참조</span><span class="sxs-lookup"><span data-stu-id="ca7e8-152">See also</span></span>

- [<span data-ttu-id="ca7e8-153">방법: Windows Forms에서 디자인 타임 지원 액세스</span><span class="sxs-lookup"><span data-stu-id="ca7e8-153">How to: Access Design-Time Support in Windows Forms</span></span>](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time)
