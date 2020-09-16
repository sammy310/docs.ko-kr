---
title: '방법: 모델 및 매핑 파일을 포함 리소스로 만들기'
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: aaab2ccc96497cb718b868f7ac63995ad4ba35c8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546681"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a><span data-ttu-id="a58f4-102">방법: 모델 및 매핑 파일을 포함 리소스로 만들기</span><span class="sxs-lookup"><span data-stu-id="a58f4-102">How to: Make Model and Mapping Files Embedded Resources</span></span>
<span data-ttu-id="a58f4-103">Entity Framework를 사용 하면 모델 및 매핑 파일을 응용 프로그램의 포함 리소스로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a58f4-103">The Entity Framework enables you to deploy model and mapping files as embedded resources of an application.</span></span> <span data-ttu-id="a58f4-104">포함된 모델 및 매핑 파일이 있는 어셈블리는 엔터티 연결과 동일한 애플리케이션 도메인에 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f4-104">The assembly with the embedded model and mapping files must be loaded in the same application domain as the entity connection.</span></span> <span data-ttu-id="a58f4-105">자세한 내용은 [연결 문자열](connection-strings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a58f4-105">For more information, see [Connection Strings](connection-strings.md).</span></span> <span data-ttu-id="a58f4-106">기본적으로 엔터티 데이터 모델 도구는 모델 및 매핑 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f4-106">By default, the Entity Data Model tools embed the model and mapping files.</span></span> <span data-ttu-id="a58f4-107">모델 및 매핑 파일을 수동으로 정의 하는 경우이 절차를 사용 하 여 파일이 Entity Framework 응용 프로그램과 함께 포함 리소스로 배포 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f4-107">When you manually define the model and mapping files, use this procedure to ensure that the files are deployed as embedded resources together with an Entity Framework application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a58f4-108">포함 리소스를 유지하려면 모델 및 매핑 파일이 수정될 때마다 이 절차를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f4-108">To maintain embedded resources, you must repeat this procedure whenever the model and mapping files are modified.</span></span>  
  
### <a name="to-embed-model-and-mapping-files"></a><span data-ttu-id="a58f4-109">모델 및 매핑 파일을 포함하려면</span><span class="sxs-lookup"><span data-stu-id="a58f4-109">To embed model and mapping files</span></span>  
  
1. <span data-ttu-id="a58f4-110">**솔루션 탐색기**에서 개념 파일 (csdl)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f4-110">In **Solution Explorer**, select the conceptual (.csdl) file.</span></span>  
  
2. <span data-ttu-id="a58f4-111">**속성** 창에서 **빌드 작업** 을 **포함 리소스**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f4-111">In the **Properties** pane, set **Build Action** to **Embedded Resource**.</span></span>  
  
3. <span data-ttu-id="a58f4-112">스토리지 파일(.ssdl) 및 매핑 파일(.msl)에 대해 1단계와 2단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f4-112">Repeat steps 1 and 2 for the storage (.ssdl) file and the mapping (.msl) file.</span></span>  
  
4. <span data-ttu-id="a58f4-113">**솔루션 탐색기**에서 App.config 파일을 두 번 클릭 하 고 `Metadata` `connectionString` 다음 형식 중 하나를 기반으로 특성의 매개 변수를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f4-113">In **Solution Explorer**, double-click the App.config file and then modify the `Metadata` parameter in the `connectionString` attribute based on one of the following formats:</span></span>  
  
    - <span data-ttu-id="a58f4-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="a58f4-114">`Metadata=` `res://<assemblyFullName>/<resourceName>;`</span></span>  
  
    - <span data-ttu-id="a58f4-115">`Metadata=` `res://*/<resourceName>;`</span><span class="sxs-lookup"><span data-stu-id="a58f4-115">`Metadata=` `res://*/<resourceName>;`</span></span>  
  
    - `Metadata=res://*;`  
  
     <span data-ttu-id="a58f4-116">자세한 내용은 [연결 문자열](connection-strings.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a58f4-116">For more information, see [Connection Strings](connection-strings.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a58f4-117">예제</span><span class="sxs-lookup"><span data-stu-id="a58f4-117">Example</span></span>  
 <span data-ttu-id="a58f4-118">다음 연결 문자열은 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)에 대 한 포함 된 모델 및 매핑 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a58f4-118">The following connection string references embedded model and mapping files for the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="a58f4-119">이 연결 문자열은 프로젝트의 App.config 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a58f4-119">This connection string is stored in the project's App.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a58f4-120">참조</span><span class="sxs-lookup"><span data-stu-id="a58f4-120">See also</span></span>

- [<span data-ttu-id="a58f4-121">모델링 및 매핑</span><span class="sxs-lookup"><span data-stu-id="a58f4-121">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- [<span data-ttu-id="a58f4-122">방법: 연결 문자열 정의</span><span class="sxs-lookup"><span data-stu-id="a58f4-122">How to: Define the Connection String</span></span>](how-to-define-the-connection-string.md)
- [<span data-ttu-id="a58f4-123">방법: EntityConnection 연결 문자열 빌드</span><span class="sxs-lookup"><span data-stu-id="a58f4-123">How to: Build an EntityConnection Connection String</span></span>](how-to-build-an-entityconnection-connection-string.md)
- <span data-ttu-id="a58f4-124">[ADO.NET 엔터티 데이터 모델 도구](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a58f4-124">[ADO.NET Entity Data Model Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
