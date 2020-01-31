---
title: 컨트롤에서 특성 적용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: b8ecd516cf6bb189c6ad1b208dd8e3a5444f001c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741484"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="e550e-102">방법: Windows Forms 컨트롤에서 특성 적용</span><span class="sxs-lookup"><span data-stu-id="e550e-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="e550e-103">디자인 환경과 올바르게 상호 작용 하 고 런타임에 제대로 실행 되는 구성 요소와 컨트롤을 개발 하려면 클래스 및 멤버에 특성을 올바르게 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e550e-104">예</span><span class="sxs-lookup"><span data-stu-id="e550e-104">Example</span></span>  
 <span data-ttu-id="e550e-105">다음 코드 예제에서는 사용자 지정 컨트롤에 여러 특성을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="e550e-106">컨트롤은 간단한 로깅 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="e550e-107">컨트롤은 데이터 소스에 바인딩될 때 데이터 소스에서 보낸 값을 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e550e-108">값이 `Threshold` 속성에 지정 된 값을 초과 하면 `ThresholdExceeded` 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="e550e-109">`AttributesDemoControl`은 `LogEntry` 클래스를 사용 하 여 값을 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="e550e-110">`LogEntry` 클래스는 템플릿 클래스입니다. 즉, 기록 하는 형식에 대해 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="e550e-111">예를 들어 `AttributesDemoControl` `float`형식의 값을 기록 하는 경우 각 `LogEntry` 인스턴스가 다음과 같이 선언 되 고 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="e550e-112">`LogEntry`는 임의의 형식에 의해 매개 변수화 되기 때문에 리플렉션을 사용 하 여 매개 변수 형식에 대해 작업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="e550e-113">임계값 기능이 작동 하려면 매개 변수 형식 `T` <xref:System.IComparable> 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="e550e-114">`AttributesDemoControl`를 호스팅하는 폼은 성능 카운터를 주기적으로 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="e550e-115">각 값은 적절 한 형식의 `LogEntry` 패키지 되 고 폼의 <xref:System.Windows.Forms.BindingSource>에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="e550e-116">`AttributesDemoControl`는 데이터 바인딩을 통해 값을 받고 <xref:System.Windows.Forms.DataGridView> 컨트롤에 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="e550e-117">첫 번째 코드 예제는 `AttributesDemoControl` 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="e550e-118">두 번째 코드 예제에서는 `AttributesDemoControl`를 사용 하는 폼을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="e550e-119">클래스 수준 특성</span><span class="sxs-lookup"><span data-stu-id="e550e-119">Class-level Attributes</span></span>  
 <span data-ttu-id="e550e-120">일부 특성은 클래스 수준에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="e550e-121">다음 코드 예제에서는 Windows Forms 컨트롤에 일반적으로 적용 되는 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="e550e-122">TypeConverter 특성</span><span class="sxs-lookup"><span data-stu-id="e550e-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="e550e-123"><xref:System.ComponentModel.TypeConverterAttribute>은 일반적으로 사용 되는 다른 클래스 수준 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="e550e-124">다음 코드 예제에서는 `LogEntry` 클래스에 대 한 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="e550e-125">또한이 예제에서는 `LogEntryTypeConverter`이라고 하는 `LogEntry` 형식에 대 한 <xref:System.ComponentModel.TypeConverter> 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="e550e-126">멤버 수준 특성</span><span class="sxs-lookup"><span data-stu-id="e550e-126">Member-level Attributes</span></span>  
 <span data-ttu-id="e550e-127">일부 특성은 멤버 수준에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="e550e-128">다음 코드 예제에서는 Windows Forms 컨트롤의 속성에 일반적으로 적용 되는 몇 가지 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="e550e-129">AmbientValue 특성</span><span class="sxs-lookup"><span data-stu-id="e550e-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="e550e-130">다음 예제에서는 <xref:System.ComponentModel.AmbientValueAttribute>을 보여 주고 디자인 환경과의 상호 작용을 지 원하는 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="e550e-131">이 상호 작용을 *외계*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="e550e-132">데이터 바인딩 특성</span><span class="sxs-lookup"><span data-stu-id="e550e-132">Databinding Attributes</span></span>  
 <span data-ttu-id="e550e-133">다음 예에서는 복합 데이터 바인딩의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="e550e-134">이전에 표시 된 클래스 수준 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>는 데이터 바인딩에 사용할 `DataSource` 및 `DataMember` 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="e550e-135">`DataSource` 속성이 바인딩될 형식을 지정 하 <xref:System.ComponentModel.AttributeProviderAttribute>입니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e550e-136">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e550e-136">Compiling the Code</span></span>  
  
- <span data-ttu-id="e550e-137">`AttributesDemoControl`를 호스팅하는 폼에는를 빌드하기 위해 `AttributesDemoControl` 어셈블리에 대 한 참조가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e550e-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e550e-138">참조</span><span class="sxs-lookup"><span data-stu-id="e550e-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="e550e-139">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="e550e-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="e550e-140">Windows Forms 컨트롤의 특성</span><span class="sxs-lookup"><span data-stu-id="e550e-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="e550e-141">[방법: DesignerSerializationVisibilityAttribute를 사용 하 여 표준 형식의 컬렉션 Serialize](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e550e-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
