---
description: '자세한 정보: LINQ to SQL 사용에 대 한 일반적인 단계'
title: LINQ to SQL 사용을 위한 일반 단계
ms.date: 03/30/2017
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
ms.openlocfilehash: eb35b983471db8926646418352b01e1186e235e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680969"
---
# <a name="typical-steps-for-using-linq-to-sql"></a><span data-ttu-id="64da5-103">LINQ to SQL 사용을 위한 일반 단계</span><span class="sxs-lookup"><span data-stu-id="64da5-103">Typical Steps for Using LINQ to SQL</span></span>

<span data-ttu-id="64da5-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 애플리케이션을 구현하려면 이 항목에 설명된 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-104">To implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application, you follow the steps described later in this topic.</span></span> <span data-ttu-id="64da5-105">대부분의 단계는 선택 사항이며</span><span class="sxs-lookup"><span data-stu-id="64da5-105">Note that many steps are optional.</span></span> <span data-ttu-id="64da5-106">고유한 개체 모델을 기본 상태에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-106">It is very possible that you can use your object model in its default state.</span></span>  
  
 <span data-ttu-id="64da5-107">매우 빠른 시작을 위해 개체 관계형 디자이너를 사용 하 여 개체 모델을 만들고 쿼리 코딩을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-107">For a really fast start, use the Object Relational Designer to create your object model and start coding your queries.</span></span>  
  
