---
title: XPath 및 LINQ to XML 비교
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 87d361b1-daa9-4fd4-a53a-cbfa40111ad3
ms.openlocfilehash: e9bf192a2075653802f0c5a8b4e44ff0ceacb975
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "66487536"
---
# <a name="comparison-of-xpath-and-linq-to-xml"></a><span data-ttu-id="83a89-102">XPath 및 LINQ to XML 비교</span><span class="sxs-lookup"><span data-stu-id="83a89-102">Comparison of XPath and LINQ to XML</span></span>
<span data-ttu-id="83a89-103">XPath와 LINQ to XML은 유사한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-103">XPath and LINQ to XML offer some similar functionality.</span></span> <span data-ttu-id="83a89-104">XML 트리를 쿼리하여 결과를 요소 컬렉션, 특성 컬렉션, 노드 컬렉션 또는 요소나 특성의 값으로 반환하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-104">Both can be used to query an XML tree, returning such results as a collection of elements, a collection of attributes, a collection of nodes, or the value of an element or attribute.</span></span> <span data-ttu-id="83a89-105">하지만 차이점도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-105">However, there are also some differences.</span></span>  
  
## <a name="differences-between-xpath-and-linq-to-xml"></a><span data-ttu-id="83a89-106">XPath와 LINQ to XML의 차이점</span><span class="sxs-lookup"><span data-stu-id="83a89-106">Differences Between XPath and LINQ to XML</span></span>  
 <span data-ttu-id="83a89-107">XPath는 새 형식의 프로젝션을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-107">XPath does not allow projection of new types.</span></span> <span data-ttu-id="83a89-108">XPath는 트리에서 노드 컬렉션만 반환할 수 있지만, LINQ to XML은 쿼리를 실행하고 개체 그래프나 XML 트리를 새 모양으로 프로젝션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-108">It can only return collections of nodes from the tree, whereas LINQ to XML can execute a query and project an object graph or an XML tree in a new shape.</span></span> <span data-ttu-id="83a89-109">LINQ to XML 쿼리는 훨씬 많은 기능을 포함하며 XPath 식보다 훨씬 더 강력합니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-109">LINQ to XML queries encompass much more functionality and are much more powerful than XPath expressions.</span></span>  
  
 <span data-ttu-id="83a89-110">XPath 식은 문자열 내에 분리되어 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-110">XPath expressions exist in isolation within a string.</span></span> <span data-ttu-id="83a89-111">C# 컴파일러는 컴파일 시간에 XPath 식의 구문을 분석할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-111">The C# compiler cannot help parse the XPath expression at compile time.</span></span> <span data-ttu-id="83a89-112">이와 반대로 LINQ to XML 쿼리는 C# 컴파일러에서 구문이 분석되고 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-112">By contrast, LINQ to XML queries are parsed and compiled by the C# compiler.</span></span> <span data-ttu-id="83a89-113">컴파일러에서는 많은 쿼리 오류를 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-113">The compiler is able to catch many query errors.</span></span>  
  
 <span data-ttu-id="83a89-114">XPath 결과는 강력한 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-114">XPath results are not strongly typed.</span></span> <span data-ttu-id="83a89-115">많은 경우에 XPath 식의 계산 결과는 개체이며 적절한 형식을 결정하고 필요한 경우 결과를 캐스팅하는 것은 개발자에게 달려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-115">In a number of circumstances, the result of evaluating an XPath expression is an object, and it is up to the developer to determine the proper type and cast the result as necessary.</span></span> <span data-ttu-id="83a89-116">이와 반대로 LINQ to XML 쿼리의 프로젝션은 강력한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-116">By contrast, the projections from a LINQ to XML query are strongly typed.</span></span>  
  
