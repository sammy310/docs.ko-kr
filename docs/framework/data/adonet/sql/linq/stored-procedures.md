---
description: '다음에 대 한 자세한 정보: 저장 프로시저'
title: 저장 프로시저
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: 16157dc5a8d2da880deb2d43b649b872d19c73a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681437"
---
# <a name="stored-procedures"></a><span data-ttu-id="68d19-103">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="68d19-103">Stored Procedures</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="68d19-104">는 개체 모델의 메서드를 사용 하 여 데이터베이스의 저장 프로시저를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-104">uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="68d19-105">필요한 위치에 <xref:System.Data.Linq.Mapping.FunctionAttribute> 특성과 <xref:System.Data.Linq.Mapping.ParameterAttribute> 특성을 적용하여 메서드를 저장 프로시저로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-105">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="68d19-106">자세한 내용은 [LINQ to SQL 개체 모델](the-linq-to-sql-object-model.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68d19-106">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="68d19-107">Visual Studio를 사용 하는 개발자는 일반적으로 개체 관계형 디자이너를 사용 하 여 저장 프로시저를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-107">Developers using Visual Studio would typically use the Object Relational Designer to map stored procedures.</span></span> <span data-ttu-id="68d19-108">이 단원의 항목에서는 코드를 사용자가 직접 작성하는 경우 애플리케이션에서 이러한 메서드를 만들어 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-108">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68d19-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="68d19-109">In This Section</span></span>  

 [<span data-ttu-id="68d19-110">방법: 행 집합 반환</span><span class="sxs-lookup"><span data-stu-id="68d19-110">How to: Return Rowsets</span></span>](how-to-return-rowsets.md)  
 <span data-ttu-id="68d19-111">데이터의 행을 반환하고 입력 매개 변수를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-111">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="68d19-112">방법: 매개 변수를 사용하는 저장 프로시저 사용</span><span class="sxs-lookup"><span data-stu-id="68d19-112">How to: Use Stored Procedures that Take Parameters</span></span>](how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="68d19-113">입력 및 출력 매개 변수를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-113">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="68d19-114">방법: 여러 결과 도형에 매핑된 저장 프로시저 사용</span><span class="sxs-lookup"><span data-stu-id="68d19-114">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="68d19-115">동일한 저장 프로시저에 다양한 모양의 반환을 제공하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-115">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="68d19-116">방법: 순차적 결과 도형에 매핑된 저장 프로시저 사용</span><span class="sxs-lookup"><span data-stu-id="68d19-116">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="68d19-117">반환 시퀀스에 다양한 모양을 제공하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-117">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="68d19-118">저장 프로시저를 사용하여 작업 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="68d19-118">Customizing Operations By Using Stored Procedures</span></span>](customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="68d19-119">저장 프로시저를 사용하여 삽입, 업데이트 및 삭제 작업을 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-119">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="68d19-120">단독으로 저장 프로시저를 사용하여 작업 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="68d19-120">Customizing Operations by Using Stored Procedures Exclusively</span></span>](customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="68d19-121">저장 프로시저만 사용하여 삽입, 업데이트 및 삭제 작업을 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-121">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="68d19-122">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="68d19-122">Related Sections</span></span>  

 [<span data-ttu-id="68d19-123">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="68d19-123">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="68d19-124">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개체 모델을 만들고 사용하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-124">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="68d19-125">연습: 저장 프로시저만 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68d19-125">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="68d19-126">Visual Basic에서 저장 프로시저를 사용하는 방법을 보여 주는 절차를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-126">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="68d19-127">연습: 저장 프로시저만 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="68d19-127">Walkthrough: Using Only Stored Procedures (C#)</span></span>](walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="68d19-128">C#에서 저장 프로시저를 사용하는 방법을 보여 주는 절차를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="68d19-128">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