## <a name="creating-the-object-model"></a><span data-ttu-id="64da5-108">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="64da5-108">Creating the Object Model</span></span>  

 <span data-ttu-id="64da5-109">첫 번째 단계는 기존 관계형 데이터베이스의 메타데이터에서 개체 모델을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-109">The first step is to create an object model from the metadata of an existing relational database.</span></span> <span data-ttu-id="64da5-110">개체 모델은 개발자의 프로그래밍 언어에 따라 데이터베이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-110">The object model represents the database according to the programming language of the developer.</span></span> <span data-ttu-id="64da5-111">자세한 내용은 [LINQ to SQL 개체 모델](the-linq-to-sql-object-model.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64da5-111">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
### <a name="1-select-a-tool-to-create-the-model"></a><span data-ttu-id="64da5-112">1. 모델을 만들 도구를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-112">1. Select a tool to create the model.</span></span>  

 <span data-ttu-id="64da5-113">모델을 만들기 위한 세 가지 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-113">Three tools are available for creating the model.</span></span>  
  
- <span data-ttu-id="64da5-114">개체 관계형 디자이너</span><span class="sxs-lookup"><span data-stu-id="64da5-114">The Object Relational Designer</span></span>  
  
     <span data-ttu-id="64da5-115">이 디자이너는 기존 데이터베이스에서 개체 모델을 만들기 위한 풍부한 사용자 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-115">This designer provides a rich user interface for creating an object model from an existing database.</span></span> <span data-ttu-id="64da5-116">이 도구는 Visual Studio IDE의 일부 이며 중소 규모의 데이터베이스에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-116">This tool is part of the Visual Studio IDE, and is best suited to small or medium databases.</span></span>  
  
- <span data-ttu-id="64da5-117">SQLMetal 코드 생성 도구</span><span class="sxs-lookup"><span data-stu-id="64da5-117">The SQLMetal code-generation tool</span></span>  
  
     <span data-ttu-id="64da5-118">이 명령줄 유틸리티는 O/R 디자이너와 약간 다른 옵션 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-118">This command-line utility provides a slightly different set of options from the O/R Designer.</span></span> <span data-ttu-id="64da5-119">대규모 데이터베이스 모델링에는 이 도구를 사용하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-119">Modeling large databases is best done by using this tool.</span></span> <span data-ttu-id="64da5-120">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="64da5-120">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
- <span data-ttu-id="64da5-121">코드 편집기</span><span class="sxs-lookup"><span data-stu-id="64da5-121">A code editor</span></span>  
  
     <span data-ttu-id="64da5-122">Visual Studio code 편집기나 다른 편집기를 사용 하 여 사용자 고유의 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-122">You can write your own code by using either the Visual Studio code editor or another editor.</span></span> <span data-ttu-id="64da5-123">기존 데이터베이스를 사용 하 고 O/R 디자이너나 SQLMetal 도구를 사용할 수 있는 경우 오류가 발생할 수 있는이 방법은 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-123">We do not recommend this approach, which can be prone to errors, when you have an existing database and can use either the O/R Designer or the SQLMetal tool.</span></span> <span data-ttu-id="64da5-124">단, 다른 도구를 사용하여 이미 생성한 코드를 구체화하거나 수정하려는 경우 코드 편집기가 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-124">However, the code editor can be valuable for refining or modifying code you have already generated by using other tools.</span></span> <span data-ttu-id="64da5-125">자세한 내용은 [방법: 코드 편집기를 사용 하 여 엔터티 클래스 사용자 지정](how-to-customize-entity-classes-by-using-the-code-editor.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64da5-125">For more information, see [How to: Customize Entity Classes by Using the Code Editor](how-to-customize-entity-classes-by-using-the-code-editor.md).</span></span>  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a><span data-ttu-id="64da5-126">2. 생성 하려는 코드 종류를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-126">2. Select the kind of code you want to generate.</span></span>  
  
- <span data-ttu-id="64da5-127">특성 기반 매핑의 c # 또는 Visual Basic 소스 코드 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-127">A C# or Visual Basic source code file for attribute-based mapping.</span></span>  
  
     <span data-ttu-id="64da5-128">그런 다음 Visual Studio 프로젝트에이 코드 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-128">You then include this code file in your Visual Studio project.</span></span> <span data-ttu-id="64da5-129">자세한 내용은 [특성 기반 매핑](attribute-based-mapping.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64da5-129">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="64da5-130">외부 매핑을 위한 XML 파일</span><span class="sxs-lookup"><span data-stu-id="64da5-130">An XML file for external mapping.</span></span>  
  
     <span data-ttu-id="64da5-131">이 방법을 사용하면 애플리케이션 코드 외부에 매핑 메타데이터를 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-131">By using this approach, you can keep the mapping metadata out of your application code.</span></span> <span data-ttu-id="64da5-132">자세한 내용은 [외부 매핑](external-mapping.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64da5-132">For more information, see [External Mapping](external-mapping.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="64da5-133">O/R 디자이너는 외부 매핑 파일의 생성을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-133">The O/R Designer does not support the generation of external mapping files.</span></span> <span data-ttu-id="64da5-134">SQLMetal 도구를 사용하여 이 기능을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-134">You must use the SQLMetal tool to implement this feature.</span></span>  
  
- <span data-ttu-id="64da5-135">최종 코드 파일을 생성하기 전에 수정할 수 있는 DBML 파일</span><span class="sxs-lookup"><span data-stu-id="64da5-135">A DBML file, which you can modify before generating a final code file.</span></span>  
  
     <span data-ttu-id="64da5-136">이는 고급 기능에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-136">This is an advanced feature.</span></span>  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a><span data-ttu-id="64da5-137">3. 응용 프로그램의 요구를 반영 하도록 코드 파일을 구체화 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-137">3. Refine the code file to reflect the needs of your application.</span></span>  

 <span data-ttu-id="64da5-138">이러한 목적을 위해 O/R 디자이너 또는 코드 편집기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-138">For this purpose, you can use either the O/R Designer or the code editor.</span></span>  
  
## <a name="using-the-object-model"></a><span data-ttu-id="64da5-139">개체 모델 사용</span><span class="sxs-lookup"><span data-stu-id="64da5-139">Using the Object Model</span></span>  

 <span data-ttu-id="64da5-140">다음 그림에서는 2계층 시나리오에서 개발자와 데이터 간의 관계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-140">The following illustration shows the relationship between the developer and the data in a two-tier scenario.</span></span> <span data-ttu-id="64da5-141">다른 시나리오의 경우 [LINQ to SQL를 사용 하는 N 계층 및 원격 응용 프로그램](n-tier-and-remote-applications-with-linq-to-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64da5-141">For other scenarios, see [N-Tier and Remote Applications with LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md).</span></span>  
  
 ![Linq 개체 모델을 보여 주는 스크린샷](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 <span data-ttu-id="64da5-143">이제 개체 모델이 있으므로 해당 모델 내에서 정보 요청을 설명하고 데이터를 조작할 차례입니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-143">Now that you have the object model, you describe information requests and manipulate data within that model.</span></span> <span data-ttu-id="64da5-144">데이터베이스의 행과 열이 아니라 개체 모델의 개체와 속성을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-144">You think in terms of the objects and properties in your object model and not in terms of the rows and columns of the database.</span></span> <span data-ttu-id="64da5-145">데이터베이스를 직접 다루지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-145">You do not deal directly with the database.</span></span>  
  
 <span data-ttu-id="64da5-146">설명한 쿼리를 실행하거나 조작한 데이터에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]를 호출하도록 `SubmitChanges()`에 지시할 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 데이터베이스 언어로 데이터베이스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-146">When you instruct [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to either execute a query that you have described or call `SubmitChanges()` on data that you have manipulated, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] communicates with the database in the language of the database.</span></span>  
  
 <span data-ttu-id="64da5-147">만들어진 개체 모델을 사용하기 위한 일반적인 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-147">The following represents typical steps for using the object model that you have created.</span></span>  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a><span data-ttu-id="64da5-148">1. 데이터베이스에서 정보를 검색 하는 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-148">1. Create queries to retrieve information from the database.</span></span>  

 <span data-ttu-id="64da5-149">자세한 내용은 [쿼리 개념](query-concepts.md) 및 [쿼리 예제](query-examples.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64da5-149">For more information, see [Query Concepts](query-concepts.md) and [Query Examples](query-examples.md).</span></span>  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a><span data-ttu-id="64da5-150">2. Insert, Update 및 Delete의 기본 동작을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-150">2. Override default behaviors for Insert, Update, and Delete.</span></span>  

 <span data-ttu-id="64da5-151">이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-151">This step is optional.</span></span> <span data-ttu-id="64da5-152">자세한 내용은 [삽입, 업데이트 및 삭제 작업 사용자 지정](customizing-insert-update-and-delete-operations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64da5-152">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a><span data-ttu-id="64da5-153">3. 동시성 충돌을 검색 하 고 보고 하는 적절 한 옵션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-153">3. Set appropriate options to detect and report concurrency conflicts.</span></span>  

 <span data-ttu-id="64da5-154">모델에서 동시성 충돌을 처리하기 위한 기본값을 유지하거나 원하는 목적에 맞게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-154">You can leave your model with its default values for handling concurrency conflicts, or you can change it to suit your purposes.</span></span> <span data-ttu-id="64da5-155">자세한 내용은 [방법: 동시성 충돌에 테스트할 멤버 지정](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) 및 [방법: 동시성 예외가 Throw 되는 시기 지정](how-to-specify-when-concurrency-exceptions-are-thrown.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64da5-155">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) and [How to: Specify When Concurrency Exceptions are Thrown](how-to-specify-when-concurrency-exceptions-are-thrown.md).</span></span>  
  
### <a name="4-establish-an-inheritance-hierarchy"></a><span data-ttu-id="64da5-156">4. 상속 계층 구조를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-156">4. Establish an inheritance hierarchy.</span></span>  

 <span data-ttu-id="64da5-157">이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-157">This step is optional.</span></span> <span data-ttu-id="64da5-158">자세한 내용은 [상속 지원](inheritance-support.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64da5-158">For more information, see [Inheritance Support](inheritance-support.md).</span></span>  
  
### <a name="5-provide-an-appropriate-user-interface"></a><span data-ttu-id="64da5-159">5. 적절 한 사용자 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-159">5. Provide an appropriate user interface.</span></span>  

 <span data-ttu-id="64da5-160">이 단계는 선택 사항이며 애플리케이션이 사용될 방법에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-160">This step is optional, and depends on how your application will be used.</span></span>  
  
### <a name="6-debug-and-test-your-application"></a><span data-ttu-id="64da5-161">6. 응용 프로그램을 디버그 하 고 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="64da5-161">6. Debug and test your application.</span></span>  

 <span data-ttu-id="64da5-162">자세한 내용은 [디버깅 지원](debugging-support.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64da5-162">For more information, see [Debugging Support](debugging-support.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64da5-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64da5-163">See also</span></span>

- [<span data-ttu-id="64da5-164">시작</span><span class="sxs-lookup"><span data-stu-id="64da5-164">Getting Started</span></span>](getting-started.md)
- [<span data-ttu-id="64da5-165">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="64da5-165">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="64da5-166">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="64da5-166">Stored Procedures</span></span>](stored-procedures.md)
