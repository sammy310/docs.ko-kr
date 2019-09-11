---
title: Entity Framework 데이터 공급자 작성
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 29aa8cb1c6b31d9ada6b01860d76bcf03d37416c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854168"
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="789ff-102">Entity Framework 데이터 공급자 작성</span><span class="sxs-lookup"><span data-stu-id="789ff-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="789ff-103">이 섹션에서는 SQL Server 이외의 데이터 원본을 지원 하기 위해 Entity Framework 공급자를 작성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="789ff-103">This section discusses how to write an Entity Framework provider to support a data source other than SQL Server.</span></span> <span data-ttu-id="789ff-104">Entity Framework에는 SQL Server를 지 원하는 공급자가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="789ff-104">The Entity Framework includes a provider that supports SQL Server.</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="789ff-105">Entity Framework 공급자 모델 소개</span><span class="sxs-lookup"><span data-stu-id="789ff-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="789ff-106">Entity Framework는 데이터베이스 독립적 이며, ADO.NET 공급자 모델을 사용 하 여 다양 한 데이터 원본 집합에 연결 하 여 공급자를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="789ff-106">The Entity Framework is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="789ff-107">Entity Framework 데이터 공급자(ADO.NET 데이터 공급자 모델을 사용하여 작성됨)는 다음과 같은 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="789ff-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
- <span data-ttu-id="789ff-108">EDM(엔터티 데이터 모델) 기본 형식을 공급자 형식에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="789ff-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
- <span data-ttu-id="789ff-109">공급자별 함수를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="789ff-109">Exposes provider-specific functions.</span></span>  
  
- <span data-ttu-id="789ff-110">지정 된 DbQueryCommandTree에 대 한 공급자별 명령을 생성 하 Entity Framework 쿼리를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="789ff-110">Generates provider-specific commands for a given DbQueryCommandTree to support Entity Framework queries.</span></span>  
  
- <span data-ttu-id="789ff-111">Entity Framework를 통한 업데이트를 지원 하기 위해 지정 된 DbModificationCommandTree에 대 한 공급자별 업데이트 명령을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="789ff-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the Entity Framework.</span></span>  
  
- <span data-ttu-id="789ff-112">데이터베이스 기반의 모델 생성을 지원하기 위해 저장소 스키마 정의에 대한 매핑 파일을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="789ff-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
- <span data-ttu-id="789ff-113">개념적 모델을 통해 메타데이터(예: 테이블 및 뷰)를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="789ff-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="789ff-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="789ff-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="789ff-115">예제</span><span class="sxs-lookup"><span data-stu-id="789ff-115">Sample</span></span>  
 <span data-ttu-id="789ff-116">SQL Server 이외의 데이터 원본을 지 원하는 Entity Framework 공급자에 대 한 샘플은 [Entity Framework 샘플 공급자](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="789ff-116">See the [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) for a sample of an Entity Framework provider that supports a data source other than SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="789ff-117">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="789ff-117">In This Section</span></span>  
 [<span data-ttu-id="789ff-118">SQL 생성</span><span class="sxs-lookup"><span data-stu-id="789ff-118">SQL Generation</span></span>](sql-generation.md)  
  
 [<span data-ttu-id="789ff-119">수정 SQL 생성</span><span class="sxs-lookup"><span data-stu-id="789ff-119">Modification SQL Generation</span></span>](modification-sql-generation.md)  
  
 [<span data-ttu-id="789ff-120">공급자 매니페스트 지정</span><span class="sxs-lookup"><span data-stu-id="789ff-120">Provider Manifest Specification</span></span>](provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="789ff-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="789ff-121">See also</span></span>

- [<span data-ttu-id="789ff-122">데이터 공급자 작업</span><span class="sxs-lookup"><span data-stu-id="789ff-122">Working with Data Providers</span></span>](working-with-data-providers.md)
