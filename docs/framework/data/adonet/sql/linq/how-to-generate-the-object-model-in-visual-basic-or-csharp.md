---
title: '방법: Visual Basic 또는 C#에서 개체 모델 생성'
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: e2491cf18be556cb26f084a178b7bf09448c6904
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546616"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="912d6-102">방법: Visual Basic 또는 C에서 개체 모델 생성\#</span><span class="sxs-lookup"><span data-stu-id="912d6-102">How to: Generate the Object Model in Visual Basic or C\#</span></span>
<span data-ttu-id="912d6-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 사용자 프로그래밍 언어의 개체 모델은 관계형 데이터베이스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="912d6-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="912d6-104">기존 데이터베이스의 메타 데이터에서 Visual Basic 또는 c # 모델을 자동으로 생성 하는 데는 두 가지 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="912d6-104">Two tools are available for automatically generating a Visual Basic or C# model from the metadata of an existing database.</span></span>  
  
- <span data-ttu-id="912d6-105">Visual Studio를 사용 하는 경우 개체 관계형 디자이너를 사용 하 여 개체 모델을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="912d6-105">If you are using Visual Studio, you can use the Object Relational Designer to generate an object model.</span></span> <span data-ttu-id="912d6-106">O/R 디자이너는 개체 모델을 생성 하는 데 도움이 되는 다양 한 사용자 인터페이스를 제공 합니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="912d6-106">The O/R Designer provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="912d6-107">자세한 내용은 [Visual Studio의 Linq TO SQL 도구](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="912d6-107">For more information see, [Linq to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
- <span data-ttu-id="912d6-108">SQLMetal 명령줄 도구.</span><span class="sxs-lookup"><span data-stu-id="912d6-108">The SQLMetal command-line tool.</span></span> <span data-ttu-id="912d6-109">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="912d6-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="912d6-110">기존 데이터베이스가 없는 경우 개체 모델에서 데이터베이스를 만들려면 코드 편집기와 <xref:System.Data.Linq.DataContext.CreateDatabase%2A>를 사용하여 개체 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="912d6-110">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="912d6-111">자세한 내용은 [방법: 동적으로 데이터베이스 만들기](how-to-dynamically-create-a-database.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="912d6-111">For more information, see [How to: Dynamically Create a Database](how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="912d6-112">O/R 디자이너에 대 한 설명서는 O/R 디자이너를 사용 하 여 Visual Basic 또는 c # 개체 모델을 생성 하는 방법에 대 한 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="912d6-112">Documentation for the O/R Designer provides examples of how to generate a Visual Basic or C# object model by using the O/R Designer.</span></span> <span data-ttu-id="912d6-113">다음 정보에서는 SQLMetal 명령줄 도구를 사용하는 방법에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="912d6-113">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="912d6-114">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="912d6-114">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="912d6-115">예제</span><span class="sxs-lookup"><span data-stu-id="912d6-115">Example</span></span>  
 <span data-ttu-id="912d6-116">다음 예제의 SQLMetal 명령줄에서는 Northwind 샘플 데이터베이스의 특성 기반 개체 모델 Visual Basic 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="912d6-116">The SQLMetal command line shown in the following example produces Visual Basic code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="912d6-117">또한 저장 프로시저와 함수가 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="912d6-117">Stored procedures and functions are also rendered.</span></span>  
  
```console  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="912d6-118">예제</span><span class="sxs-lookup"><span data-stu-id="912d6-118">Example</span></span>  
 <span data-ttu-id="912d6-119">다음 예제의 SQLMetal 명령줄에서는 Northwind 샘플 데이터베이스의 특성 기반 개체 모델과 같은 C# 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="912d6-119">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="912d6-120">또한 저장 프로시저와 함수가 렌더링되며 테이블 이름은 자동으로 복수화됩니다.</span><span class="sxs-lookup"><span data-stu-id="912d6-120">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```console  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="912d6-121">참조</span><span class="sxs-lookup"><span data-stu-id="912d6-121">See also</span></span>

- [<span data-ttu-id="912d6-122">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="912d6-122">Programming Guide</span></span>](programming-guide.md)
- [<span data-ttu-id="912d6-123">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="912d6-123">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="912d6-124">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="912d6-124">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
- [<span data-ttu-id="912d6-125">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="912d6-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [<span data-ttu-id="912d6-126">특성 기반 매핑</span><span class="sxs-lookup"><span data-stu-id="912d6-126">Attribute-Based Mapping</span></span>](attribute-based-mapping.md)
- [<span data-ttu-id="912d6-127">SqlMetal.exe(코드 생성 도구)</span><span class="sxs-lookup"><span data-stu-id="912d6-127">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="912d6-128">외부 매핑</span><span class="sxs-lookup"><span data-stu-id="912d6-128">External Mapping</span></span>](external-mapping.md)
- [<span data-ttu-id="912d6-129">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="912d6-129">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="912d6-130">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="912d6-130">Creating the Object Model</span></span>](creating-the-object-model.md)
