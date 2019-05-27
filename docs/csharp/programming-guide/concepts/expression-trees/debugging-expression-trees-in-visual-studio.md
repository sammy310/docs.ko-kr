---
title: Visual Studio에서 식 트리 디버그(C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 4017e2c2592dc1d6067b428fc1d47f37775abf85
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877125"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="0c630-102">Visual Studio에서 식 트리 디버그(C#)</span><span class="sxs-lookup"><span data-stu-id="0c630-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="0c630-103">애플리케이션을 디버그할 때 식 트리의 구조 및 내용을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="0c630-104">식 트리 구조에 대한 간략한 개요를 보려면 [아래](#debugview-syntax)에 설명된 특수 구문을 사용하여 식 트리를 나타내는 `DebugView` 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="0c630-105">(`DebugView`는 디버그 모드에서만 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="0c630-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Visual Studio 디버거 내의 식 트리 DebugView](media/debugging-expression-trees-in-visual-studio/debugview.png)

<span data-ttu-id="0c630-107">`DebugView`는 문자열이므로 `DebugView` 레이블 옆의 돋보기 아이콘에서 **텍스트 시각화 도우미**를 선택하여 [기본 제공 텍스트 시각화 도우미](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer)를 사용하여 여러 줄에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 !['DebugView'의 결과에 적용되는 텍스트 시각화 도우미](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

<span data-ttu-id="0c630-109">또는 식 트리에 [사용자 지정 시각화 도우미](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)를 설치하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="0c630-110">[읽을 수 있는 식](https://github.com/agileobjects/ReadableExpressions)([MIT 라이선스](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)에서 사용 가능)은 식 트리를 C# 코드로 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![읽을 수 있는 식 시각화 도우미](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="0c630-112">[식 트리 시각화 도우미](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees)([MIT 라이선스](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE))는 식 트리, 해당 속성 및 관련 개체의 그래픽 뷰를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects:</span></span>

  ![ExpressionToString 시각화 도우미](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="0c630-114">식 트리에 대한 시각화 도우미를 열려면</span><span class="sxs-lookup"><span data-stu-id="0c630-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="0c630-115">**DataTips**, **조사식** 창, **자동** 창 또는 **지역** 창의 식 트리 옆에 나타나는 돋보기 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="0c630-116">사용 가능한 시각화 도우미의 목록이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-116">A list of available visualizers is displayed.:</span></span> 

      ![Visual Studio에서 시각화 도우미 열기](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. <span data-ttu-id="0c630-118">사용할 시각화 도우미를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="0c630-119">`DebugView` 구문</span><span class="sxs-lookup"><span data-stu-id="0c630-119">`DebugView` syntax</span></span> 

<span data-ttu-id="0c630-120">각 식 형식은 다음 섹션에 설명된 대로 `DebugView` 속성으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-120">Each expression type is displayed by the `DebugView` property as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="0c630-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="0c630-121">ParameterExpressions</span></span>  
 <span data-ttu-id="0c630-122"><xref:System.Linq.Expressions.ParameterExpression> 변수 이름의 시작 부분에 “$” 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="0c630-123">매개 변수에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `$var1` 또는 `$var2`).</span><span class="sxs-lookup"><span data-stu-id="0c630-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0c630-124">예제</span><span class="sxs-lookup"><span data-stu-id="0c630-124">Examples</span></span>  
  
|<span data-ttu-id="0c630-125">식</span><span class="sxs-lookup"><span data-stu-id="0c630-125">Expression</span></span>|<span data-ttu-id="0c630-126">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="0c630-126">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="0c630-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="0c630-127">ConstantExpressions</span></span>  
 <span data-ttu-id="0c630-128">정수 값, 문자열 및 `null`을 나타내는 <xref:System.Linq.Expressions.ConstantExpression> 개체의 경우 상수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="0c630-129">표준 접미사인 C# 리터럴이 있는 숫자 형식의 경우 접미사가 값에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-129">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="0c630-130">다음 표에서는 다양한 숫자 형식과 연결된 접미사를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-130">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="0c630-131">형식</span><span class="sxs-lookup"><span data-stu-id="0c630-131">Type</span></span>|<span data-ttu-id="0c630-132">접미사</span><span class="sxs-lookup"><span data-stu-id="0c630-132">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="0c630-133">U</span><span class="sxs-lookup"><span data-stu-id="0c630-133">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="0c630-134">L</span><span class="sxs-lookup"><span data-stu-id="0c630-134">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="0c630-135">UL</span><span class="sxs-lookup"><span data-stu-id="0c630-135">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="0c630-136">D</span><span class="sxs-lookup"><span data-stu-id="0c630-136">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="0c630-137">F</span><span class="sxs-lookup"><span data-stu-id="0c630-137">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="0c630-138">M</span><span class="sxs-lookup"><span data-stu-id="0c630-138">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="0c630-139">예제</span><span class="sxs-lookup"><span data-stu-id="0c630-139">Examples</span></span>  
  
|<span data-ttu-id="0c630-140">식</span><span class="sxs-lookup"><span data-stu-id="0c630-140">Expression</span></span>|<span data-ttu-id="0c630-141">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="0c630-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="0c630-142">10</span><span class="sxs-lookup"><span data-stu-id="0c630-142">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="0c630-143">10D</span><span class="sxs-lookup"><span data-stu-id="0c630-143">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="0c630-144">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="0c630-144">BlockExpression</span></span>  
 <span data-ttu-id="0c630-145"><xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 블록에 있는 마지막 식의 형식과 다를 경우 형식은 꺾쇠 괄호(\< 및 >) 안의 `DebugInfo` 속성에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-145">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="0c630-146">같을 경우 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-146">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0c630-147">예제</span><span class="sxs-lookup"><span data-stu-id="0c630-147">Examples</span></span>  
  
|<span data-ttu-id="0c630-148">식</span><span class="sxs-lookup"><span data-stu-id="0c630-148">Expression</span></span>|<span data-ttu-id="0c630-149">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="0c630-149">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="0c630-150">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="0c630-150">LambdaExpression</span></span>  
 <span data-ttu-id="0c630-151"><xref:System.Linq.Expressions.LambdaExpression> 개체는 대리자 형식과 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-151"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="0c630-152">람다 식에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Lambda1` 또는 `#Lambda2`).</span><span class="sxs-lookup"><span data-stu-id="0c630-152">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0c630-153">예제</span><span class="sxs-lookup"><span data-stu-id="0c630-153">Examples</span></span>  
  
|<span data-ttu-id="0c630-154">식</span><span class="sxs-lookup"><span data-stu-id="0c630-154">Expression</span></span>|<span data-ttu-id="0c630-155">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="0c630-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="0c630-156">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="0c630-156">LabelExpression</span></span>  
 <span data-ttu-id="0c630-157"><xref:System.Linq.Expressions.LabelExpression> 개체의 기본값을 지정하면 이 값은 <xref:System.Linq.Expressions.LabelTarget> 개체 앞에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-157">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="0c630-158">`.Label` 토큰은 레이블의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-158">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="0c630-159">`.LabelTarget` 토큰은 이동할 대상의 목적지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-159">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="0c630-160">레이블에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Label1` 또는 `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="0c630-160">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0c630-161">예제</span><span class="sxs-lookup"><span data-stu-id="0c630-161">Examples</span></span>  
  
|<span data-ttu-id="0c630-162">식</span><span class="sxs-lookup"><span data-stu-id="0c630-162">Expression</span></span>|<span data-ttu-id="0c630-163">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="0c630-163">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="0c630-164">확인된 연산자</span><span class="sxs-lookup"><span data-stu-id="0c630-164">Checked Operators</span></span>  
 <span data-ttu-id="0c630-165">확인된 연산자는 연산자 앞에 "#" 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-165">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="0c630-166">예를 들어 확인된 더하기 연산자는 `#+`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c630-166">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0c630-167">예제</span><span class="sxs-lookup"><span data-stu-id="0c630-167">Examples</span></span>  
  
|<span data-ttu-id="0c630-168">식</span><span class="sxs-lookup"><span data-stu-id="0c630-168">Expression</span></span>|<span data-ttu-id="0c630-169">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="0c630-169">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="0c630-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c630-170">See also</span></span>

- [<span data-ttu-id="0c630-171">식 트리(C#)</span><span class="sxs-lookup"><span data-stu-id="0c630-171">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="0c630-172">Visual Studio의 디버깅</span><span class="sxs-lookup"><span data-stu-id="0c630-172">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- <span data-ttu-id="0c630-173">[Create Custom Visualizers of Data](/visualstudio/debugger/create-custom-visualizers-of-data)(데이터의 사용자 지정 시각화 도우미 만들기)</span><span class="sxs-lookup"><span data-stu-id="0c630-173">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
