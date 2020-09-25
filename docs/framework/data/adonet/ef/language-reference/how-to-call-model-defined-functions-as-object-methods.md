---
title: '방법: 개체 메서드로 모델 정의 함수 호출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33bae8a8-4ed8-4a1f-85d1-c62ff288cc61
ms.openlocfilehash: 5e5ae2fd838a34d7f665b23a14db2a599367e801
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197796"
---
# <a name="how-to-call-model-defined-functions-as-object-methods"></a><span data-ttu-id="5db21-102">방법: 개체 메서드로 모델 정의 함수 호출</span><span class="sxs-lookup"><span data-stu-id="5db21-102">How to: Call Model-Defined Functions as Object Methods</span></span>

<span data-ttu-id="5db21-103">이 항목에서는 모델 정의 함수를 <xref:System.Data.Objects.ObjectContext> 개체의 메서드 또는 사용자 지정 클래스의 정적 메서드로 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-103">This topic describes how to call a model-defined function as a method on an <xref:System.Data.Objects.ObjectContext> object or as a static method on a custom class.</span></span> <span data-ttu-id="5db21-104">*모델 정의 함수* 는 개념적 모델에 정의 된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-104">A *model-defined function* is a function that is defined in the conceptual model.</span></span> <span data-ttu-id="5db21-105">이 항목의 절차에서는 이러한 함수를 LINQ to Entities 쿼리에서 호출하는 대신 직접 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-105">The procedures in the topic describe how to call these functions directly instead of calling them from LINQ to Entities queries.</span></span> <span data-ttu-id="5db21-106">LINQ to Entities 쿼리에서 모델 정의 함수를 호출 하는 방법에 대 한 자세한 내용은 [방법: 쿼리에서 모델 정의 함수 호출](how-to-call-model-defined-functions-in-queries.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5db21-106">For information about calling model-defined functions in LINQ to Entities queries, see [How to: Call Model-Defined Functions in Queries](how-to-call-model-defined-functions-in-queries.md).</span></span>  
  
 <span data-ttu-id="5db21-107">모델 정의 함수를 <xref:System.Data.Objects.ObjectContext> 메서드 또는 사용자 지정 클래스의 정적 메서드로 호출하려면 먼저 메서드를 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>가 있는 모델 정의 함수로 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-107">Whether you call a model-defined function as an <xref:System.Data.Objects.ObjectContext> method or as a static method on a custom class, you must first map the method to the model-defined function with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="5db21-108">그러나 <xref:System.Data.Objects.ObjectContext> 클래스의 메서드를 정의하는 경우에는 <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> 속성을 사용하여 LINQ 공급자를 노출해야 하고, 사용자 지정 클래스의 정적 메서드를 정의하는 경우에는 <xref:System.Linq.IQueryable.Provider%2A> 속성을 사용하여 LINQ 공급자를 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-108">However, when you define a method on the <xref:System.Data.Objects.ObjectContext> class, you must use the <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> property to expose the LINQ provider, whereas when you define a static method on a custom class, you must use the <xref:System.Linq.IQueryable.Provider%2A> property to expose the LINQ provider.</span></span> <span data-ttu-id="5db21-109">자세한 내용은 다음 절차 아래에 나오는 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5db21-109">For more information, see the examples that follow the procedures below.</span></span>  
  
 <span data-ttu-id="5db21-110">다음 절차에서는 모델 정의 함수를 <xref:System.Data.Objects.ObjectContext> 개체의 메서드 및 사용자 지정 클래스의 정적 메서드로 호출하는 방법에 대해 간단히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-110">The procedures below provide high-level outlines for calling a model-defined function as a method on an <xref:System.Data.Objects.ObjectContext> object and as a static method on a custom class.</span></span> <span data-ttu-id="5db21-111">절차 다음에 나오는 예제에서는 절차의 단계를 보다 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-111">The examples that follow provide more detail about the steps in the procedures.</span></span> <span data-ttu-id="5db21-112">이러한 절차에서는 사용자가 개념적 모델에서 함수를 정의했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-112">The procedures assume that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="5db21-113">자세한 내용은 [방법: 개념적 모델에서 사용자 지정 함수 정의](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5db21-113">For more information, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span></span>  
  
### <a name="to-call-a-model-defined-function-as-a-method-on-an-objectcontext-object"></a><span data-ttu-id="5db21-114">모델 정의 함수를 ObjectContext 개체의 메서드로 호출하려면</span><span class="sxs-lookup"><span data-stu-id="5db21-114">To call a model-defined function as a method on an ObjectContext object</span></span>  
  
1. <span data-ttu-id="5db21-115">Entity Framework 도구에 의해 자동으로 생성된 <xref:System.Data.Objects.ObjectContext> 클래스에서 파생되는 partial 클래스를 확장하기 위해 소스 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-115">Add a source file to extend the partial class derived from the <xref:System.Data.Objects.ObjectContext> class, auto-generated by the Entity Framework tools.</span></span> <span data-ttu-id="5db21-116">CLR 스텁을 별도의 소스 파일에서 정의하면 파일을 다시 생성할 때 변경 내용이 손실되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-116">Defining the CLR stub in a separate source file will prevent the changes from being lost when the file is regenerated.</span></span>  
  
