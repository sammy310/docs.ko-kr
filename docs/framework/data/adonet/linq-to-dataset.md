---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 1c03cca80de6003a4e49278871983ed7fcb3dc0b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200669"
---
# <a name="linq-to-dataset"></a><span data-ttu-id="d7234-102">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="d7234-102">LINQ to DataSet</span></span>

<span data-ttu-id="d7234-103">LINQ to DataSet를 사용 하면 개체에 캐시 된 데이터를 보다 쉽고 빠르게 쿼리할 수 <xref:System.Data.DataSet> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7234-103">LINQ to DataSet makes it easier and faster to query over data cached in a <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="d7234-104">특히 LINQ to DataSet는 개발자가 별도의 쿼리 언어를 사용 하는 대신 프로그래밍 언어 자체에서 쿼리를 작성할 수 있도록 하 여 쿼리를 단순화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7234-104">Specifically, LINQ to DataSet simplifies querying by enabling developers to write queries from the programming language itself, instead of by using a separate query language.</span></span> <span data-ttu-id="d7234-105">이러한 기능은 visual studio 개발자에 게 특히 유용 합니다 .이는 이제 visual Studio에서 제공 하는 컴파일 시간 구문 검사, 정적 입력 및 IntelliSense 지원을 해당 쿼리에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7234-105">This is especially useful for Visual Studio developers, who can now take advantage of the compile-time syntax checking, static typing, and IntelliSense support provided by the Visual Studio in their queries.</span></span>  
  
 <span data-ttu-id="d7234-106">LINQ to DataSet를 사용 하 여 하나 이상의 데이터 원본에서 통합 된 데이터를 쿼리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7234-106">LINQ to DataSet can also be used to query over data that has been consolidated from one or more data sources.</span></span> <span data-ttu-id="d7234-107">이 기능은 논리적으로 집계된 데이터 쿼리, 웹 애플리케이션의 중간 계층 캐시 등과 같이 유연하게 데이터를 표현하고 처리해야 하는 여러 시나리오에 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7234-107">This enables many scenarios that require flexibility in how data is represented and handled, such as querying locally aggregated data and middle-tier caching in Web applications.</span></span> <span data-ttu-id="d7234-108">이러한 조작 방법은 일반적인 보고, 분석 및 비즈니스 인텔리전스 애플리케이션에 특히 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d7234-108">In particular, generic reporting, analysis, and business intelligence applications require this method of manipulation.</span></span>  
  
 <span data-ttu-id="d7234-109">LINQ to DataSet 기능은 주로 및 클래스의 확장 메서드를 통해 노출 됩니다 <xref:System.Data.DataRowExtensions> <xref:System.Data.DataTableExtensions> .</span><span class="sxs-lookup"><span data-stu-id="d7234-109">The LINQ to DataSet functionality is exposed primarily through the extension methods in the <xref:System.Data.DataRowExtensions> and <xref:System.Data.DataTableExtensions> classes.</span></span> <span data-ttu-id="d7234-110">LINQ to DataSet는 기존 ADO.NET 아키텍처를 기반으로 하며 응용 프로그램 코드에서 ADO.NET를 대체 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7234-110">LINQ to DataSet builds on and uses the existing ADO.NET architecture, and is not meant to replace ADO.NET in application code.</span></span> <span data-ttu-id="d7234-111">기존 ADO.NET 코드는 LINQ to DataSet 응용 프로그램에서 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7234-111">Existing ADO.NET code will continue to function in a LINQ to DataSet application.</span></span> <span data-ttu-id="d7234-112">ADO.NET와 데이터 저장소에 대 한 LINQ to DataSet의 관계는 다음 다이어그램에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7234-112">The relationship of LINQ to DataSet to ADO.NET and the data store is illustrated in the following diagram.</span></span>  
  
 ![ADO.NET 공급자를 기반으로 LINQ to DataSet 있음을 보여 주는 다이어그램](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="d7234-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d7234-114">In This Section</span></span>  

 [<span data-ttu-id="d7234-115">시작</span><span class="sxs-lookup"><span data-stu-id="d7234-115">Getting Started</span></span>](getting-started-linq-to-dataset.md)  
  
 [<span data-ttu-id="d7234-116">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d7234-116">Programming Guide</span></span>](programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a><span data-ttu-id="d7234-117">참고</span><span class="sxs-lookup"><span data-stu-id="d7234-117">Reference</span></span>  

 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a><span data-ttu-id="d7234-118">참조</span><span class="sxs-lookup"><span data-stu-id="d7234-118">See also</span></span>

- [<span data-ttu-id="d7234-119">LINQ(Language-Integrated Query) - C#</span><span class="sxs-lookup"><span data-stu-id="d7234-119">Language-Integrated Query (LINQ) - C#</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="d7234-120">LINQ(Language-Integrated Query) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7234-120">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="d7234-121">LINQ 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d7234-121">LINQ and ADO.NET</span></span>](linq-and-ado-net.md)
- [<span data-ttu-id="d7234-122">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d7234-122">ADO.NET</span></span>](index.md)
