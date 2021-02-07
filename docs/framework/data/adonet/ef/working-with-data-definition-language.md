---
description: '자세한 정보: 데이터 정의 언어 작업'
title: 데이터 정의 언어로 작업
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
ms.openlocfilehash: 2f924087d12b519e6086289a91dedce3a88199f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673026"
---
# <a name="working-with-data-definition-language"></a><span data-ttu-id="bb9fe-103">데이터 정의 언어로 작업</span><span class="sxs-lookup"><span data-stu-id="bb9fe-103">Working with Data Definition Language</span></span>

<span data-ttu-id="bb9fe-104">.NET Framework 버전 4부터 Entity Framework은 DDL (데이터 정의 언어)을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-104">Starting with the .NET Framework version 4, the Entity Framework supports data definition language (DDL).</span></span> <span data-ttu-id="bb9fe-105">이렇게 하면 연결 문자열 및 스토리지(SSDL) 모델의 메타데이터를 기반으로 데이터베이스 인스턴스를 만들거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-105">This allows you to create or delete a database instance based on the connection string and the metadata of the storage (SSDL) model.</span></span>  
  
 <span data-ttu-id="bb9fe-106"><xref:System.Data.Objects.ObjectContext>의 다음 메서드는 연결 문자열과 SSDL 콘텐츠를 사용하여 데이터베이스를 만들거나 삭제하고, 데이터베이스가 있는지 확인하며, 생성된 DDL 스크립트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-106">The following methods on the <xref:System.Data.Objects.ObjectContext> use the connection string and the SSDL content to accomplish the following: create or delete the database, check whether the database exists, and view the generated DDL script:</span></span>  
  
- <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
- <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
- <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
- <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
> <span data-ttu-id="bb9fe-107">DDL 명령을 실행하려면 충분한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-107">Executing the DDL commands assumes sufficient permissions.</span></span>  
  
 <span data-ttu-id="bb9fe-108">위에 나열된 메서드는 대부분의 작업을 기본 ADO.NET 데이터 공급자에 위임합니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-108">The methods previously listed delegate most of the work to the underlying ADO.NET data provider.</span></span> <span data-ttu-id="bb9fe-109">데이터베이스 개체를 생성하는 데 사용되는 명명 규칙이 쿼리 및 업데이트에 사용되는 규칙과 일치하는지 확인하는 것은 공급자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-109">It is the provider’s responsibility to ensure that the naming convention used to generate database objects is consistent with conventions used for querying and updates.</span></span>  
  
 <span data-ttu-id="bb9fe-110">다음 예제에서는 기존 모델을 기반으로 데이터베이스를 생성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-110">The following example shows you how to generate the database based on the existing model.</span></span> <span data-ttu-id="bb9fe-111">또한 새 엔터티 개체를 개체 컨텍스트에 추가한 다음 데이터베이스에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-111">It also adds a new entity object to the object context and then saves it to the database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="bb9fe-112">프로시저</span><span class="sxs-lookup"><span data-stu-id="bb9fe-112">Procedures</span></span>  
  
### <a name="to-define-a-database-based-on-the-existing-model"></a><span data-ttu-id="bb9fe-113">기존 모델을 기반으로 데이터베이스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="bb9fe-113">To define a database based on the existing model</span></span>  
  
1. <span data-ttu-id="bb9fe-114">콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-114">Create a console application.</span></span>  
  
2. <span data-ttu-id="bb9fe-115">애플리케이션에 기존 모델을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-115">Add an existing model to your application.</span></span>  
  
    1. <span data-ttu-id="bb9fe-116">이라는 빈 모델을 추가 `SchoolModel` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-116">Add an empty model named `SchoolModel`.</span></span> <span data-ttu-id="bb9fe-117">빈 모델을 만들려면 [방법: 새 .Edmx 파일 만들기](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100)) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-117">To create an empty model, see the [How to: Create a New .edmx File](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100)) topic.</span></span>  
  
     <span data-ttu-id="bb9fe-118">SchoolModel.edmx 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-118">The SchoolModel.edmx file is added to your project.</span></span>  
  
    1. <span data-ttu-id="bb9fe-119">[School](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) 모델 토픽에서 school 모델에 대 한 개념, 저장소 및 매핑 콘텐츠를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-119">Copy the conceptual, storage, and mapping content for the School model from the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) topic.</span></span>  
  
    2. <span data-ttu-id="bb9fe-120">SchoolModel.edmx 파일을 열고 콘텐츠를 `edmx:Runtime` 태그 안에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-120">Open the SchoolModel.edmx file and paste the content within the `edmx:Runtime` tags.</span></span>  
  
3. <span data-ttu-id="bb9fe-121">다음 코드를 main 함수에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-121">Add the following code to your main function.</span></span> <span data-ttu-id="bb9fe-122">이 코드에서는 데이터베이스 서버에 대한 연결 문자열을 초기화하고 DDL 스크립트를 확인하며, 데이터베이스를 만들고 새 엔터티를 컨텍스트에 추가한 다음 변경 내용을 데이터베이스에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bb9fe-122">The code initializes the connection string to your database server, views the DDL script, creates the database, adds a new entity to the context, and saves the changes to the database.</span></span>  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
