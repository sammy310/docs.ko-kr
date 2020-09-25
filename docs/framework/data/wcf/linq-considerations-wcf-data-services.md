---
title: LINQ 고려 사항(WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ
- querying the data service [WCF Data Services]
- WCF Data Services, querying
ms.assetid: cc4ec9e9-348f-42a6-a78e-1cd40e370656
ms.openlocfilehash: 2523aac510516fdf19087425b10ab3f2296eb726
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194346"
---
# <a name="linq-considerations-wcf-data-services"></a>LINQ 고려 사항(WCF Data Services)

이 항목에서는 WCF Data Services 클라이언트를 사용할 때 LINQ 쿼리를 작성 하 고 실행 하는 방법에 대 한 정보를 제공 하 고 LINQ를 사용 하 여 OData (Open Data Protocol)를 구현 하는 데이터 서비스를 쿼리할 수 있는 제한 사항을 제공 합니다. OData 기반 데이터 서비스에 대 한 쿼리를 작성 하 고 실행 하는 방법에 대 한 자세한 내용은 [데이터 서비스 쿼리](querying-the-data-service-wcf-data-services.md)를 참조 하세요.  
  
## <a name="composing-linq-queries"></a>LINQ 쿼리 작성  

 LINQ 쿼리를 사용하면 <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 개체의 집합에 대한 쿼리를 작성할 수 있습니다. Visual Studio 및 DataSvcUtil.exe 도구의 **서비스 참조 추가** 대화 상자는 모두에서 상속 되는 엔터티 컨테이너 클래스와 피드에 반환 되는 엔터티를 나타내는 개체와 같은 OData 서비스의 표현을 생성 하는 데 사용 됩니다 <xref:System.Data.Services.Client.DataServiceContext> . 또한 이러한 도구는 서비스에서 피드로 노출되는 모음의 엔터티 컨테이너 클래스에 대한 속성도 생성합니다. 데이터 서비스를 캡슐화하는 클래스의 해당 속성은 <xref:System.Data.Services.Client.DataServiceQuery%601>을 반환합니다. <xref:System.Data.Services.Client.DataServiceQuery%601> 클래스가 LINQ로 정의된 <xref:System.Linq.IQueryable%601> 인터페이스를 구현하기 때문에 데이터 서비스를 통해 노출되는 피드에 대해 LINQ 쿼리를 작성할 수 있으며, 이 쿼리는 클라이언트 라이브러리에 의해 실행 시 데이터 서비스로 보내지는 쿼리 요청 URI로 변환됩니다.  
  
> [!IMPORTANT]
> LINQ 구문에서 표현할 수 있는 쿼리 집합은 OData 데이터 서비스에서 사용 되는 URI 구문에서 사용 되는 것 보다 더 광범위 합니다. 쿼리를 대상 데이터 서비스의 URI에 매핑할 수 없으면 <xref:System.NotSupportedException>이 발생합니다. 자세한 내용은이 항목의 [지원 되지 않는 LINQ 메서드](linq-considerations-wcf-data-services.md#unsupportedMethods) 를 참조 하세요.  
  
 다음 예는 운송료가 $30를 초과하는 `Orders`를 반환하고 결과를 최근 운송 날짜순으로 정렬하는 LINQ 쿼리입니다.  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqspecific)]
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqspecific)]
  
 이 LINQ 쿼리는 Northwind 기반 [퀵 스타트](quickstart-wcf-data-services.md) 데이터 서비스에 대해 실행 되는 다음 쿼리 URI로 변환 됩니다.  
  
```http
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30  
```  
  
 LINQ에 대 한 자세한 내용은 linq ( [언어 통합 쿼리)-c #](../../../csharp/programming-guide/concepts/linq/index.md) 또는 [Linq (통합 언어 쿼리)-Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)를 참조 하세요.  
  
 LINQ를 통해 위의 예제와 같은 언어별 선언적 쿼리 구문과 표준 쿼리 연산자로 알려진 쿼리 메서드 집합을 모두 사용하여 쿼리를 작성할 수 있습니다. 위의 예와 동등한 쿼리는 다음 예와 같이 메서드 기반 구문만을 사용하여 작성할 수 있습니다.  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqexpressionspecific)]
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqexpressionspecific)]
  
 WCF Data Services 클라이언트는 두 종류의 구성 된 쿼리를 쿼리 URI로 변환할 수 있으며 쿼리 식에 쿼리 메서드를 추가 하 여 LINQ 쿼리를 확장할 수 있습니다. 쿼리 식 또는 <xref:System.Data.Services.Client.DataServiceQuery%601>에 메서드 구문을 추가하여 LINQ 쿼리를 작성할 때 메서드가 호출되는 순서로 연산이 쿼리 URI에 추가됩니다. 이 동작은 <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> 메서드를 호출하여 쿼리 URI에 각 쿼리 옵션을 추가하는 것과 같습니다.  
  
