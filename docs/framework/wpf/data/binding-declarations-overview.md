---
title: 바인딩 선언 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- markup extensions [WPF]
- data binding [WPF], declarations
- object element syntax [WPF]
- binding data [WPF], declarations
- syntax [WPF], object elements
- binding declarations [WPF]
ms.assetid: b97fd626-4c0d-4761-872a-2bca5820da2c
ms.openlocfilehash: c0fcbc8054272356c39ba7925041ecef05a0322c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165271"
---
# <a name="binding-declarations-overview"></a><span data-ttu-id="83dee-102">바인딩 선언 개요</span><span class="sxs-lookup"><span data-stu-id="83dee-102">Binding Declarations Overview</span></span>
<span data-ttu-id="83dee-103">이 항목에서는 바인딩을 선언할 수 있는 여러 가지 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-103">This topic discusses the different ways you can declare a binding.</span></span>  

<a name="Prereq"></a>   
## <a name="prerequisites"></a><span data-ttu-id="83dee-104">전제 조건</span><span class="sxs-lookup"><span data-stu-id="83dee-104">Prerequisites</span></span>  
 <span data-ttu-id="83dee-105">이 항목은 태그 확장의 개념 및 사용 방법에 익숙하다는 것을 전제로 합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-105">Before reading this topic, it is important that you are familiar with the concept and usage of markup extensions.</span></span> <span data-ttu-id="83dee-106">태그 확장에 대한 자세한 내용은 [XAML 태그 확장 및 WPF XAML](../advanced/markup-extensions-and-wpf-xaml.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83dee-106">For more information about markup extensions, see [Markup Extensions and WPF XAML](../advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="83dee-107">이 항목에서는 데이터 바인딩 개념에 대해 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-107">This topic does not cover data binding concepts.</span></span> <span data-ttu-id="83dee-108">데이터 바인딩 개념에 대한 자세한 내용은 [데이터 바인딩 개요](data-binding-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83dee-108">For a discussion of data binding concepts, see [Data Binding Overview](data-binding-overview.md).</span></span>  
  
<a name="BindinginXAML"></a>   
## <a name="declaring-a-binding-in-xaml"></a><span data-ttu-id="83dee-109">XAML에서 바인딩 선언</span><span class="sxs-lookup"><span data-stu-id="83dee-109">Declaring a Binding in XAML</span></span>  
 <span data-ttu-id="83dee-110">이 섹션에서는 XAML에서 바인딩을 선언하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-110">This section discusses how to declare a binding in XAML.</span></span>  
  
<a name="MarkupExtensionSyntax"></a>   
### <a name="markup-extension-usage"></a><span data-ttu-id="83dee-111">태그 확장 사용</span><span class="sxs-lookup"><span data-stu-id="83dee-111">Markup Extension Usage</span></span>  
 <xref:System.Windows.Data.Binding> <span data-ttu-id="83dee-112">태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-112">is a markup extension.</span></span> <span data-ttu-id="83dee-113">바인딩 확장을 사용하여 바인딩을 선언할 때 선언은 `Binding` 키워드 뒤에 일련의 절이 쉼표(,)로 구분된 형태로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-113">When you use the binding extension to declare a binding, the declaration consists of a series of clauses following the `Binding` keyword and separated by commas (,).</span></span> <span data-ttu-id="83dee-114">바인딩 선언의 절 순서는 중요하지 않으며 수많은 조합이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-114">The clauses in the binding declaration can be in any order and there are many possible combinations.</span></span> <span data-ttu-id="83dee-115">절을 *이름*=*값* 위치 쌍 *이름* 이름인 합니다 <xref:System.Windows.Data.Binding> 속성 및 *값* 는 속성에 대해 설정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-115">The clauses are *Name*=*Value* pairs where *Name* is the name of the <xref:System.Windows.Data.Binding> property and *Value* is the value you are setting for the property.</span></span>  
  
 <span data-ttu-id="83dee-116">태그에서 바인딩 선언 문자열을 만들 때는 대상 개체의 특정 종속성 속성에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-116">When creating binding declaration strings in markup, they must be attached to the specific dependency property of a target object.</span></span> <span data-ttu-id="83dee-117">다음 예제에서는 바인딩하는 방법을 보여줍니다 합니다 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 속성 바인딩 확장을 사용 하 여, 지정 하는 <xref:System.Windows.Data.Binding.Source%2A> 및 <xref:System.Windows.Data.Binding.Path%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="83dee-117">The following example shows how to bind the <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property using the binding extension, specifying the <xref:System.Windows.Data.Binding.Source%2A> and <xref:System.Windows.Data.Binding.Path%2A> properties.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#L37-L37)]  
  
 <span data-ttu-id="83dee-118">대부분의 속성을 지정할 수 있습니다는 <xref:System.Windows.Data.Binding> 이 이런 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-118">You can specify most of the properties of the <xref:System.Windows.Data.Binding> class this way.</span></span> <span data-ttu-id="83dee-119">목록은 물론 바인딩 확장에 대 한 자세한 내용은 <xref:System.Windows.Data.Binding> 바인딩 확장을 사용 하 여 설정할 수 없는 속성 참조를 [바인딩 태그 확장](../advanced/binding-markup-extension.md) 개요.</span><span class="sxs-lookup"><span data-stu-id="83dee-119">For more information about the binding extension as well as for a list of <xref:System.Windows.Data.Binding> properties that cannot be set using the binding extension, see the [Binding Markup Extension](../advanced/binding-markup-extension.md) overview.</span></span>  
  
<a name="ObjectElementSyntax"></a>   
### <a name="object-element-syntax"></a><span data-ttu-id="83dee-120">개체 요소 구문</span><span class="sxs-lookup"><span data-stu-id="83dee-120">Object Element Syntax</span></span>  
 <span data-ttu-id="83dee-121">개체 요소 구문은 바인딩 선언을 만드는 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-121">Object element syntax is an alternative to creating the binding declaration.</span></span> <span data-ttu-id="83dee-122">대부분의 경우 태그 확장 또는 개체 요소 구문을 사용할 때의 특별한 이점은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-122">In most cases, there is no particular advantage to using either the markup extension or the object element syntax.</span></span> <span data-ttu-id="83dee-123">그러나 태그 확장을 사용할 수 없는 시나리오, 예를 들어 속성 값이 문자열 형식이 아니어서 형식 변환이 존재하지 않는 경우에는 개체 요소 구문을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-123">However, in cases which the markup extension does not support your scenario, such as when your property value is of a non-string type for which no type conversion exists, you need to use the object element syntax.</span></span>  
  
 <span data-ttu-id="83dee-124">다음은 개체 요소 구문 및 태그 확장 사용의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-124">The following is an example of both the object element syntax and the markup extension usage:</span></span>  
  
 [!code-xaml[BindConversionMarkup#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindConversionMarkup/CSharp/Page1.xaml#1)]  
  
 <span data-ttu-id="83dee-125">이 예제에서는 바인딩하는 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 확장 구문을 사용 하 여 바인딩을 선언 하 여 속성.</span><span class="sxs-lookup"><span data-stu-id="83dee-125">The example binds the <xref:System.Windows.Controls.TextBlock.Foreground%2A> property by declaring a binding using the extension syntax.</span></span> <span data-ttu-id="83dee-126">바인딩 선언은 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성 개체 요소 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-126">The binding declaration for the <xref:System.Windows.Controls.TextBlock.Text%2A> property uses the object element syntax.</span></span>  
  
 <span data-ttu-id="83dee-127">다양한 용어에 대한 자세한 내용은 [XAML 구문 정보](../advanced/xaml-syntax-in-detail.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83dee-127">For more information about the different terms, see [XAML Syntax In Detail](../advanced/xaml-syntax-in-detail.md).</span></span>  
  
<a name="MBandPB"></a>   
### <a name="multibinding-and-prioritybinding"></a><span data-ttu-id="83dee-128">MultiBinding 및 PriorityBinding</span><span class="sxs-lookup"><span data-stu-id="83dee-128">MultiBinding and PriorityBinding</span></span>  
 <xref:System.Windows.Data.MultiBinding> <span data-ttu-id="83dee-129">및 <xref:System.Windows.Data.PriorityBinding> XAML 확장 구문을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-129">and <xref:System.Windows.Data.PriorityBinding> do not support the XAML extension syntax.</span></span> <span data-ttu-id="83dee-130">따라서 선언 하는 경우 개체 요소 구문을 사용 해야 합니다 있습니다를 <xref:System.Windows.Data.MultiBinding> 또는 <xref:System.Windows.Data.PriorityBinding> XAML에서.</span><span class="sxs-lookup"><span data-stu-id="83dee-130">Therefore, you must use the object element syntax if you are declaring a <xref:System.Windows.Data.MultiBinding> or a <xref:System.Windows.Data.PriorityBinding> in XAML.</span></span>  
  
<a name="BindinginCode"></a>   
## <a name="creating-a-binding-in-code"></a><span data-ttu-id="83dee-131">코드에서 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="83dee-131">Creating a Binding in Code</span></span>  
 <span data-ttu-id="83dee-132">바인딩을 지정 하는 또 다른 방법은 속성을 직접 설정 하는 것을 <xref:System.Windows.Data.Binding> 코드의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-132">Another way to specify a binding is to set properties directly on a <xref:System.Windows.Data.Binding> object in code.</span></span> <span data-ttu-id="83dee-133">다음 예제에서는 만드는 방법을 보여 줍니다는 <xref:System.Windows.Data.Binding> 개체 및 코드에서 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-133">The following example shows how to create a <xref:System.Windows.Data.Binding> object and specify the properties in code.</span></span>  <span data-ttu-id="83dee-134">이 예에서 `TheConverter` 를 구현 하는 개체는 <xref:System.Windows.Data.IValueConverter> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-134">In this example, `TheConverter` is an object that implements the <xref:System.Windows.Data.IValueConverter> interface.</span></span>  
  
 [!code-csharp[BindConversion#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindConversion/CSharp/Window1.xaml.cs#1)]
 [!code-vb[BindConversion#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindConversion/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="83dee-135">바인딩하는 개체가 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 호출할 수 있습니다 합니다 `SetBinding` 메서드를 사용 하는 대신 직접 개체 <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-135">If the object you are binding is a <xref:System.Windows.FrameworkElement> or a <xref:System.Windows.FrameworkContentElement> you can call the `SetBinding` method on your object directly instead of using <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="83dee-136">예제는 [코드에서 바인딩 만들기](how-to-create-a-binding-in-code.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83dee-136">For an example, see [Create a Binding in Code](how-to-create-a-binding-in-code.md).</span></span>  
  
<a name="Path_Syntax"></a>   
## <a name="binding-path-syntax"></a><span data-ttu-id="83dee-137">바인딩 경로 구문</span><span class="sxs-lookup"><span data-stu-id="83dee-137">Binding Path Syntax</span></span>  
 <span data-ttu-id="83dee-138">사용 된 <xref:System.Windows.Data.Binding.Path%2A> 속성에 바인딩할 원본 값을 지정 하려면:</span><span class="sxs-lookup"><span data-stu-id="83dee-138">Use the <xref:System.Windows.Data.Binding.Path%2A> property to specify the source value you want to bind to:</span></span>  
  
-   <span data-ttu-id="83dee-139">가장 간단한 경우에는 <xref:System.Windows.Data.Binding.Path%2A> 속성 값이 같은 바인딩에 사용할 소스 개체의 속성 이름을 `Path=PropertyName`입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-139">In the simplest case, the <xref:System.Windows.Data.Binding.Path%2A> property value is the name of the property of the source object to use for the binding, such as `Path=PropertyName`.</span></span>  
  
-   <span data-ttu-id="83dee-140">와 같이 유사한 구문을 사용 하 여 속성의 하위 속성을 지정할 수 있습니다 C#입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-140">Subproperties of a property can be specified by a similar syntax as in C#.</span></span> <span data-ttu-id="83dee-141">예를 들어 `Path=ShoppingCart.Order` 절은 개체 또는 속성 `ShoppingCart`의 하위 속성 `Order`에 대한 바인딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-141">For instance, the clause `Path=ShoppingCart.Order` sets the binding to the subproperty `Order` of the object or property `ShoppingCart`.</span></span>  
  
-   <span data-ttu-id="83dee-142">연결된 속성에 바인딩하려면 연결된 속성을 괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-142">To bind to an attached property, place parentheses around the attached property.</span></span> <span data-ttu-id="83dee-143">예를 들어 연결된 된 속성에 바인딩할 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, 구문은 `Path=(DockPanel.Dock)`합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-143">For example, to bind to the attached property <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, the syntax is `Path=(DockPanel.Dock)`.</span></span>  
  
-   <span data-ttu-id="83dee-144">속성의 인덱서는 인덱서가 적용되는 속성 이름 뒤에 대괄호로 묶어서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-144">Indexers of a property can be specified within square brackets following the property name where the indexer is applied.</span></span> <span data-ttu-id="83dee-145">예를 들어 `Path=ShoppingCart[0]` 절은 속성의 내부 인덱싱에서 리터럴 문자열 "0"을 처리하는 방법에 해당하는 인덱스에 대한 바인딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-145">For instance, the clause `Path=ShoppingCart[0]` sets the binding to the index that corresponds to how your property's internal indexing handles the literal string "0".</span></span> <span data-ttu-id="83dee-146">중첩된 인덱서도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-146">Nested indexers are also supported.</span></span>  
  
-   <span data-ttu-id="83dee-147">인덱서 및 하위 속성 함께 사용할 수 있습니다는 `Path` 절 예를 들어,</span><span class="sxs-lookup"><span data-stu-id="83dee-147">Indexers and subproperties can be mixed in a `Path` clause; for example,</span></span> `Path=ShoppingCart.ShippingInfo[MailingAddress,Street].`  
  
-   <span data-ttu-id="83dee-148">여러 인덱서 매개 변수를 쉼표(,)로 구분하여 인덱서 안에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-148">Inside indexers you can have multiple indexer parameters separated by commas (,).</span></span> <span data-ttu-id="83dee-149">각 매개 변수의 형식은 괄호를 사용하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-149">The type of each parameter can be specified with parentheses.</span></span> <span data-ttu-id="83dee-150">예를 들어 `Path="[(sys:Int32)42,(sys:Int32)24]"`를 사용할 수 있으며 여기서 `sys`는 `System` 네임스페이스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-150">For example, you can have `Path="[(sys:Int32)42,(sys:Int32)24]"`, where `sys` is mapped to the `System` namespace.</span></span>  
  
-   <span data-ttu-id="83dee-151">소스가 컬렉션 뷰인 경우 슬래시(/)를 사용하여 현재 항목을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-151">When the source is a collection view, the current item can be specified with a slash (/).</span></span> <span data-ttu-id="83dee-152">예를 들어 `Path=/` 절은 뷰의 현재 항목에 대한 바인딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-152">For example, the clause `Path=/` sets the binding to the current item in the view.</span></span> <span data-ttu-id="83dee-153">소스가 컬렉션인 경우 이 구문은 기본 컬렉션 뷰의 현재 항목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-153">When the source is a collection, this syntax specifies the current item of the default collection view.</span></span>  
  
-   <span data-ttu-id="83dee-154">속성 이름과 슬래시를 결합하여 컬렉션인 속성을 트래버스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-154">Property names and slashes can be combined to traverse properties that are collections.</span></span> <span data-ttu-id="83dee-155">예를 들어 `Path=/Offices/ManagerName`은 소스 컬렉션의 현재 항목을 지정하며 여기에는 컬렉션인 `Offices` 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-155">For example, `Path=/Offices/ManagerName` specifies the current item of the source collection, which contains an `Offices` property that is also a collection.</span></span> <span data-ttu-id="83dee-156">현재 항목은 `ManagerName` 속성을 포함하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-156">Its current item is an object that contains a `ManagerName` property.</span></span>  
  
-   <span data-ttu-id="83dee-157">필요에 따라 마침표(.) 경로를 사용하여 현재 소스에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-157">Optionally, a period (.) path can be used to bind to the current source.</span></span> <span data-ttu-id="83dee-158">예를 들어 `Text="{Binding}"`은 `Text="{Binding Path=.}"`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-158">For example, `Text="{Binding}"` is equivalent to `Text="{Binding Path=.}"`.</span></span>  
  
### <a name="escaping-mechanism"></a><span data-ttu-id="83dee-159">이스케이프 메커니즘</span><span class="sxs-lookup"><span data-stu-id="83dee-159">Escaping Mechanism</span></span>  
  
-   <span data-ttu-id="83dee-160">인덱서([ ]) 안의 캐럿 문자(^)는 다음 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-160">Inside indexers ([ ]), the caret character (^) escapes the next character.</span></span>  
  
-   <span data-ttu-id="83dee-161">설정한 경우 <xref:System.Windows.Data.Binding.Path%2A> XAML에도 해야 이스케이프 (XML 엔터티 사용) XML 언어 정의와 관련 된 특정 문자:</span><span class="sxs-lookup"><span data-stu-id="83dee-161">If you set <xref:System.Windows.Data.Binding.Path%2A> in XAML, you also need to escape (using XML entities) certain characters that are special to the XML language definition:</span></span>  
  
    -   <span data-ttu-id="83dee-162">"&" 문자를 이스케이프하려면 `&`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-162">Use `&` to escape the character "&".</span></span>  
  
    -   <span data-ttu-id="83dee-163">">" 태그를 이스케이프하려면 `>`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-163">Use `>` to escape the end tag ">".</span></span>  
  
-   <span data-ttu-id="83dee-164">또한 태그 확장 구문을 사용하여 특성의 전체 바인딩을 설명하는 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 태그 확장 파서와 관련된 문자를 이스케이프(백슬래시 \\ 사용)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-164">Additionally, if you describe the entire binding in an attribute using the markup extension syntax, you need to escape (using backslash \\) characters that are special to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] markup extension parser:</span></span>  
  
    -   <span data-ttu-id="83dee-165">백슬래시(\\)는 그 자체로 이스케이프 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-165">Backslash (\\) is the escape character itself.</span></span>  
  
    -   <span data-ttu-id="83dee-166">등호(=)는 속성 값에서 속성 이름을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-166">The equal sign (=) separates property name from property value.</span></span>  
  
    -   <span data-ttu-id="83dee-167">쉼표(,)는 속성을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-167">Comma (,) separates properties.</span></span>  
  
    -   <span data-ttu-id="83dee-168">오른쪽 중괄호(})는 태그 확장의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-168">The right curly brace (}) is the end of a markup extension.</span></span>  
  
<a name="Default"></a>   
## <a name="default-behaviors"></a><span data-ttu-id="83dee-169">기본 동작</span><span class="sxs-lookup"><span data-stu-id="83dee-169">Default Behaviors</span></span>  
 <span data-ttu-id="83dee-170">선언에서 지정되지 않은 경우 기본 동작은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-170">The default behavior is as follows if not specified in the declaration.</span></span>  
  
-   <span data-ttu-id="83dee-171">바인딩 소스 값과 바인딩 대상 값 간에 형식을 변환하는 기본 변환기가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-171">A default converter is created that tries to do a type conversion between the binding source value and the binding target value.</span></span> <span data-ttu-id="83dee-172">변환을 만들 수 없는 경우 기본 변환기는 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-172">If a conversion cannot be made, the default converter returns `null`.</span></span>  
  
-   <span data-ttu-id="83dee-173">설정 하지 않은 경우 <xref:System.Windows.Data.Binding.ConverterCulture%2A>, 바인딩 엔진은는 `Language` 바인딩 대상 개체의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-173">If you do not set <xref:System.Windows.Data.Binding.ConverterCulture%2A>, the binding engine uses the `Language` property of the binding target object.</span></span> <span data-ttu-id="83dee-174">XAML에서 이 값을 명시적으로 설정하지 않은 경우 기본적으로 "en-US"로 설정되거나 페이지 루트 요소(또는 임의의 요소)에서 값이 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-174">In XAML, this defaults to "en-US" or inherits the value from the root element (or any element) of the page, if one has been explicitly set.</span></span>  
  
-   <span data-ttu-id="83dee-175">바인딩으로 있다면 이미 데이터 컨텍스트가 (예를 들어의 데이터 컨텍스트가 상속 된 부모 요소에서), 및 항목 또는 해당 컨텍스트에 의해 반환 되는 컬렉션에 적합 한 바인딩을 추가 경로 수정 없이 바인딩 선언의 절을 사용 하지를 전혀 가질 수 있습니다. `{Binding}` 이것이 종종 데이터 스타일링에 바인딩이 컬렉션에 대해 작동 하는 위치에 대 한 바인딩이 지정 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-175">As long as the binding already has a data context (for instance, the inherited data context coming from a parent element), and whatever item or collection being returned by that context is appropriate for binding without requiring further path modification, a binding declaration can have no clauses at all: `{Binding}` This is often the way a binding is specified for data styling, where the binding acts upon a collection.</span></span> <span data-ttu-id="83dee-176">자세한 내용은 [바인딩 소스 개요](binding-sources-overview.md)의 "전체 개체를 바인딩 소스로 사용" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83dee-176">For more information, see the "Entire Objects Used as a Binding Source" section in the [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
-   <span data-ttu-id="83dee-177">기본 <xref:System.Windows.Data.Binding.Mode%2A> 간의 단방향 및 양방향 바인딩되는 종속성 속성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-177">The default <xref:System.Windows.Data.Binding.Mode%2A> varies between one-way and two-way depending on the dependency property that is being bound.</span></span> <span data-ttu-id="83dee-178">바인딩이 원하는 대로 동작하도록 항상 바인딩 모드를 명시적으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-178">You can always declare the binding mode explicitly to ensure that your binding has the desired behavior.</span></span> <span data-ttu-id="83dee-179">일반적으로 사용자가 편집 가능한 컨트롤 속성에서와 같은 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType>, 기본값 양방향 바인딩으로 설정 되지만 대부분의 다른 속성 기본값은 단방향 바인딩으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-179">In general, user-editable control properties, such as <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A?displayProperty=nameWithType>, default to two-way bindings, whereas most other properties default to one-way bindings.</span></span>  
  
-   <span data-ttu-id="83dee-180">기본값 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값에 따라 다릅니다 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> 고 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> 도 바인딩된 종속성 속성에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-180">The default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value varies between <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> and <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> depending on the bound dependency property as well.</span></span> <span data-ttu-id="83dee-181">대부분의 종속성 속성에 대한 기본값이 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>인 반면 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 속성의 기본값은 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>입니다.</span><span class="sxs-lookup"><span data-stu-id="83dee-181">The default value for most dependency properties is <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, while the <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property has a default value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83dee-182">참고자료</span><span class="sxs-lookup"><span data-stu-id="83dee-182">See also</span></span>

- [<span data-ttu-id="83dee-183">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="83dee-183">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="83dee-184">방법 항목</span><span class="sxs-lookup"><span data-stu-id="83dee-184">How-to Topics</span></span>](data-binding-how-to-topics.md)
- [<span data-ttu-id="83dee-185">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="83dee-185">Data Binding</span></span>](../advanced/optimizing-performance-data-binding.md)
- [<span data-ttu-id="83dee-186">PropertyPath XAML 구문</span><span class="sxs-lookup"><span data-stu-id="83dee-186">PropertyPath XAML Syntax</span></span>](../advanced/propertypath-xaml-syntax.md)