2. <span data-ttu-id="5db21-117">다음 작업을 수행하는 <xref:System.Data.Objects.ObjectContext> 클래스에 CLR(공용 언어 런타임) 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-117">Add a common language runtime (CLR) method to your <xref:System.Data.Objects.ObjectContext> class that does the following:</span></span>  
  
    - <span data-ttu-id="5db21-118">개념적 모델에 정의된 함수로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-118">Maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="5db21-119">메서드를 매핑하려면 메서드에 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-119">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="5db21-120">특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> 매개 변수는 개념적 모델의 네임스페이스 이름이고, 특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> 매개 변수는 개념적 모델의 함수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-120">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model, respectively.</span></span> <span data-ttu-id="5db21-121">LINQ에서 함수 이름을 확인할 때는 대/소문자가 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-121">Function name resolution for LINQ is case sensitive.</span></span>  
  
    - <span data-ttu-id="5db21-122"><xref:System.Linq.IQueryProvider.Execute%2A> 속성에 의해 반환된 <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> 메서드의 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-122">Returns the results of the <xref:System.Linq.IQueryProvider.Execute%2A> method that is returned by the <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> property.</span></span>  
  
3. <span data-ttu-id="5db21-123">메서드를 <xref:System.Data.Objects.ObjectContext> 클래스 인스턴스의 멤버로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-123">Call the method as a member on an instance of the <xref:System.Data.Objects.ObjectContext> class.</span></span>  
  
### <a name="to-call-a-model-defined-function-as-static-method-on-a-custom-class"></a><span data-ttu-id="5db21-124">모델 정의 함수를 사용자 지정 클래스의 정적 메서드로 호출하려면</span><span class="sxs-lookup"><span data-stu-id="5db21-124">To call a model-defined function as static method on a custom class</span></span>  
  
1. <span data-ttu-id="5db21-125">다음 작업을 수행하는 정적 메서드가 포함된 애플리케이션에 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-125">Add a class to your application with a static method that does the following:</span></span>  
  
    - <span data-ttu-id="5db21-126">개념적 모델에 정의된 함수로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-126">Maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="5db21-127">메서드를 매핑하려면 메서드에 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-127">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="5db21-128">특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> 매개 변수는 개념적 모델의 네임스페이스 이름이고, 특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> 매개 변수는 개념적 모델의 함수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-128">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model, respectively.</span></span>  
  
    - <span data-ttu-id="5db21-129"><xref:System.Linq.IQueryable> 인수를 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-129">Accepts an <xref:System.Linq.IQueryable> argument.</span></span>  
  
    - <span data-ttu-id="5db21-130"><xref:System.Linq.IQueryProvider.Execute%2A> 속성에 의해 반환된 <xref:System.Linq.IQueryable.Provider%2A> 메서드의 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-130">Returns the results of the <xref:System.Linq.IQueryProvider.Execute%2A> method that is returned by the <xref:System.Linq.IQueryable.Provider%2A> property.</span></span>  
  
2. <span data-ttu-id="5db21-131">메서드를 사용자 지정 클래스의 정적 메서드 멤버로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-131">Call the method as a member a static method on the custom class</span></span>  
  