## <a name="result-ordering"></a><span data-ttu-id="83a89-117">결과 정렬</span><span class="sxs-lookup"><span data-stu-id="83a89-117">Result Ordering</span></span>  
 <span data-ttu-id="83a89-118">XPath 1.0 권장 사항에는 XPath 식의 계산 결과인 컬렉션이 정렬되지 않는다고 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-118">The XPath 1.0 Recommendation states that a collection that is the result of evaluating an XPath expression is unordered.</span></span>  
  
 <span data-ttu-id="83a89-119">그러나 LINQ to XML XPath 축 메서드에서 반환하는 컬렉션을 반복할 때 컬렉션의 노드는 문서 순서로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-119">However, when iterating through a collection returned by a LINQ to XML XPath axis method, the nodes in the collection are returned in document order.</span></span> <span data-ttu-id="83a89-120">이는 조건자가 `preceding` 및 `preceding-sibling`과 같이 문서 순서의 역순으로 표현되는 XPath 축에 액세스하는 경우에도 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-120">This is the case even when accessing the XPath axes where predicates are expressed in terms of reverse document order, such as `preceding` and `preceding-sibling`.</span></span>  
  
 <span data-ttu-id="83a89-121">이와 반대로 대부분의 LINQ to XML 축은 문서 순서로 컬렉션을 반환하지만 그 중 <xref:System.Xml.Linq.XNode.Ancestors%2A> 및 <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>는 문서 순서의 역순으로 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-121">By contrast, most of the LINQ to XML axes return collections in document order, but two of them, <xref:System.Xml.Linq.XNode.Ancestors%2A> and <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, return collections in reverse document order.</span></span> <span data-ttu-id="83a89-122">다음 표에서는 축을 열거하고 각 축의 컬렉션 순서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-122">The following table enumerates the axes, and indicates collection order for each:</span></span>  
  
|<span data-ttu-id="83a89-123">LINQ to XML 축</span><span class="sxs-lookup"><span data-stu-id="83a89-123">LINQ to XML axis</span></span>|<span data-ttu-id="83a89-124">순서</span><span class="sxs-lookup"><span data-stu-id="83a89-124">Ordering</span></span>|  
|----------------------|--------------|  
|<span data-ttu-id="83a89-125">XContainer.DescendantNodes</span><span class="sxs-lookup"><span data-stu-id="83a89-125">XContainer.DescendantNodes</span></span>|<span data-ttu-id="83a89-126">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-126">Document order</span></span>|  
|<span data-ttu-id="83a89-127">XContainer.Descendants</span><span class="sxs-lookup"><span data-stu-id="83a89-127">XContainer.Descendants</span></span>|<span data-ttu-id="83a89-128">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-128">Document order</span></span>|  
|<span data-ttu-id="83a89-129">XContainer.Elements</span><span class="sxs-lookup"><span data-stu-id="83a89-129">XContainer.Elements</span></span>|<span data-ttu-id="83a89-130">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-130">Document order</span></span>|  
|<span data-ttu-id="83a89-131">XContainer.Nodes</span><span class="sxs-lookup"><span data-stu-id="83a89-131">XContainer.Nodes</span></span>|<span data-ttu-id="83a89-132">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-132">Document order</span></span>|  
|<span data-ttu-id="83a89-133">XContainer.NodesAfterSelf</span><span class="sxs-lookup"><span data-stu-id="83a89-133">XContainer.NodesAfterSelf</span></span>|<span data-ttu-id="83a89-134">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-134">Document order</span></span>|  
|<span data-ttu-id="83a89-135">XContainer.NodesBeforeSelf</span><span class="sxs-lookup"><span data-stu-id="83a89-135">XContainer.NodesBeforeSelf</span></span>|<span data-ttu-id="83a89-136">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-136">Document order</span></span>|  
|<span data-ttu-id="83a89-137">XElement.AncestorsAndSelf</span><span class="sxs-lookup"><span data-stu-id="83a89-137">XElement.AncestorsAndSelf</span></span>|<span data-ttu-id="83a89-138">문서 순서의 역순</span><span class="sxs-lookup"><span data-stu-id="83a89-138">Reverse document order</span></span>|  
|<span data-ttu-id="83a89-139">XElement.Attributes</span><span class="sxs-lookup"><span data-stu-id="83a89-139">XElement.Attributes</span></span>|<span data-ttu-id="83a89-140">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-140">Document order</span></span>|  
|<span data-ttu-id="83a89-141">XElement.DescendantNodesAndSelf</span><span class="sxs-lookup"><span data-stu-id="83a89-141">XElement.DescendantNodesAndSelf</span></span>|<span data-ttu-id="83a89-142">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-142">Document order</span></span>|  
|<span data-ttu-id="83a89-143">XElement.DescendantsAndSelf</span><span class="sxs-lookup"><span data-stu-id="83a89-143">XElement.DescendantsAndSelf</span></span>|<span data-ttu-id="83a89-144">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-144">Document order</span></span>|  
|<span data-ttu-id="83a89-145">XNode.Ancestors</span><span class="sxs-lookup"><span data-stu-id="83a89-145">XNode.Ancestors</span></span>|<span data-ttu-id="83a89-146">문서 순서의 역순</span><span class="sxs-lookup"><span data-stu-id="83a89-146">Reverse document order</span></span>|  
|<span data-ttu-id="83a89-147">XNode.ElementsAfterSelf</span><span class="sxs-lookup"><span data-stu-id="83a89-147">XNode.ElementsAfterSelf</span></span>|<span data-ttu-id="83a89-148">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-148">Document order</span></span>|  
|<span data-ttu-id="83a89-149">XNode.ElementsBeforeSelf</span><span class="sxs-lookup"><span data-stu-id="83a89-149">XNode.ElementsBeforeSelf</span></span>|<span data-ttu-id="83a89-150">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-150">Document order</span></span>|  
|<span data-ttu-id="83a89-151">XNode.NodesAfterSelf</span><span class="sxs-lookup"><span data-stu-id="83a89-151">XNode.NodesAfterSelf</span></span>|<span data-ttu-id="83a89-152">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-152">Document order</span></span>|  
|<span data-ttu-id="83a89-153">XNode.NodesBeforeSelf</span><span class="sxs-lookup"><span data-stu-id="83a89-153">XNode.NodesBeforeSelf</span></span>|<span data-ttu-id="83a89-154">문서 순서</span><span class="sxs-lookup"><span data-stu-id="83a89-154">Document order</span></span>|  
  