## <a name="executing-linq-queries"></a>LINQ 쿼리 실행  

 <xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> 또는 <xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>과 같은 쿼리에 추가되는 특정 LINQ 쿼리 메서드로 인해 쿼리가 실행됩니다. 또한 쿼리는 `foreach` 루프 중이나 쿼리가 `List` 컬렉션에 할당될 때와 같이 결과가 명시적으로 열거될 때에도 실행됩니다. 자세한 내용은 [데이터 서비스 쿼리](querying-the-data-service-wcf-data-services.md)를 참조 하세요.  
  
 클라이언트는 LINQ 쿼리를 두 부분으로 실행합니다. 가능한 경우 쿼리의 LINQ 식이 클라이언트에서 먼저 계산된 다음 URI 기반 쿼리가 생성되고 서비스의 데이터와 비교하여 평가되도록 데이터 서비스로 보내집니다. 자세한 내용은 [데이터 서비스 쿼리](querying-the-data-service-wcf-data-services.md)에서 [클라이언트 및 서버 실행](querying-the-data-service-wcf-data-services.md#executingQueries) 단원을 참조 하세요.  
  
 OData 규격 쿼리 URI에서 LINQ 쿼리를 변환할 수 없는 경우 실행을 시도할 때 예외가 발생 합니다. 자세한 내용은 [데이터 서비스 쿼리](querying-the-data-service-wcf-data-services.md)를 참조 하세요.  
  
## <a name="linq-query-examples"></a>LINQ 쿼리 예제  

 다음 섹션의 예에서는 OData 서비스에 대해 실행할 수 있는 LINQ 쿼리 종류를 보여 줍니다.  
  
<a name="filtering"></a>

### <a name="filtering"></a>필터링  

 이 단원의 LINQ 쿼리 예는 서비스에서 반환된 피드의 데이터를 필터링합니다.  
  
 다음 예는 운송료가 $30를 초과하는 주문만 반환되도록 반환된 `Orders` 엔터티를 필터링하는 쿼리입니다.  
  
- LINQ 쿼리 구문 사용:  
  
[!code-csharp[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwhereclausespecific)]
[!code-vb[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwhereclausespecific)]
  
- LINQ 쿼리 메서드 사용:  
  
[!code-csharp[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwheremethodspecific)]
[!code-vb[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwheremethodspecific)]
  
- URI 쿼리 문자열 `$filter` 옵션:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitquerywheremethodspecific)]
[!code-vb[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitquerywheremethodspecific)]
  
 위의 모든 예제는 쿼리 URI `http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M`으로 변환됩니다.  
  
<a name="sorting"></a>

### <a name="sorting"></a>정렬  

 다음 예제는 회사 이름 및 우편 번호를 기준으로 반환된 데이터를 내림차순으로 정렬하는 쿼리를 나타냅니다.  
  
- LINQ 쿼리 구문 사용:  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbyclausespecific)]
[!code-vb[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbyclausespecific)]
  
- LINQ 쿼리 메서드 사용:  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbymethodspecific)]
[!code-vb[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbymethodspecific)]
  
- URI 쿼리 문자열 `$orderby` 옵션:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryorderbymethodspecific)]
[!code-vb[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryorderbymethodspecific)]
  
 위의 모든 예제는 쿼리 URI `http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc`으로 변환됩니다.  
  
<a name="projection"></a>

### <a name="projection"></a>프로젝션  

 다음 예는 반환된 데이터를 더 좁은 범위의 `CustomerAddress` 유형으로 프로젝션하는 동등한 쿼리를 나타냅니다.  
  
- LINQ 쿼리 구문 사용:  
  
[!code-csharp[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectclausespecific)]
[!code-vb[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectclausespecific)]
  
- LINQ 쿼리 메서드 사용:  
  
[!code-csharp[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectmethodspecific)]
[!code-vb[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectmethodspecific)]

> [!NOTE]
> `$select` 쿼리 옵션은 <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> 메서드를 사용하여 쿼리 URI에 추가할 수 없습니다. LINQ <xref:System.Linq.Enumerable.Select%2A> 메서드를 사용하여 클라이언트에서 요청 URI에 `$select` 쿼리 옵션을 생성하도록 하는 것이 좋습니다.  
  
 위의 두 가지 예는 쿼리 URI `"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"`로 변환됩니다.  
  
<a name="paging"></a>

### <a name="client-paging"></a>클라이언트 페이징  

 다음 예에서는 첫 50개 주문은 건너뛰고 25개 주문을 포함하는 정렬된 주문 엔터티 페이지를 요청하는 쿼리를 나타냅니다.  
  
- LINQ 쿼리에 쿼리 메서드 적용:  
  
