---
title: Visual Studio (Visual Basic)에서 식 트리 디버깅
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 7fc97d898c5956b5a569036e6e0fe1174714576d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65879808"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="62761-102">Visual Studio (Visual Basic)에서 식 트리 디버깅</span><span class="sxs-lookup"><span data-stu-id="62761-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="62761-103">애플리케이션을 디버그할 때 식 트리의 구조 및 내용을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62761-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="62761-104">식 트리 구조를 간단히 살펴보려면를 사용할 수 있습니다 합니다 `DebugView` 속성을 설명 하는 특수 구문을 사용 하 여 식 트리를 나타내는 [아래](#debugview-syntax)합니다.</span><span class="sxs-lookup"><span data-stu-id="62761-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="62761-105">(유의 `DebugView` 디버그 모드 에서만 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="62761-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Visual Studio 디버거 내에서 식 트리의 DebugView](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

<span data-ttu-id="62761-107">하므로 `DebugView` 문자열인 경우 사용할 수는 [기본 제공 텍스트 시각화 도우미](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) 선택 하 여 여러 줄에 표시할 **텍스트 시각화 도우미** 옆에 있는 돋보기 아이콘에서는 `DebugView` 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="62761-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 !['DebugView'의 결과에 적용 되는 텍스트 시각화 도우미](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

<span data-ttu-id="62761-109">설치 및 사용할 수 또는 [사용자 지정 시각화 도우미](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) 식 트리에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="62761-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="62761-110">[읽을 수 있는 식을](https://github.com/agileobjects/ReadableExpressions) ([MIT 라이선스](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md)에서 사용할 수 있는 합니다 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), 식 트리를 렌더링 C# 코드:</span><span class="sxs-lookup"><span data-stu-id="62761-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![읽을 수 있는 식 시각화 도우미](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="62761-112">[식 트리 시각화 도우미](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT 라이선스](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), 식 트리, 속성 및 관련된 개체의 그래픽 뷰를 제공 하 고 Visual Basic 코드를 사용 하 여 식 트리를 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62761-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![ExpressionToString 시각화 도우미](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="62761-114">식 트리에 대한 시각화 도우미를 열려면</span><span class="sxs-lookup"><span data-stu-id="62761-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="62761-115">에서는 식 트리의 옆에 나타나는 돋보기 아이콘을 클릭 **DataTips**, **조사식** 창 합니다 **자동** 창 또는 **지역** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="62761-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="62761-116">사용 가능한 시각화 도우미의 목록이 표시 됩니다.:</span><span class="sxs-lookup"><span data-stu-id="62761-116">A list of available visualizers is displayed.:</span></span> 

      ![Visual Studio에서 열기 시각화 도우미](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. <span data-ttu-id="62761-118">사용할 시각화 도우미를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="62761-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="62761-119">`DebugView` 구문</span><span class="sxs-lookup"><span data-stu-id="62761-119">`DebugView` syntax</span></span> 

<span data-ttu-id="62761-120">각 식 형식은 다음 섹션에 설명된 대로 시각화 도우미에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="62761-120">Each expression type is displayed in the visualizer as described in the following sections.</span></span>

## <a name="parameterexpressions"></a><span data-ttu-id="62761-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="62761-121">ParameterExpressions</span></span>

<span data-ttu-id="62761-122"><xref:System.Linq.Expressions.ParameterExpression> 변수 이름의 시작 부분에 “$” 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="62761-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="62761-123">매개 변수에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `$var1` 또는 `$var2`).</span><span class="sxs-lookup"><span data-stu-id="62761-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="62761-124">예제</span><span class="sxs-lookup"><span data-stu-id="62761-124">Examples</span></span>

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    <span data-ttu-id="62761-125">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="62761-125">`DebugView` property</span></span>

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    <span data-ttu-id="62761-126">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="62761-126">`DebugView` property</span></span>

    `$var1`

## <a name="constantexpressions"></a><span data-ttu-id="62761-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="62761-127">ConstantExpressions</span></span>
 <span data-ttu-id="62761-128">정수 값, 문자열 및 `null`을 나타내는 <xref:System.Linq.Expressions.ConstantExpression> 개체의 경우 상수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="62761-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="62761-129">예제</span><span class="sxs-lookup"><span data-stu-id="62761-129">Examples</span></span>

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="62761-130">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="62761-130">`DebugView` property</span></span>

    <span data-ttu-id="62761-131">10</span><span class="sxs-lookup"><span data-stu-id="62761-131">10</span></span>

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="62761-132">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="62761-132">`DebugView` property</span></span>

    <span data-ttu-id="62761-133">10D</span><span class="sxs-lookup"><span data-stu-id="62761-133">10D</span></span>

## <a name="blockexpression"></a><span data-ttu-id="62761-134">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="62761-134">BlockExpression</span></span>

<span data-ttu-id="62761-135"><xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 블록에 있는 마지막 식의 형식과 다를 경우 형식은 꺾쇠 괄호(\< 및 >) 안의 `DebugInfo` 속성에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="62761-135">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="62761-136">같을 경우 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62761-136">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="62761-137">예제</span><span class="sxs-lookup"><span data-stu-id="62761-137">Examples</span></span>

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    <span data-ttu-id="62761-138">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="62761-138">`DebugView` property</span></span>

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    <span data-ttu-id="62761-139">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="62761-139">`DebugView` property</span></span>

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a><span data-ttu-id="62761-140">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="62761-140">LambdaExpression</span></span>

<span data-ttu-id="62761-141"><xref:System.Linq.Expressions.LambdaExpression> 개체는 대리자 형식과 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="62761-141"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="62761-142">람다 식에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Lambda1` 또는 `#Lambda2`).</span><span class="sxs-lookup"><span data-stu-id="62761-142">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="62761-143">예제</span><span class="sxs-lookup"><span data-stu-id="62761-143">Examples</span></span>

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    <span data-ttu-id="62761-144">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="62761-144">`DebugView` property</span></span>

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    <span data-ttu-id="62761-145">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="62761-145">`DebugView` property</span></span>

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a><span data-ttu-id="62761-146">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="62761-146">LabelExpression</span></span>

<span data-ttu-id="62761-147"><xref:System.Linq.Expressions.LabelExpression> 개체의 기본값을 지정하면 이 값은 <xref:System.Linq.Expressions.LabelTarget> 개체 앞에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="62761-147">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="62761-148">`.Label` 토큰은 레이블의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62761-148">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="62761-149">`.LabelTarget` 토큰은 이동할 대상의 목적지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62761-149">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="62761-150">레이블에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Label1` 또는 `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="62761-150">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="62761-151">예제</span><span class="sxs-lookup"><span data-stu-id="62761-151">Examples</span></span>

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    <span data-ttu-id="62761-152">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="62761-152">`DebugView` property</span></span>

    `.Block() {`

    `.Goto SampleLabel { 0 };`

    `.Label`

    `-1`

    `.LabelTarget SampleLabel:`

    `}`

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label()
    Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), Expression.Label(target))
    ```

    <span data-ttu-id="62761-153">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="62761-153">`DebugView` property</span></span>

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a><span data-ttu-id="62761-154">확인된 연산자</span><span class="sxs-lookup"><span data-stu-id="62761-154">Checked Operators</span></span>

<span data-ttu-id="62761-155">확인된 연산자는 연산자 앞에 "#" 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="62761-155">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="62761-156">예를 들어 확인된 더하기 연산자는 `#+`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="62761-156">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="62761-157">예제</span><span class="sxs-lookup"><span data-stu-id="62761-157">Examples</span></span>

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    <span data-ttu-id="62761-158">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="62761-158">`DebugView` property</span></span>

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    <span data-ttu-id="62761-159">`DebugView` 속성</span><span class="sxs-lookup"><span data-stu-id="62761-159">`DebugView` property</span></span>

    `#(System.Int32)10D`

## <a name="see-also"></a><span data-ttu-id="62761-160">참고자료</span><span class="sxs-lookup"><span data-stu-id="62761-160">See also</span></span>

- [<span data-ttu-id="62761-161">식 트리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62761-161">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="62761-162">Visual Studio의 디버깅</span><span class="sxs-lookup"><span data-stu-id="62761-162">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- <span data-ttu-id="62761-163">[Create Custom Visualizers of Data](/visualstudio/debugger/create-custom-visualizers-of-data)(데이터의 사용자 지정 시각화 도우미 만들기)</span><span class="sxs-lookup"><span data-stu-id="62761-163">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
