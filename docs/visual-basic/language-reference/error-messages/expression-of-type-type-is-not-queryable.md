---
description: '자세히 알아보기: BC36593: 형식의 식은 <type> 쿼리할 수 없습니다.'
title: <type> 형식의 식은 쿼리할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: b2fc6c81ee34c1f8e251ac65ba582fde1c6a7b9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796355"
---
# <a name="bc36593-expression-of-type-type-is-not-queryable"></a><span data-ttu-id="257a4-103">BC36593: 형식의 식은 \<type> 쿼리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="257a4-103">BC36593: Expression of type \<type> is not queryable</span></span>

<span data-ttu-id="257a4-104">형식의 식은 \<type> 쿼리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="257a4-104">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="257a4-105">LINQ 공급자에 대 한 어셈블리 참조 및/또는 네임 스페이스 가져오기가 누락 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="257a4-105">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>

 <span data-ttu-id="257a4-106">쿼리 가능한 형식은 <xref:System.Linq> , <xref:System.Data.Linq> 및 네임 스페이스에 정의 됩니다 <xref:System.Xml.Linq> .</span><span class="sxs-lookup"><span data-stu-id="257a4-106">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="257a4-107">LINQ 쿼리를 수행 하려면 이러한 네임 스페이스를 하나 이상 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="257a4-107">You must import one or more of these namespaces to perform LINQ queries.</span></span>

 <span data-ttu-id="257a4-108">네임 스페이스를 사용 하면 <xref:System.Linq> LINQ를 사용 하 여 컬렉션 및 배열과 같은 개체를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257a4-108">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>

 <span data-ttu-id="257a4-109">네임 스페이스를 사용 하면 <xref:System.Data.Linq> LINQ를 사용 하 여 ADO.NET 데이터 집합 및 SQL Server 데이터베이스를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257a4-109">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>

 <span data-ttu-id="257a4-110">네임 스페이스를 사용 하면 <xref:System.Xml.Linq> LINQ를 사용 하 여 xml을 쿼리하고 Visual Basic에서 xml 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257a4-110">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>

 <span data-ttu-id="257a4-111">**오류 ID:** BC36593</span><span class="sxs-lookup"><span data-stu-id="257a4-111">**Error ID:** BC36593</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="257a4-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="257a4-112">To correct this error</span></span>

1. <span data-ttu-id="257a4-113">`Import` <xref:System.Linq> , 또는 네임 스페이스에 대 한 문을 <xref:System.Data.Linq> <xref:System.Xml.Linq> 코드 파일에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="257a4-113">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="257a4-114">프로젝트 디자이너의 **참조** 페이지 (**My project**)를 사용 하 여 프로젝트에 대 한 네임 스페이스를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="257a4-114">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>

2. <span data-ttu-id="257a4-115">쿼리의 원본으로 식별 한 형식이 쿼리 가능한 형식 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="257a4-115">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="257a4-116">즉, 또는을 구현 하는 형식입니다 <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="257a4-116">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>

## <a name="see-also"></a><span data-ttu-id="257a4-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="257a4-117">See also</span></span>

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [<span data-ttu-id="257a4-118">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="257a4-118">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="257a4-119">LINQ</span><span class="sxs-lookup"><span data-stu-id="257a4-119">LINQ</span></span>](../../programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="257a4-120">XML</span><span class="sxs-lookup"><span data-stu-id="257a4-120">XML</span></span>](../../programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="257a4-121">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="257a4-121">References and the Imports Statement</span></span>](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="257a4-122">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="257a4-122">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="257a4-123">참조 페이지, 프로젝트 디자이너(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="257a4-123">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
