---
title: 런타임 상태를 기준으로 쿼리 (Visual Basic)
description: LINQ 메서드 호출 또는 이러한 메서드에 전달 된 식 트리를 변경 하 여 코드에서 런타임 상태에 따라 동적으로 쿼리 하는 데 사용할 수 있는 다양 한 기술에 대해 설명 합니다.
ms.date: 02/14/2021
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
ms.openlocfilehash: c9f57950b2c26c0cca798ab632da90bf9f6c519a
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "100584841"
---
# <a name="querying-based-on-runtime-state-visual-basic"></a>런타임 상태를 기준으로 쿼리 (Visual Basic)

<xref:System.Linq.IQueryable>데이터 원본에 대해 또는 [IQueryable (Of T)](<xref:System.Linq.IQueryable%601>) 을 정의 하는 코드를 고려 합니다.

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Initialize":::

이 코드를 실행할 때마다 동일한 정확한 쿼리가 실행 됩니다. 이는 런타임에 조건에 따라 코드에서 다른 쿼리를 실행 하려는 경우에는 자주 유용 하지 않습니다. 이 문서에서는 런타임 상태에 따라 다른 쿼리를 실행 하는 방법을 설명 합니다.

## <a name="iqueryable--iqueryableof-t-and-expression-trees"></a>IQueryable/IQueryable (Of T) 및 식 트리

기본적으로에는 <xref:System.Linq.IQueryable> 다음과 같은 두 가지 구성 요소가 있습니다.

* <xref:System.Linq.IQueryable.Expression>&mdash;식 트리 형식의 현재 쿼리 구성 요소에 대 한 언어 및 datasource를 구분 하지 않는 표현입니다.
* <xref:System.Linq.IQueryable.Provider>&mdash;현재 쿼리를 값 또는 값 집합으로 구체화 하는 방법을 알고 있는 LINQ 공급자의 인스턴스입니다.

동적 쿼리 컨텍스트에서 공급자는 일반적으로 동일 하 게 유지 됩니다. 쿼리의 식 트리가 쿼리와 다릅니다.

식 트리는 변경할 수 없습니다. 다른 식 트리가 필요 &mdash; 하므로 다른 쿼리를 수행 하려면 &mdash; 기존 식 트리를 새로운 식 트리로 변환 해야 <xref:System.Linq.IQueryable> 합니다.

다음 섹션에서는 런타임 상태에 대 한 응답으로 다르게 쿼리 하는 특정 기술에 대해 설명 합니다.