[!code-csharp[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqskiptakemethodspecific)]
[!code-vb[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqskiptakemethodspecific)]
  
- URI 쿼리 문자열 `$skip` 및 `$top` 옵션:  
  
[!code-csharp[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryskiptakemethodspecific)]
[!code-vb[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryskiptakemethodspecific)]
  
 위의 두 가지 예는 쿼리 URI `http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25`로 변환됩니다.  
  
<a name="expand"></a>

### <a name="expand"></a>Expand  

 OData 데이터 서비스를 쿼리하면 쿼리를 대상으로 하는 엔터티와 관련 된 엔터티에 반환 된 피드가 포함 되도록 요청할 수 있습니다. <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> 메서드는 LINQ 쿼리의 대상인 엔터티 집합에 대한 <xref:System.Data.Services.Client.DataServiceQuery%601>에서 호출되며, 관련 엔터티 집합 이름은 `path` 매개 변수로 지정됩니다. 자세한 내용은 [지연 된 콘텐츠 로드](loading-deferred-content-wcf-data-services.md)를 참조 하세요.  
  
 다음 예에서는 쿼리에서 <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> 메서드를 사용하는 여러 가지 동등한 방법을 보여 줍니다.  
  
- LINQ 쿼리 구문:  
  
[!code-csharp[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandspecific)]
[!code-vb[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandspecific)]  
  
- LINQ 쿼리 메서드 사용:  

[!code-csharp[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandmethodspecific)]
[!code-vb[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandmethodspecific)]

 위의 두 가지 예는 쿼리 URI `http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details`로 변환됩니다.  
  
<a name="unsupportedMethods"></a>

## <a name="unsupported-linq-methods"></a>지원되는 LINQ 메서드  

 다음 표에서는 지원 되지 않으며 OData 서비스에 대해 실행 되는 쿼리에 포함 될 수 없는 LINQ 메서드의 클래스를 포함 합니다.  
  
|작업 유형|지원되지 않는 메서드|  
|--------------------|------------------------|  
|집합 연산자|다음을 포함한 모든 집합 연산자는 <xref:System.Data.Services.Client.DataServiceQuery%601>에 대해 지원되지 않습니다.<br /><br /> -   <xref:System.Linq.Enumerable.All%2A><br />-   <xref:System.Linq.Enumerable.Any%2A><br />-   <xref:System.Linq.Enumerable.Concat%2A><br />-   <xref:System.Linq.Enumerable.DefaultIfEmpty%2A><br />-   <xref:System.Linq.Enumerable.Distinct%2A><br />-   <xref:System.Linq.Enumerable.Except%2A><br />-   <xref:System.Linq.Enumerable.Intersect%2A><br />-   <xref:System.Linq.Enumerable.Union%2A><br />-   <xref:System.Linq.Enumerable.Zip%2A>|  
|정렬 연산자:|<xref:System.Collections.Generic.IComparer%601>이 필요한 다음과 같은 모든 정렬 연산자는 <xref:System.Data.Services.Client.DataServiceQuery%601>에 대해 지원되지 않습니다.<br /><br /> -   <xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29>|  
|프로젝션 및 필터링 연산자|위치 인수를 허용하는 다음과 같은 프로젝션 및 필터링 연산자는 <xref:System.Data.Services.Client.DataServiceQuery%601>에 대해 지원되지 않습니다.<br /><br /> -   <xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2C%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Where%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29>|  
|그룹화 연산자|다음을 포함한 모든 그룹화 연산자는 <xref:System.Data.Services.Client.DataServiceQuery%601>에 대해 지원되지 않습니다.<br /><br /> -   <xref:System.Linq.Enumerable.GroupBy%2A><br />-   <xref:System.Linq.Enumerable.GroupJoin%2A><br /><br /> 그룹화 연산은 클라이언트에서 수행되어야 합니다.|  
|집계 연산자|다음을 포함한 모든 집계 연산자는 <xref:System.Data.Services.Client.DataServiceQuery%601>에 대해 지원되지 않습니다.<br /><br /> -   <xref:System.Linq.Enumerable.Aggregate%2A><br />-   <xref:System.Linq.Enumerable.Average%2A><br />-   <xref:System.Linq.Enumerable.Count%2A><br />-   <xref:System.Linq.Enumerable.LongCount%2A><br />-   <xref:System.Linq.Enumerable.Max%2A><br />-   <xref:System.Linq.Enumerable.Min%2A><br />-   <xref:System.Linq.Enumerable.Sum%2A><br /><br /> 집계 연산은 클라이언트에서 수행되거나 서비스 작업으로 캡슐화되어야 합니다.|  
|페이징 연산자|다음 페이징 연산자는 <xref:System.Data.Services.Client.DataServiceQuery%601>에 대해 지원되지 않습니다.<br /><br /> -   <xref:System.Linq.Enumerable.ElementAt%2A><br />-   <xref:System.Linq.Enumerable.Last%2A><br />-   <xref:System.Linq.Enumerable.LastOrDefault%2A><br />-   <xref:System.Linq.Enumerable.SkipWhile%2A><br />-   <xref:System.Linq.Enumerable.TakeWhile%2A><br/><br/>**참고:**  빈 시퀀스에서 실행 되는 페이징 연산자는 null을 반환 합니다.|  
|기타 연산자|또한 다음 연산자는에 대해 지원 되지 않습니다 <xref:System.Data.Services.Client.DataServiceQuery%601> .<br /><br /> - <xref:System.Linq.Enumerable.Empty%2A><br />- <xref:System.Linq.Enumerable.Range%2A><br />- <xref:System.Linq.Enumerable.Repeat%2A><br />- <xref:System.Linq.Enumerable.ToDictionary%2A><br />- <xref:System.Linq.Enumerable.ToLookup%2A>|  
  
