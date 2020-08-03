---
title: LINQ를 통한 데이터 변환(C#)
description: C#에서 LINQ 쿼리를 사용하여 데이터를 변환하는 방법에 대해 알아봅니다. 정렬하고 그룹화하여 시퀀스를 수정하고 select 절을 사용하여 새 형식을 만들 수 있습니다.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: 6844cf2aa589f7516a9e40bc604c5f907ec6d311
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104019"
---
# <a name="data-transformations-with-linq-c"></a><span data-ttu-id="e65b1-104">LINQ를 통한 데이터 변환(C#)</span><span class="sxs-lookup"><span data-stu-id="e65b1-104">Data Transformations with LINQ (C#)</span></span>
<span data-ttu-id="e65b1-105">LINQ(Language-Integrated Query)는 데이터 검색에만 관련된 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-105">Language-Integrated Query (LINQ) is not only about retrieving data.</span></span> <span data-ttu-id="e65b1-106">데이터 변환을 위한 강력한 도구이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-106">It is also a powerful tool for transforming data.</span></span> <span data-ttu-id="e65b1-107">LINQ 쿼리를 사용하여 소스 시퀀스를 입력으로 사용하고 다양한 방법으로 수정하여 새 출력 시퀀스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-107">By using a LINQ query, you can use a source sequence as input and modify it in many ways to create a new output sequence.</span></span> <span data-ttu-id="e65b1-108">정렬 및 그룹화를 통해 요소 자체를 수정하지 않고 시퀀스 자체를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-108">You can modify the sequence itself without modifying the elements themselves by sorting and grouping.</span></span> <span data-ttu-id="e65b1-109">하지만 LINQ 쿼리의 가장 강력한 기능은 새 형식을 만드는 기능일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-109">But perhaps the most powerful feature of LINQ queries is the ability to create new types.</span></span> <span data-ttu-id="e65b1-110">이 작업은 [select](../../../language-reference/keywords/select-clause.md) 절에서 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-110">This is accomplished in the [select](../../../language-reference/keywords/select-clause.md) clause.</span></span> <span data-ttu-id="e65b1-111">예를 들어, 아래와 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-111">For example, you can perform the following tasks:</span></span>  
  
- <span data-ttu-id="e65b1-112">여러 입력 시퀀스를 새 형식을 가진 단일 출력 시퀀스로 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-112">Merge multiple input sequences into a single output sequence that has a new type.</span></span>  
  
- <span data-ttu-id="e65b1-113">소스 시퀀스에 있는 각 요소의 속성 하나만으로 또는 여러 속성으로 구성된 출력 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-113">Create output sequences whose elements consist of only one or several properties of each element in the source sequence.</span></span>  
  
- <span data-ttu-id="e65b1-114">요소가 소스 데이터에서 수행된 작업의 결과로 구성된 출력 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-114">Create output sequences whose elements consist of the results of operations performed on the source data.</span></span>  
  
- <span data-ttu-id="e65b1-115">출력 시퀀스를 다른 형식으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-115">Create output sequences in a different format.</span></span> <span data-ttu-id="e65b1-116">예를 들어 데이터를 SQL 행 또는 텍스트 파일에서 XML로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-116">For example, you can transform data from SQL rows or text files into XML.</span></span>  
  
 <span data-ttu-id="e65b1-117">이것은 몇 가지 예일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-117">These are just several examples.</span></span> <span data-ttu-id="e65b1-118">물론 같은 쿼리에서 다양한 방법으로 이러한 변환을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-118">Of course, these transformations can be combined in various ways in the same query.</span></span> <span data-ttu-id="e65b1-119">또한 한 쿼리의 출력 시퀀스는 새 쿼리에 대한 입력 시퀀스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-119">Furthermore, the output sequence of one query can be used as the input sequence for a new query.</span></span>  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a><span data-ttu-id="e65b1-120">여러 입력을 단일 출력 시퀀스로 결합</span><span class="sxs-lookup"><span data-stu-id="e65b1-120">Joining Multiple Inputs into One Output Sequence</span></span>  
 <span data-ttu-id="e65b1-121">LINQ 쿼리를 사용하여 두 개 이상의 입력 시퀀스에서 생성된 요소가 포함된 출력 시퀀스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-121">You can use a LINQ query to create an output sequence that contains elements from more than one input sequence.</span></span> <span data-ttu-id="e65b1-122">다음 예제에서는 두 개의 메모리 내 데이터 구조를 결합하는 방법을 보여 주지만 XML, SQL 또는 DataSet 소스에서 데이터를 결합하는 데는 같은 원칙을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-122">The following example shows how to combine two in-memory data structures, but the same principles can be applied to combine data from XML or SQL or DataSet sources.</span></span> <span data-ttu-id="e65b1-123">다음 두 가지 클래스 형식을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-123">Assume the following two class types:</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 <span data-ttu-id="e65b1-124">다음 예제에서는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-124">The following example shows the query:</span></span>  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 <span data-ttu-id="e65b1-125">자세한 내용은 [join 절](../../../language-reference/keywords/join-clause.md) 및 [select 절](../../../language-reference/keywords/select-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e65b1-125">For more information, see [join clause](../../../language-reference/keywords/join-clause.md) and [select clause](../../../language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="selecting-a-subset-of-each-source-element"></a><span data-ttu-id="e65b1-126">각 소스 요소의 하위 집합 선택</span><span class="sxs-lookup"><span data-stu-id="e65b1-126">Selecting a Subset of each Source Element</span></span>  
 <span data-ttu-id="e65b1-127">소스 시퀀스에서 각 요소의 하위 집합을 선택하는 두 가지 기본 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-127">There are two primary ways to select a subset of each element in the source sequence:</span></span>  
  
1. <span data-ttu-id="e65b1-128">소스 요소의 멤버를 하나만 선택하려면 점 작업을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-128">To select just one member of the source element, use the dot operation.</span></span> <span data-ttu-id="e65b1-129">다음 예제에서는 `Customer` 개체에 `City` 문자열을 비롯한 여러 public 속성이 포함된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-129">In the following example, assume that a `Customer` object contains several public properties including a string named `City`.</span></span> <span data-ttu-id="e65b1-130">실행될 경우 이 쿼리는 문자열의 출력 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-130">When executed, this query will produce an output sequence of strings.</span></span>  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. <span data-ttu-id="e65b1-131">소스 요소의 속성의 두 개 이상 포함된 요소를 만들려면 개체 이니셜라이저를 명명된 개체 또는 무명 형식과 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-131">To create elements that contain more than one property from the source element, you can use an object initializer with either a named object or an anonymous type.</span></span> <span data-ttu-id="e65b1-132">다음 예제에서는 무명 형식을 사용하여 각 `Customer` 요소의 두 개 속성을 캡슐화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-132">The following example shows the use of an anonymous type to encapsulate two properties from each `Customer` element:</span></span>  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 <span data-ttu-id="e65b1-133">자세한 내용은 [개체 및 컬렉션 이니셜라이저](../../classes-and-structs/object-and-collection-initializers.md) 및 [무명 형식](../../classes-and-structs/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e65b1-133">For more information, see [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md) and [Anonymous Types](../../classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="transforming-in-memory-objects-into-xml"></a><span data-ttu-id="e65b1-134">메모리 내 개체를 XML로 변환</span><span class="sxs-lookup"><span data-stu-id="e65b1-134">Transforming in-Memory Objects into XML</span></span>  
 <span data-ttu-id="e65b1-135">LINQ 쿼리를 통해 메모리 내 데이터 구조, SQL 데이터베이스, ADO.NET 데이터 세트 및 XML 스트림이나 문서 간에 손쉽게 데이터를 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-135">LINQ queries make it easy to transform data between in-memory data structures, SQL databases, ADO.NET Datasets and XML streams or documents.</span></span> <span data-ttu-id="e65b1-136">다음 예제에서는 메모리 내 데이터 구조의 개체를 XML 요소로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-136">The following example transforms objects in an in-memory data structure into XML elements.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 <span data-ttu-id="e65b1-137">이 코드에서는 다음 XML 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-137">The code produces the following XML output:</span></span>  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 <span data-ttu-id="e65b1-138">자세한 내용은 [C#에서 XML 트리 만들기(LINQ to XML)](./creating-xml-trees-linq-to-xml-2.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e65b1-138">For more information, see [Creating XML Trees in C# (LINQ to XML)](./creating-xml-trees-linq-to-xml-2.md).</span></span>  
  
## <a name="performing-operations-on-source-elements"></a><span data-ttu-id="e65b1-139">소스 요소에서 작업 수행</span><span class="sxs-lookup"><span data-stu-id="e65b1-139">Performing Operations on Source Elements</span></span>  
 <span data-ttu-id="e65b1-140">출력 시퀀스에 소스 시퀀스의 요소 또는 요소 속성이 포함되어 있지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-140">An output sequence might not contain any elements or element properties from the source sequence.</span></span> <span data-ttu-id="e65b1-141">대신에 출력이 소스 요소를 입력 인수로 사용하여 계산되는 값 시퀀스일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-141">The output might instead be a sequence of values that is computed by using the source elements as input arguments.</span></span>

 <span data-ttu-id="e65b1-142">다음 쿼리는 원의 반지름을 나타내는 숫자의 시퀀스를 사용하여 각 반지름의 면적을 계산하고, 계산된 면적으로 형식이 지정된 문자열이 포함된 출력 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-142">The following query will take a sequence of numbers that represent radii of circles, calculate the area for each radius, and return an output sequence containing strings formatted with the calculated area.</span></span>

 <span data-ttu-id="e65b1-143">출력 시퀀스의 각 문자열은 [문자열 보간](../../../language-reference/tokens/interpolated.md)를 사용하여 형식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-143">Each string for the output sequence will be formatted using [string interpolation](../../../language-reference/tokens/interpolated.md).</span></span> <span data-ttu-id="e65b1-144">보간된 문자열에는 문자열의 여는 따옴표 앞에 `$` 기호가 포함되며, 보간된 문자열 내에 배치된 중괄호 내에서 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-144">An interpolated string will have a `$` in front of the string's opening quotation mark, and operations can be performed within curly braces placed inside the interpolated string.</span></span> <span data-ttu-id="e65b1-145">이러한 작업이 수행된 후에는 결과가 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-145">Once those operations are performed, the results will be concatenated.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e65b1-146">쿼리가 일부 다른 도메인으로 변환될 경우 쿼리 식에서 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-146">Calling methods in query expressions is not supported if the query will be translated into some other domain.</span></span> <span data-ttu-id="e65b1-147">예를 들어 SQL Server에는 관련 컨텍스트가 없으므로 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]에서 일반 C# 메서드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-147">For example, you cannot call an ordinary C# method in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] because SQL Server has no context for it.</span></span> <span data-ttu-id="e65b1-148">그러나 저장 프로시저를 메서드에 매핑하고 저장 프로시저를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65b1-148">However, you can map stored procedures to methods and call those.</span></span> <span data-ttu-id="e65b1-149">자세한 내용은 [저장 프로시저](../../../../framework/data/adonet/sql/linq/stored-procedures.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e65b1-149">For more information, see [Stored Procedures](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="e65b1-150">참조</span><span class="sxs-lookup"><span data-stu-id="e65b1-150">See also</span></span>

- [<span data-ttu-id="e65b1-151">LINQ(Language-Integrated Query)(C#)</span><span class="sxs-lookup"><span data-stu-id="e65b1-151">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="e65b1-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e65b1-152">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="e65b1-153">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="e65b1-153">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)
- [<span data-ttu-id="e65b1-154">LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="e65b1-154">LINQ to XML (C#)</span></span>](./linq-to-xml-overview.md)
- [<span data-ttu-id="e65b1-155">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="e65b1-155">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="e65b1-156">select 절</span><span class="sxs-lookup"><span data-stu-id="e65b1-156">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