- 식 트리 내에서 런타임 상태를 사용 합니다.
- 추가 LINQ 메서드 호출
- LINQ 메서드에 전달 된 식 트리를 변경 합니다.
- 에서 팩터리 메서드를 사용 하 여 [식 (TDelegate의)](xref:System.Linq.Expressions.Expression%601) 식 트리를 생성 합니다. <xref:System.Linq.Expressions.Expression>
- 의 식 트리에 메서드 호출 노드를 추가 합니다. <xref:System.Linq.IQueryable>
- 문자열 생성 및 [동적 LINQ 라이브러리](https://dynamic-linq.net/) 사용

## <a name="use-runtime-state-from-within-the-expression-tree"></a>식 트리 내에서 런타임 상태를 사용 합니다.

LINQ 공급자가 지 원하는 것으로 가정 하 여 동적으로 쿼리 하는 가장 간단한 방법은 다음 코드 예제와 같이 닫혀 있는 변수를 통해 쿼리에서 직접 런타임 상태를 참조 하는 것입니다 `length` .

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Runtime_state_from_within_expression_tree":::

내부 식 트리 &mdash; 이므로 쿼리가 &mdash; 수정 되지 않았습니다 .의 값이 변경 되었기 때문에 쿼리는 다른 값만 반환 합니다 `length` .

## <a name="call-additional-linq-methods"></a>추가 LINQ 메서드 호출

일반적으로에서 [기본 제공 되는 LINQ 메서드](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Linq.Queryable/src/System/Linq/Queryable.cs) 는 <xref:System.Linq.Queryable> 다음 두 단계를 수행 합니다.

* 메서드 호출을 나타내는에서 현재 식 트리를 래핑합니다 <xref:System.Linq.Expressions.MethodCallExpression> .
* 래핑된 식 트리를 공급자에 게 다시 전달 하 여 공급자의 메서드를 통해 값을 반환 <xref:System.Linq.IQueryProvider.Execute%2A?displayProperty=nameWithType> 하거나, 메서드를 통해 번역 된 쿼리 개체를 반환 <xref:System.Linq.IQueryProvider.CreateQuery%2A?displayProperty=nameWithType> 합니다.

원래 쿼리를 [IQueryable (Of T)](xref:System.Linq.IQueryable%601)반환 메서드의 결과로 바꿔서 새 쿼리를 가져올 수 있습니다. 다음 예제와 같이 런타임 상태를 기준으로이 작업을 조건부로 수행할 수 있습니다.

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Added_method_calls":::

## <a name="vary-the-expression-tree-passed-into-the-linq-methods"></a>LINQ 메서드에 전달 된 식 트리를 변경 합니다.

런타임 상태에 따라 다양 한 식을 LINQ 메서드에 전달할 수 있습니다.

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Varying_expressions":::

[LinqKit](http://www.albahari.com/nutshell/linqkit.aspx)의 [PredicateBuilder](http://www.albahari.com/nutshell/predicatebuilder.aspx)와 같은 타사 라이브러리를 사용 하 여 다양 한 하위 식을 작성 해야 할 수도 있습니다.

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Compose_expression":::

## <a name="construct-expression-trees-and-queries-using-factory-methods"></a>팩터리 메서드를 사용 하 여 식 트리 및 쿼리 생성

이 시점까지 모든 예제에서 컴파일 시간에 요소 형식을 알 수 &mdash; `String` &mdash; 있으므로 쿼리 형식이 알려졌습니다 &mdash; `IQueryable(Of String)` . 요소 형식의 쿼리에 구성 요소를 추가 하거나 요소 형식에 따라 다른 구성 요소를 추가 해야 할 수도 있습니다. 에서 팩터리 메서드를 사용 하 여 식 트리를 처음부터 만들 수 <xref:System.Linq.Expressions.Expression?displayProperty=fullName> 있으므로 런타임에 식을 특정 요소 형식으로 조정할 수 있습니다.

### <a name="constructing-an-expressionof-tdelegate"></a>식 생성 [(TDelegate의 경우)](xref:System.Linq.Expressions.Expression%601)

LINQ 메서드 중 하나에 전달할 식을 생성할 때는 실제로 [식](xref:System.Linq.Expressions.Expression%601)의 인스턴스를 구성 하는 `TDelegate` 것입니다. 여기서는 `Func(Of String, Boolean)` , `Action` 또는 사용자 지정 대리자 형식과 같은 대리자 형식입니다.

[식 (TDelegate))](xref:System.Linq.Expressions.Expression%601) 는 <xref:System.Linq.Expressions.LambdaExpression> 다음과 같은 전체 람다 식을 나타내는에서 상속 됩니다.

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Compiler_generated":::

에는 <xref:System.Linq.Expressions.LambdaExpression> 다음 두 가지 구성 요소가 있습니다.

* &mdash; `(x As String)` &mdash; 속성이 나타내는 매개 변수 목록 <xref:System.Linq.Expressions.LambdaExpression.Parameters>
* &mdash; `x.StartsWith("a")` &mdash; 속성이 나타내는 본문 <xref:System.Linq.Expressions.LambdaExpression.Body> 입니다.

[식 (TDelegate의 경우)](xref:System.Linq.Expressions.Expression%601) 을 생성 하는 기본 단계는 다음과 같습니다.

* <xref:System.Linq.Expressions.ParameterExpression>팩터리 메서드를 사용 하 여 람다 식에서 각 매개 변수 (있는 경우)에 대 한 개체를 정의 <xref:System.Linq.Expressions.Expression.Parameter%2A> 합니다.

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_parameter":::

* 사용자가 <xref:System.Linq.Expressions.LambdaExpression> 정의한 및의 팩터리 메서드를 사용 하 여의 본문을 생성 <xref:System.Linq.Expressions.ParameterExpression> <xref:System.Linq.Expressions.Expression> 합니다. 예를 들어를 나타내는 식은 `x.StartsWith("a")` 다음과 같이 생성할 수 있습니다.

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_body":::

* 적절 한 팩터리 메서드 오버 로드를 사용 하 여 매개 변수 및 본문을 컴파일 시간 형식화 [식 (TDelegate)](xref:System.Linq.Expressions.Expression%601)로 래핑합니다 <xref:System.Linq.Expressions.Expression.Lambda%2A> .

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_lambda":::

다음 섹션에서는 LINQ 메서드에 전달할 [식 (TDelegate)](xref:System.Linq.Expressions.Expression%601) 을 생성 하 고 팩터리 메서드를 사용 하 여이 작업을 수행 하는 방법의 전체 예제를 제공 하는 시나리오에 대해 설명 합니다.

### <a name="scenario"></a>시나리오

여러 엔터티 형식이 있다고 가정해 보겠습니다.

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Entities.vb":::

이러한 엔터티 형식에 대해 필드 중 하나에 지정 된 텍스트가 있는 엔터티만 필터링 하 고 반환 하려고 합니다 `string` . 의 경우 `Person` 및 속성을 검색 합니다 `FirstName` `LastName` .

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="PersonsQry":::

하지만의 경우 속성만 `Car` 검색 하려고 합니다 `Model` .

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="CarsQry":::

에 대해 하나의 사용자 지정 함수를 작성 하 고에 대해 다른 사용자 지정 함수를 작성할 수 있지만 `IQueryable(Of Person)` `IQueryable(Of Car)` , 다음 함수는 특정 요소 형식에 관계 없이 기존 쿼리에이 필터링을 추가 합니다.

### <a name="example"></a>예제

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_expression_of_tdelegate":::

함수는 `TextFilter` 뿐 아니라 [IQueryable (Of T)](xref:System.Linq.IQueryable%601) 를 사용 하 고 반환 하기 때문에 <xref:System.Linq.IQueryable> 텍스트 필터 뒤에 컴파일 시간 형식화 된 쿼리 요소를 더 추가할 수 있습니다.

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_expression_of_tdelegate_usage":::

## <a name="add-method-call-nodes-to-the-xrefsystemlinqiqueryables-expression-tree"></a>식 트리에 메서드 호출 노드를 추가 합니다. <xref:System.Linq.IQueryable>

<xref:System.Linq.IQueryable> [IQueryable (of T)](xref:System.Linq.IQueryable%601)이 아닌가 있는 경우 제네릭 LINQ 메서드를 직접 호출할 수 없습니다. 한 가지 대안은 위와 같이 내부 식 트리를 작성 하 고 리플렉션을 사용 하 여 식 트리를 전달 하는 동안 적절 한 LINQ 메서드를 호출 하는 것입니다.

LINQ 메서드 호출을 나타내는에 전체 트리를 래핑하여 LINQ 메서드의 기능을 복제할 수도 있습니다 <xref:System.Linq.Expressions.MethodCallExpression> .

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_lambdaexpression":::

이 경우 컴파일 시간 `T` 제네릭 자리 표시 자가 없으므로 <xref:System.Linq.Expressions.Expression.Lambda%2A> 컴파일 시간 형식 정보를 요구 하지 않는 오버 로드를 사용 하 고 <xref:System.Linq.Expressions.LambdaExpression> [식 (tdelegate의 경우)](xref:System.Linq.Expressions.Expression%601)대신을 생성 합니다.

## <a name="the-dynamic-linq-library"></a>동적 LINQ 라이브러리

팩터리 메서드를 사용 하 여 식 트리를 생성 하는 것은 비교적 복잡 합니다. 문자열을 작성 하는 것이 더 쉽습니다. [동적 linq 라이브러리](https://dynamic-linq.net/) 는의 표준 LINQ 메서드에 해당 하는의 확장 메서드 집합을 노출 하 <xref:System.Linq.IQueryable> <xref:System.Linq.Queryable> 고, 식 트리 대신 [특수 구문](https://dynamic-linq.net/expression-language) 에서 문자열을 허용 합니다. 라이브러리는 문자열에서 적절 한 식 트리를 생성 하 고 번역 된 결과를 반환할 수 있습니다 <xref:System.Linq.IQueryable> .

예를 들어 앞의 예제 (식 트리 생성 포함)를 다음과 같이 다시 작성할 수 있습니다.

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Dynamic_linq":::

## <a name="see-also"></a>참고 항목

- [식 트리(Visual Basic)](index.md)
- [방법: 식 트리 실행(Visual Basic)](how-to-execute-expression-trees.md)