## <a name="positional-predicates"></a><span data-ttu-id="83a89-155">위치 조건자</span><span class="sxs-lookup"><span data-stu-id="83a89-155">Positional Predicates</span></span>  
 <span data-ttu-id="83a89-156">XPath 식에서 위치 조건자는 많은 축의 경우 문서 순서로 표현되지만 `preceding`, `preceding-sibling`, `ancestor` 및 `ancestor-or-self`와 같은 역방향 축의 경우에는 문서 순서의 역순으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-156">Within an XPath expression, positional predicates are expressed in terms of document order for many axes, but are expressed in reverse document order for reverse axes, which are `preceding`, `preceding-sibling`, `ancestor`, and `ancestor-or-self`.</span></span> <span data-ttu-id="83a89-157">예를 들어, XPath 식 `preceding-sibling::*[1]`은 바로 이전 형제를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-157">For example, the XPath expression `preceding-sibling::*[1]` returns the immediately preceding sibling.</span></span> <span data-ttu-id="83a89-158">이는 최종 결과 집합이 문서 순서로 제공되는 경우에도 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-158">This is the case even though the final result set is presented in document order.</span></span>  
  
 <span data-ttu-id="83a89-159">이와 반대로 LINQ to XML의 모든 위치 조건자는 항상 축의 순서로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-159">By contrast, all positional predicates in LINQ to XML are always expressed in terms of the order of the axis.</span></span> <span data-ttu-id="83a89-160">예를 들어, `anElement.ElementsBeforeSelf().ElementAt(0)`은 바로 이전 형제가 아니라 쿼리된 요소에 대한 부모의 첫 번째 자식 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-160">For example, `anElement.ElementsBeforeSelf().ElementAt(0)` returns the first child element of the parent of the queried element, not the immediate preceding sibling.</span></span> <span data-ttu-id="83a89-161">또 다른 예로, `anElement.Ancestors().ElementAt(0)`은 부모 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-161">Another example: `anElement.Ancestors().ElementAt(0)` returns the parent element.</span></span>  
  
 <span data-ttu-id="83a89-162">LINQ to XML에서 바로 이전 요소를 찾으려는 경우 다음 식을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-162">If you wanted to find the immediately preceding element in LINQ to XML, you would write the following expression:</span></span>  
  
```csharp
ElementsBeforeSelf().Last()
```
  
```vb
ElementsBeforeSelf().Last()
```
  
## <a name="performance-differences"></a><span data-ttu-id="83a89-163">성능 차이점</span><span class="sxs-lookup"><span data-stu-id="83a89-163">Performance Differences</span></span>  
 <span data-ttu-id="83a89-164">LINQ to XML에서 XPath 기능을 사용하는 XPath 쿼리의 성능은 LINQ to XML 쿼리의 성능보다 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-164">XPath queries that use the XPath functionality in LINQ to XML will not perform as well as LINQ to XML queries.</span></span>  
  
