---
title: '방법: 다형성 쿼리 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 08ae5722267ef781ed6bee59c7895269f63a75e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606192"
---
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="79664-102">방법: 다형성 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="79664-102">How to: Execute a Polymorphic Query</span></span>

<span data-ttu-id="79664-103">이 항목에서는 다형성을 실행 하는 방법을 보여 줍니다 [!INCLUDE[esql](../../../../../includes/esql-md.md)] 사용 하 여 쿼리를 [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="79664-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) operator.</span></span>

### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="79664-104">이 예제의 코드를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="79664-104">To run the code in this example</span></span>

1. <span data-ttu-id="79664-105">추가 합니다 [School 모델](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) 프로젝트 및 Entity Framework를 사용 하도록 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="79664-105">Add the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="79664-106">자세한 내용은 [방법: 엔터티 데이터 모델 마법사를 사용 하 여](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))입니다.</span><span class="sxs-lookup"><span data-stu-id="79664-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

2. <span data-ttu-id="79664-107">애플리케이션의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="79664-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. <span data-ttu-id="79664-108">단계를 수행 하 여 계층당 하나의 테이블 상속을 포함 하는 개념적 모델을 수정 [연습: 매핑 상속 – 계층당 하나의 테이블](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="79664-108">Modify the conceptual model to have a table-per-hierarchy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="79664-109">예제</span><span class="sxs-lookup"><span data-stu-id="79664-109">Example</span></span>

<span data-ttu-id="79664-110">다음 예제에서는 OFTYPE 연산자를 사용하여 `OnsiteCourses` 컬렉션의 `Courses`만으로 구성된 컬렉션을 가져와서 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="79664-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a><span data-ttu-id="79664-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="79664-111">See also</span></span>

- [<span data-ttu-id="79664-112">Entity Framework용 EntityClient 공급자</span><span class="sxs-lookup"><span data-stu-id="79664-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="79664-113">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="79664-113">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
