---
title: 데이터 집합 쿼리(LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: 79a9b320fbdbfecc3f7d531d992b1529873871a5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783042"
---
# <a name="querying-datasets-linq-to-dataset"></a><span data-ttu-id="785ca-102">데이터 집합 쿼리(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="785ca-102">Querying DataSets (LINQ to DataSet)</span></span>
<span data-ttu-id="785ca-103"><xref:System.Data.DataSet> 개체에 데이터가 채워지면 개체에 대한 쿼리를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785ca-103">After a <xref:System.Data.DataSet> object has been populated with data, you can begin querying it.</span></span> <span data-ttu-id="785ca-104">LINQ to DataSet 사용 하 여 쿼리를 작성 하 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] 는 것 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]은 다른 사용 데이터 소스에 대해를 사용 하는 것과 비슷합니다</span><span class="sxs-lookup"><span data-stu-id="785ca-104">Formulating queries with LINQ to DataSet is similar to using [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] against other [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-enabled data sources.</span></span> <span data-ttu-id="785ca-105">그러나 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 쿼리를 <xref:System.Data.DataSet> 개체에 사용할 경우 사용자 지정 형식의 열거형 대신 <xref:System.Data.DataRow> 개체의 열거형을 쿼리하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="785ca-105">Remember, however, that when you use [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries over a <xref:System.Data.DataSet> object you are querying an enumeration of <xref:System.Data.DataRow> objects, instead of an enumeration of a custom type.</span></span> <span data-ttu-id="785ca-106">즉, <xref:System.Data.DataRow> 쿼리에서는 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 클래스의 모든 멤버를 사용할 수 있으므로</span><span class="sxs-lookup"><span data-stu-id="785ca-106">This means that you can use any of the members of the <xref:System.Data.DataRow> class in your [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="785ca-107">다양한 기능의 복잡한 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785ca-107">This lets you to create rich, complex queries.</span></span>  
  
 <span data-ttu-id="785ca-108">의 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]다른 구현과 마찬가지로 쿼리 식 구문과 메서드 기반 쿼리 구문 이라는 두 가지 형식으로 LINQ to DataSet 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785ca-108">As with other implementations of [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], you can create LINQ to DataSet queries in two different forms: query expression syntax and method-based query syntax.</span></span> <span data-ttu-id="785ca-109">쿼리 식 구문 또는 메서드 기반 쿼리 구문을 사용하여 <xref:System.Data.DataSet>의 단일 테이블, <xref:System.Data.DataSet>의 여러 테이블 또는 형식화된 <xref:System.Data.DataSet>의 테이블에 대해 쿼리를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785ca-109">You can use query expression syntax or method-based query syntax to perform queries against single tables in a <xref:System.Data.DataSet>, against multiple tables in a <xref:System.Data.DataSet>, or against tables in a typed <xref:System.Data.DataSet>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="785ca-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="785ca-110">In This Section</span></span>  
 [<span data-ttu-id="785ca-111">단일 테이블 쿼리</span><span class="sxs-lookup"><span data-stu-id="785ca-111">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="785ca-112">단일 테이블 쿼리를 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="785ca-112">Describes how to perform single-table queries.</span></span>  
  
 [<span data-ttu-id="785ca-113">크로스 테이블 쿼리</span><span class="sxs-lookup"><span data-stu-id="785ca-113">Cross-Table Queries</span></span>](cross-table-queries-linq-to-dataset.md)  
 <span data-ttu-id="785ca-114">크로스 테이블 쿼리를 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="785ca-114">Describes how to perform cross-table queries.</span></span>  
  
 [<span data-ttu-id="785ca-115">형식화된 데이터 집합 쿼리</span><span class="sxs-lookup"><span data-stu-id="785ca-115">Querying Typed DataSets</span></span>](querying-typed-datasets.md)  
 <span data-ttu-id="785ca-116">형식화된 <xref:System.Data.DataSet> 개체를 쿼리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="785ca-116">Describes how to query typed <xref:System.Data.DataSet> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785ca-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="785ca-117">See also</span></span>

- [<span data-ttu-id="785ca-118">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="785ca-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="785ca-119">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="785ca-119">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
