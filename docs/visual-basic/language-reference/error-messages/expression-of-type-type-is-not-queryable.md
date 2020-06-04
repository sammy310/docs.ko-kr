---
title: <type> 형식의 식은 쿼리할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: e61b4dac109f714b5cf25226d1029237ca77032d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409480"
---
# <a name="expression-of-type-type-is-not-queryable"></a><span data-ttu-id="d4ba6-102">\<type> 형식의 식은 쿼리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-102">Expression of type \<type> is not queryable</span></span>
<span data-ttu-id="d4ba6-103">형식의 식은 \<type> 쿼리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="d4ba6-104">LINQ 공급자에 대 한 어셈블리 참조 및/또는 네임 스페이스 가져오기가 누락 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="d4ba6-105">쿼리 가능한 형식은 <xref:System.Linq> , <xref:System.Data.Linq> 및 네임 스페이스에 정의 됩니다 <xref:System.Xml.Linq> .</span><span class="sxs-lookup"><span data-stu-id="d4ba6-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="d4ba6-106">LINQ 쿼리를 수행 하려면 이러한 네임 스페이스를 하나 이상 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="d4ba6-107">네임 스페이스를 사용 하면 <xref:System.Linq> LINQ를 사용 하 여 컬렉션 및 배열과 같은 개체를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="d4ba6-108">네임 스페이스를 사용 하면 <xref:System.Data.Linq> LINQ를 사용 하 여 ADO.NET 데이터 집합 및 SQL Server 데이터베이스를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="d4ba6-109">네임 스페이스를 사용 하면 <xref:System.Xml.Linq> LINQ를 사용 하 여 xml을 쿼리하고 Visual Basic에서 xml 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="d4ba6-110">**오류 ID:** BC36593</span><span class="sxs-lookup"><span data-stu-id="d4ba6-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d4ba6-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d4ba6-111">To correct this error</span></span>  
  
1. <span data-ttu-id="d4ba6-112">`Import` <xref:System.Linq> , 또는 네임 스페이스에 대 한 문을 <xref:System.Data.Linq> <xref:System.Xml.Linq> 코드 파일에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="d4ba6-113">프로젝트 디자이너의 **참조** 페이지 (**My project**)를 사용 하 여 프로젝트에 대 한 네임 스페이스를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2. <span data-ttu-id="d4ba6-114">쿼리의 원본으로 식별 한 형식이 쿼리 가능한 형식 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba6-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="d4ba6-115">즉, 또는을 구현 하는 형식입니다 <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="d4ba6-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ba6-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4ba6-116">See also</span></span>

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [<span data-ttu-id="d4ba6-117">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="d4ba6-117">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="d4ba6-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="d4ba6-118">LINQ</span></span>](../../programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="d4ba6-119">XML</span><span class="sxs-lookup"><span data-stu-id="d4ba6-119">XML</span></span>](../../programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="d4ba6-120">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="d4ba6-120">References and the Imports Statement</span></span>](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="d4ba6-121">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="d4ba6-121">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="d4ba6-122">참조 페이지, 프로젝트 디자이너(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4ba6-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
