---
title: 식 트리 수정 방법(C#)
description: 기존 식 트리의 복사본을 만들고 필요한 내용을 변경하여 식 트리를 수정하는 방법에 대해 알아봅니다.
ms.date: 07/20/2015
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
ms.openlocfilehash: 01176f489794a0f4ca29d229d29507fdba0fd5a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167693"
---
# <a name="how-to-modify-expression-trees-c"></a><span data-ttu-id="c1fa4-103">식 트리 수정 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="c1fa4-103">How to modify expression trees (C#)</span></span>

<span data-ttu-id="c1fa4-104">이 항목에서는 식 트리를 수정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-104">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="c1fa4-105">식 트리는 변경할 수 없으며, 직접 수정할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-105">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="c1fa4-106">식 트리를 변경하려면 기존 식 트리의 복사본을 만들고, 해당 복사본을 만들 때 필요한 사항을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-106">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="c1fa4-107"><xref:System.Linq.Expressions.ExpressionVisitor> 클래스를 사용하여 기존 식 트리를 트래버스하고 방문하는 각 노드를 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-107">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="c1fa4-108">식 트리를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="c1fa4-108">To modify an expression tree</span></span>  
  
1. <span data-ttu-id="c1fa4-109">**콘솔 애플리케이션** 프로젝트를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-109">Create a new **Console Application** project.</span></span>  
  
2. <span data-ttu-id="c1fa4-110">`System.Linq.Expressions` 네임스페이스에 대한 `using` 지시문을 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-110">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3. <span data-ttu-id="c1fa4-111">프로젝트에 `AndAlsoModifier` 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-111">Add the `AndAlsoModifier` class to your project.</span></span>  
  
    ```csharp  
    public class AndAlsoModifier : ExpressionVisitor  
    {  
        public Expression Modify(Expression expression)  
        {  
            return Visit(expression);  
        }  
  
        protected override Expression VisitBinary(BinaryExpression b)  
        {  
            if (b.NodeType == ExpressionType.AndAlso)  
            {  
                Expression left = this.Visit(b.Left);  
                Expression right = this.Visit(b.Right);  
  
                // Make this binary expression an OrElse operation instead of an AndAlso operation.  
                return Expression.MakeBinary(ExpressionType.OrElse, left, right, b.IsLiftedToNull, b.Method);  
            }  
  
            return base.VisitBinary(b);  
        }  
    }  
    ```  
  
     <span data-ttu-id="c1fa4-112">이 클래스는 <xref:System.Linq.Expressions.ExpressionVisitor> 클래스를 상속하며, 조건부 `AND` 작업을 나타내는 식을 수정하도록 특수화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-112">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="c1fa4-113">해당 작업을 조건부 `AND`에서 조건부 `OR`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-113">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="c1fa4-114">조건부 `AND` 식은 이진 식으로 표현되기 때문에 이 작업을 위해 클래스는 기본 형식의 <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-114">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="c1fa4-115">`VisitBinary` 메서드에서 전달된 식이 조건부 `AND` 작업을 나타내는 경우 코드는 조건부 `AND` 연산자 대신 조건부 `OR` 연산자가 포함된 새 식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-115">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="c1fa4-116">`VisitBinary`에 전달된 식이 조건부 `AND` 작업을 나타내지 않는 경우 메서드는 기본 클래스 구현을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-116">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="c1fa4-117">기본 클래스 메서드는 전달된 식 트리와 유사한 노드를 생성하지만 노드의 하위 트리가 방문자에 의해 재귀적으로 생성된 식 트리로 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-117">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4. <span data-ttu-id="c1fa4-118">`System.Linq.Expressions` 네임스페이스에 대한 `using` 지시문을 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-118">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5. <span data-ttu-id="c1fa4-119">Program.cs 파일의 `Main` 메서드에 코드를 추가하여 식 트리를 만들고 이 식 트리를 수정할 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-119">Add code to the `Main` method in the Program.cs file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
    ```csharp  
    Expression<Func<string, bool>> expr = name => name.Length > 10 && name.StartsWith("G");  
    Console.WriteLine(expr);  
  
    AndAlsoModifier treeModifier = new AndAlsoModifier();  
    Expression modifiedExpr = treeModifier.Modify((Expression) expr);  
  
    Console.WriteLine(modifiedExpr);  
  
    /*  This code produces the following output:  
  
        name => ((name.Length > 10) && name.StartsWith("G"))  
        name => ((name.Length > 10) || name.StartsWith("G"))  
    */  
    ```  
  
     <span data-ttu-id="c1fa4-120">코드에서 조건부 `AND` 작업이 포함된 식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-120">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="c1fa4-121">그런 다음 `AndAlsoModifier` 클래스 인스턴스를 만들고 이 클래스의 `Modify` 메서드에 식을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-121">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="c1fa4-122">원본 및 수정된 식 트리가 둘 다 출력되어 변경 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-122">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6. <span data-ttu-id="c1fa4-123">애플리케이션을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1fa4-123">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1fa4-124">참조</span><span class="sxs-lookup"><span data-stu-id="c1fa4-124">See also</span></span>

- [<span data-ttu-id="c1fa4-125">식 트리 실행 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="c1fa4-125">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="c1fa4-126">식 트리(C#)</span><span class="sxs-lookup"><span data-stu-id="c1fa4-126">Expression Trees (C#)</span></span>](./index.md)