## <a name="example"></a><span data-ttu-id="5db21-132">예제</span><span class="sxs-lookup"><span data-stu-id="5db21-132">Example</span></span>  

 <span data-ttu-id="5db21-133">**모델 정의 함수를 ObjectContext 개체의 메서드로 호출**</span><span class="sxs-lookup"><span data-stu-id="5db21-133">**Calling a Model-Defined Function as a Method on an ObjectContext Object**</span></span>  
  
 <span data-ttu-id="5db21-134">다음 예제에서는 모델 정의 함수를 <xref:System.Data.Objects.ObjectContext> 개체의 메서드로 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-134">The following example demonstrates how to call a model-defined function as a method on an <xref:System.Data.Objects.ObjectContext> object.</span></span> <span data-ttu-id="5db21-135">이 예에서는 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-135">The example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
 <span data-ttu-id="5db21-136">지정된 제품의 제품 수익을 반환하는 다음 개념적 모델 함수를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="5db21-136">Consider the conceptual model function below that returns product revenue for a specified product.</span></span> <span data-ttu-id="5db21-137">(개념적 모델에 함수를 추가 하는 방법에 대 한 자세한 내용은 [방법: 개념적 모델의 사용자 지정 함수 정의](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="5db21-137">(For information about adding the function to your conceptual model, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)</span></span>  
  
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#4)]  

## <a name="example"></a><span data-ttu-id="5db21-138">예제</span><span class="sxs-lookup"><span data-stu-id="5db21-138">Example</span></span>  

 <span data-ttu-id="5db21-139">다음 코드에서는 위의 개념적 모델 함수로 매핑되는 `AdventureWorksEntities` 클래스에 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-139">The following code adds a method to the `AdventureWorksEntities` class that maps to the conceptual model function above.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#2)]
 [!code-vb[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="5db21-140">예제</span><span class="sxs-lookup"><span data-stu-id="5db21-140">Example</span></span>  

 <span data-ttu-id="5db21-141">다음 코드에서는 위의 메서드를 호출하여 지정된 제품의 제품 수익을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-141">The following code calls the method above to display the product revenue for a specified product:</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#3)]
 [!code-vb[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="5db21-142">예제</span><span class="sxs-lookup"><span data-stu-id="5db21-142">Example</span></span>  

 <span data-ttu-id="5db21-143">다음 예제에서는 컬렉션을 반환하는 모델 정의 함수를 <xref:System.Linq.IQueryable%601> 개체로 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-143">The following example demonstrates how to call a model-defined function that returns a collection (as an <xref:System.Linq.IQueryable%601> object).</span></span> <span data-ttu-id="5db21-144">제공된 제품 ID의 모든 `SalesOrderDetails`를 반환하는 다음 개념적 모델 함수를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="5db21-144">Consider the conceptual model function below that returns all the `SalesOrderDetails` for a given product ID.</span></span>  
  
 [!code-xml[DP L2E Methods on ObjectContext#7](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#7)]  
  
## <a name="example"></a><span data-ttu-id="5db21-145">예제</span><span class="sxs-lookup"><span data-stu-id="5db21-145">Example</span></span>  

 <span data-ttu-id="5db21-146">다음 코드에서는 위의 개념적 모델 함수로 매핑되는 `AdventureWorksEntities` 클래스에 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-146">The following code adds a method to the `AdventureWorksEntities` class that maps to the conceptual model function above.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#8)]
 [!code-vb[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="5db21-147">예제</span><span class="sxs-lookup"><span data-stu-id="5db21-147">Example</span></span>  

 <span data-ttu-id="5db21-148">다음 코드에서는 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-148">The following code calls the method.</span></span> <span data-ttu-id="5db21-149">반환된 <xref:System.Linq.IQueryable%601> 쿼리는 각 `SalesOrderDetail`의 품목 합계를 반환하도록 보다 구체화됩니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-149">Note that the returned <xref:System.Linq.IQueryable%601> query is further refined to return line totals for each `SalesOrderDetail`.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#9)]
 [!code-vb[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="5db21-150">예제</span><span class="sxs-lookup"><span data-stu-id="5db21-150">Example</span></span>  

 <span data-ttu-id="5db21-151">**모델 정의 함수를 사용자 지정 클래스의 정적 메서드로 호출**</span><span class="sxs-lookup"><span data-stu-id="5db21-151">**Calling a Model-Defined Function as a Static Method on a Custom Class**</span></span>  
  
 <span data-ttu-id="5db21-152">다음 예제에서는 모델 정의 함수를 사용자 지정 클래스의 정적 메서드로 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-152">The next example demonstrates how to call a model-defined function as a static method on a custom class.</span></span> <span data-ttu-id="5db21-153">이 예에서는 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-153">The example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5db21-154">모델 정의 함수를 사용자 지정 클래스의 정적 메서드로 호출할 때 모델 정의 함수는 컬렉션을 받아들이고 컬렉션의 값 집계를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-154">When you call a model-defined function as a static method on a custom class, the model-defined function must accept a collection and return an aggregation of values in the collection.</span></span>  
  
 <span data-ttu-id="5db21-155">SalesOrderDetail 컬렉션의 제품 수익을 반환하는 다음 개념적 모델 함수를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="5db21-155">Consider the conceptual model function below that returns product revenue for a SalesOrderDetail collection.</span></span> <span data-ttu-id="5db21-156">(개념적 모델에 함수를 추가 하는 방법에 대 한 자세한 내용은 [방법: 개념적 모델의 사용자 지정 함수 정의](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="5db21-156">(For information about adding the function to your conceptual model, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).).</span></span>  
  
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="5db21-157">예제</span><span class="sxs-lookup"><span data-stu-id="5db21-157">Example</span></span>  

 <span data-ttu-id="5db21-158">다음 코드에서는 위의 개념적 모델 함수로 매핑되는 정적 메서드가 포함된 애플리케이션에 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-158">The following code adds a class to your application that contains a static method that maps to the conceptual model function above.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#5)]
 [!code-vb[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="5db21-159">예제</span><span class="sxs-lookup"><span data-stu-id="5db21-159">Example</span></span>  

 <span data-ttu-id="5db21-160">다음 코드에서는 위의 메서드를 호출하여 SalesOrderDetail 컬렉션의 제품 수익을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5db21-160">The following code calls the method above to display the product revenue for a SalesOrderDetail collection:</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#6)]
 [!code-vb[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="5db21-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5db21-161">See also</span></span>

- <span data-ttu-id="5db21-162">[.edmx 파일 개요](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5db21-162">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="5db21-163">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="5db21-163">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="5db21-164">LINQ to Entities 쿼리에서 함수 호출</span><span class="sxs-lookup"><span data-stu-id="5db21-164">Calling Functions in LINQ to Entities Queries</span></span>](calling-functions-in-linq-to-entities-queries.md)