<a name="supportedExpressions"></a>

## <a name="supported-expression-functions"></a>지원되는 식 함수  

 다음과 같은 CLR (공용 언어 런타임) 메서드 및 속성은 OData 서비스에 대 한 요청 URI에 포함 하기 위해 쿼리 식에서 변환 될 수 있기 때문에 지원 됩니다.  
  
|<xref:System.String> 멤버|지원 되는 OData 함수|  
|-----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.String.Concat%28System.String%2CSystem.String%29>|`string concat(string p0, string p1)`|  
|<xref:System.String.Contains%28System.String%29>|`bool substringof(string p0, string p1)`|  
|<xref:System.String.EndsWith%28System.String%29>|`bool endswith(string p0, string p1)`|  
|<xref:System.String.IndexOf%28System.String%2CSystem.Int32%29>|`int indexof(string p0, string p1)`|  
|<xref:System.String.Length>|`int length(string p0)`|  
|<xref:System.String.Replace%28System.String%2CSystem.String%29>|`string replace(string p0, string find, string replace)`|  
|<xref:System.String.Substring%28System.Int32%29>|`string substring(string p0, int pos)`|  
|<xref:System.String.Substring%28System.Int32%2CSystem.Int32%29>|`string substring(string p0, int pos, int length)`|  
|<xref:System.String.ToLower>|`string tolower(string p0)`|  
|<xref:System.String.ToUpper>|`string toupper(string p0)`|  
|<xref:System.String.Trim>|`string trim(string p0)`|  
  
|<xref:System.DateTime> 구성원<sup>1</sup>|지원 되는 OData 함수|  
|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Day>|`int day(DateTime p0)`|  
|<xref:System.DateTime.Hour>|`int hour(DateTime p0)`|  
|<xref:System.DateTime.Minute>|`int minute(DateTime p0)`|  
|<xref:System.DateTime.Month>|`int month(DateTime p0)`|  
|<xref:System.DateTime.Second>|`int second(DateTime p0)`|  
|<xref:System.DateTime.Year>|`int year(DateTime p0)`|  
  
 <sup>1</sup> 의 해당 날짜 및 시간 속성과 <xref:Microsoft.VisualBasic.DateAndTime?displayProperty=nameWithType> <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> Visual Basic 메서드도 지원 됩니다.  
  
|<xref:System.Math> 멤버|지원 되는 OData 함수|  
|---------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Math.Ceiling%28System.Decimal%29>|`decimal ceiling(decimal p0)`|  
|<xref:System.Math.Ceiling%28System.Double%29>|`double ceiling(double p0)`|  
|<xref:System.Math.Floor%28System.Decimal%29>|`decimal floor(decimal p0)`|  
|<xref:System.Math.Floor%28System.Double%29>|`double floor(double p0)`|  
|<xref:System.Math.Round%28System.Decimal%29>|`decimal round(decimal p0)`|  
|<xref:System.Math.Round%28System.Double%29>|`double round(double p0)`|  
  
|<xref:System.Linq.Expressions.Expression> 멤버|지원 되는 OData 함수|  
|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Linq.Expressions.Expression.TypeIs%28System.Linq.Expressions.Expression%2CSystem.Type%29>|`bool isof(type p0)`|  
  
 또한 클라이언트가 추가 CLR 함수를 계산할 수 있습니다. 클라이언트에서 계산할 수 없고 서버에서 계산하기 위해 올바른 요청 URI로 변환할 수 없는 식에 대해서는 <xref:System.NotSupportedException>이 발생합니다.  
  
## <a name="see-also"></a>참고 항목

- [데이터 서비스 쿼리](querying-the-data-service-wcf-data-services.md)
- [프로젝션 쿼리](query-projections-wcf-data-services.md)
- [개체 구체화](object-materialization-wcf-data-services.md)
- [OData: URI 규칙](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/)
