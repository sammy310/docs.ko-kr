---
description: '자세한 정보: 방법: 개체 모델 생성 Visual Basic 또는 C #'
title: '방법: Visual Basic 또는 C#에서 개체 모델 생성'
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: d842a646f9f6186d252d10297618ddc2cb137e70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785967"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="2cf0a-103">방법: Visual Basic 또는 C에서 개체 모델 생성\#</span><span class="sxs-lookup"><span data-stu-id="2cf0a-103">How to: Generate the Object Model in Visual Basic or C\#</span></span>

<span data-ttu-id="2cf0a-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 사용자 프로그래밍 언어의 개체 모델은 관계형 데이터베이스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-104">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="2cf0a-105">기존 데이터베이스의 메타 데이터에서 Visual Basic 또는 c # 모델을 자동으로 생성 하는 데는 두 가지 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-105">Two tools are available for automatically generating a Visual Basic or C# model from the metadata of an existing database.</span></span>  
  
- <span data-ttu-id="2cf0a-106">Visual Studio를 사용 하는 경우 개체 관계형 디자이너를 사용 하 여 개체 모델을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-106">If you are using Visual Studio, you can use the Object Relational Designer to generate an object model.</span></span> <span data-ttu-id="2cf0a-107">O/R 디자이너는 개체 모델을 생성 하는 데 도움이 되는 다양 한 사용자 인터페이스를 제공 합니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cf0a-107">The O/R Designer provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="2cf0a-108">자세한 내용은 [Visual Studio의 Linq TO SQL 도구](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-108">For more information see, [Linq to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
- <span data-ttu-id="2cf0a-109">SQLMetal 명령줄 도구.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-109">The SQLMetal command-line tool.</span></span> <span data-ttu-id="2cf0a-110">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-110">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2cf0a-111">기존 데이터베이스가 없는 경우 개체 모델에서 데이터베이스를 만들려면 코드 편집기와 <xref:System.Data.Linq.DataContext.CreateDatabase%2A>를 사용하여 개체 모델을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-111">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="2cf0a-112">자세한 내용은 [방법: 동적으로 데이터베이스 만들기](how-to-dynamically-create-a-database.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-112">For more information, see [How to: Dynamically Create a Database](how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="2cf0a-113">O/R 디자이너에 대 한 설명서는 O/R 디자이너를 사용 하 여 Visual Basic 또는 c # 개체 모델을 생성 하는 방법에 대 한 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-113">Documentation for the O/R Designer provides examples of how to generate a Visual Basic or C# object model by using the O/R Designer.</span></span> <span data-ttu-id="2cf0a-114">다음 정보에서는 SQLMetal 명령줄 도구를 사용하는 방법에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-114">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="2cf0a-115">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-115">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cf0a-116">예제</span><span class="sxs-lookup"><span data-stu-id="2cf0a-116">Example</span></span>  

 <span data-ttu-id="2cf0a-117">다음 예제의 SQLMetal 명령줄에서는 Northwind 샘플 데이터베이스의 특성 기반 개체 모델 Visual Basic 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-117">The SQLMetal command line shown in the following example produces Visual Basic code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="2cf0a-118">또한 저장 프로시저와 함수가 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-118">Stored procedures and functions are also rendered.</span></span>  
  
```console  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="2cf0a-119">예제</span><span class="sxs-lookup"><span data-stu-id="2cf0a-119">Example</span></span>  

 <span data-ttu-id="2cf0a-120">다음 예제의 SQLMetal 명령줄에서는 Northwind 샘플 데이터베이스의 특성 기반 개체 모델과 같은 C# 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-120">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="2cf0a-121">또한 저장 프로시저와 함수가 렌더링되며 테이블 이름은 자동으로 복수화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf0a-121">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```console  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cf0a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cf0a-122">See also</span></span>

- [<span data-ttu-id="2cf0a-123">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="2cf0a-123">Programming Guide</span></span>](programming-guide.md)
- [<span data-ttu-id="2cf0a-124">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="2cf0a-124">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="2cf0a-125">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="2cf0a-125">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
- [<span data-ttu-id="2cf0a-126">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2cf0a-126">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [<span data-ttu-id="2cf0a-127">특성 기반 매핑</span><span class="sxs-lookup"><span data-stu-id="2cf0a-127">Attribute-Based Mapping</span></span>](attribute-based-mapping.md)
- [<span data-ttu-id="2cf0a-128">SqlMetal.exe(코드 생성 도구)</span><span class="sxs-lookup"><span data-stu-id="2cf0a-128">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="2cf0a-129">외부 매핑</span><span class="sxs-lookup"><span data-stu-id="2cf0a-129">External Mapping</span></span>](external-mapping.md)
- [<span data-ttu-id="2cf0a-130">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="2cf0a-130">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="2cf0a-131">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="2cf0a-131">Creating the Object Model</span></span>](creating-the-object-model.md)
