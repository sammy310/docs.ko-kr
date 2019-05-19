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
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Visual Studio (Visual Basic)에서 식 트리 디버깅
애플리케이션을 디버그할 때 식 트리의 구조 및 내용을 분석할 수 있습니다. 식 트리 구조를 간단히 살펴보려면를 사용할 수 있습니다 합니다 `DebugView` 속성을 설명 하는 특수 구문을 사용 하 여 식 트리를 나타내는 [아래](#debugview-syntax)합니다. (유의 `DebugView` 디버그 모드 에서만 사용할 수 있습니다.)  

![Visual Studio 디버거 내에서 식 트리의 DebugView](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

하므로 `DebugView` 문자열인 경우 사용할 수는 [기본 제공 텍스트 시각화 도우미](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) 선택 하 여 여러 줄에 표시할 **텍스트 시각화 도우미** 옆에 있는 돋보기 아이콘에서는 `DebugView` 레이블입니다.

 !['DebugView'의 결과에 적용 되는 텍스트 시각화 도우미](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

설치 및 사용할 수 또는 [사용자 지정 시각화 도우미](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) 식 트리에 대 한 합니다.

* [읽을 수 있는 식을](https://github.com/agileobjects/ReadableExpressions) ([MIT 라이선스](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md)에서 사용할 수 있는 합니다 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), 식 트리를 렌더링 C# 코드:

  ![읽을 수 있는 식 시각화 도우미](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* [식 트리 시각화 도우미](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT 라이선스](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), 식 트리, 속성 및 관련된 개체의 그래픽 뷰를 제공 하 고 Visual Basic 코드를 사용 하 여 식 트리를 렌더링할 수 있습니다.

  ![ExpressionToString 시각화 도우미](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>식 트리에 대한 시각화 도우미를 열려면  
  
1. 에서는 식 트리의 옆에 나타나는 돋보기 아이콘을 클릭 **DataTips**, **조사식** 창 합니다 **자동** 창 또는 **지역** 창입니다.  
  
     사용 가능한 시각화 도우미의 목록이 표시 됩니다.: 

      ![Visual Studio에서 열기 시각화 도우미](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. 사용할 시각화 도우미를 클릭합니다.  

## <a name="debugview-syntax"></a>`DebugView` 구문 

각 식 형식은 다음 섹션에 설명된 대로 시각화 도우미에 표시됩니다.

## <a name="parameterexpressions"></a>ParameterExpressions

<xref:System.Linq.Expressions.ParameterExpression> 변수 이름의 시작 부분에 “$” 기호가 표시됩니다.

매개 변수에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `$var1` 또는 `$var2`).

### <a name="examples"></a>예제

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    `DebugView` 속성

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    `DebugView` 속성

    `$var1`

## <a name="constantexpressions"></a>ConstantExpressions
 정수 값, 문자열 및 `null`을 나타내는 <xref:System.Linq.Expressions.ConstantExpression> 개체의 경우 상수 값이 표시됩니다.

### <a name="examples"></a>예제

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    `DebugView` 속성

    10

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    `DebugView` 속성

    10D

## <a name="blockexpression"></a>BlockExpression

<xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 블록에 있는 마지막 식의 형식과 다를 경우 형식은 꺾쇠 괄호(\< 및 >) 안의 `DebugInfo` 속성에 표시됩니다. 같을 경우 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 표시되지 않습니다.

### <a name="examples"></a>예제

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    `DebugView` 속성

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    `DebugView` 속성

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a>LambdaExpression

<xref:System.Linq.Expressions.LambdaExpression> 개체는 대리자 형식과 함께 표시됩니다.

람다 식에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Lambda1` 또는 `#Lambda2`).

### <a name="examples"></a>예제

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    `DebugView` 속성

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    `DebugView` 속성

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a>LabelExpression

<xref:System.Linq.Expressions.LabelExpression> 개체의 기본값을 지정하면 이 값은 <xref:System.Linq.Expressions.LabelTarget> 개체 앞에 표시됩니다.

`.Label` 토큰은 레이블의 시작을 나타냅니다. `.LabelTarget` 토큰은 이동할 대상의 목적지를 나타냅니다.

레이블에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Label1` 또는 `#Label2`).

### <a name="examples"></a>예제

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    `DebugView` 속성

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

    `DebugView` 속성

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a>확인된 연산자

확인된 연산자는 연산자 앞에 "#" 기호가 표시됩니다. 예를 들어 확인된 더하기 연산자는 `#+`로 표시됩니다.

### <a name="examples"></a>예제

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    `DebugView` 속성

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    `DebugView` 속성

    `#(System.Int32)10D`

## <a name="see-also"></a>참고자료

- [식 트리(Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [Visual Studio의 디버깅](/visualstudio/debugger/debugging-in-visual-studio)
- [Create Custom Visualizers of Data](/visualstudio/debugger/create-custom-visualizers-of-data)(데이터의 사용자 지정 시각화 도우미 만들기)