## <a name="comparison-of-composition"></a><span data-ttu-id="83a89-165">구성 비교</span><span class="sxs-lookup"><span data-stu-id="83a89-165">Comparison of Composition</span></span>  
 <span data-ttu-id="83a89-166">LINQ to XML 쿼리의 구성은 XPath 식의 구성과 다소 비슷하지만 구문은 매우 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-166">Composition of a LINQ to XML query is somewhat parallel to composition of an XPath expression, although very different in syntax.</span></span>  
  
 <span data-ttu-id="83a89-167">예를 들어, `customers`라는 변수에 요소가 있고 `CompanyName`라는 모든 자식 요소 아래에서 `Customer`이라는 손자 요소를 찾으려는 경우 다음과 같이 XPath 식을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-167">For example, if you have an element in a variable named `customers`, and you want to find a grandchild element named `CompanyName` under all child elements named `Customer`, you would write an XPath expression as follows:</span></span>  
  
```csharp  
customers.XPathSelectElements("./Customer/CompanyName")
```  
  
```vb
customers.XPathSelectElements("./Customer/CompanyName")
```

 <span data-ttu-id="83a89-168">동일한 LINQ to XML 쿼리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-168">The equivalent LINQ to XML query is:</span></span>  
  
```csharp  
customers.Elements("Customer").Elements("CompanyName")
```  
  
```vb
customers.Elements("Customer").Elements("CompanyName")
```  

 <span data-ttu-id="83a89-169">각 XPath 축과 유사한 LINQ to XML 축은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-169">There are similar parallels for each of the XPath axes.</span></span>  
  
|<span data-ttu-id="83a89-170">XPath 축</span><span class="sxs-lookup"><span data-stu-id="83a89-170">XPath axis</span></span>|<span data-ttu-id="83a89-171">LINQ to XML 축</span><span class="sxs-lookup"><span data-stu-id="83a89-171">LINQ to XML axis</span></span>|  
|----------------|----------------------|  
|<span data-ttu-id="83a89-172">child(기본 축)</span><span class="sxs-lookup"><span data-stu-id="83a89-172">child (the default axis)</span></span>|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="83a89-173">Parent(..)</span><span class="sxs-lookup"><span data-stu-id="83a89-173">Parent (..)</span></span>|<xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="83a89-174">attribute axis(@)</span><span class="sxs-lookup"><span data-stu-id="83a89-174">attribute axis (@)</span></span>|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="83a89-175">또는</span><span class="sxs-lookup"><span data-stu-id="83a89-175">or</span></span><br /><br /> <xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="83a89-176">ancestor 축</span><span class="sxs-lookup"><span data-stu-id="83a89-176">ancestor axis</span></span>|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="83a89-177">ancestor-or-self 축</span><span class="sxs-lookup"><span data-stu-id="83a89-177">ancestor-or-self axis</span></span>|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="83a89-178">descendant 축(//)</span><span class="sxs-lookup"><span data-stu-id="83a89-178">descendant axis (//)</span></span>|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="83a89-179">또는</span><span class="sxs-lookup"><span data-stu-id="83a89-179">or</span></span><br /><br /> <xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="83a89-180">descendant-or-self</span><span class="sxs-lookup"><span data-stu-id="83a89-180">descendant-or-self</span></span>|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="83a89-181">또는</span><span class="sxs-lookup"><span data-stu-id="83a89-181">or</span></span><br /><br /> <xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="83a89-182">following-sibling</span><span class="sxs-lookup"><span data-stu-id="83a89-182">following-sibling</span></span>|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="83a89-183">또는</span><span class="sxs-lookup"><span data-stu-id="83a89-183">or</span></span><br /><br /> <xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="83a89-184">preceding-sibling</span><span class="sxs-lookup"><span data-stu-id="83a89-184">preceding-sibling</span></span>|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="83a89-185">또는</span><span class="sxs-lookup"><span data-stu-id="83a89-185">or</span></span><br /><br /> <xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="83a89-186">following</span><span class="sxs-lookup"><span data-stu-id="83a89-186">following</span></span>|<span data-ttu-id="83a89-187">직접적으로 해당하는 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-187">No direct equivalent.</span></span>|  
|<span data-ttu-id="83a89-188">preceding</span><span class="sxs-lookup"><span data-stu-id="83a89-188">preceding</span></span>|<span data-ttu-id="83a89-189">직접적으로 해당하는 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83a89-189">No direct equivalent.</span></span>|  
  