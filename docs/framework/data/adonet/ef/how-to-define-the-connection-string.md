---
description: '자세한 정보: 방법: 연결 문자열 정의'
title: '방법: 연결 문자열 정의'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 104264299e597bc142a689aa83f3207765d18c67
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650822"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="d3039-103">방법: 연결 문자열 정의</span><span class="sxs-lookup"><span data-stu-id="d3039-103">How to: Define the Connection String</span></span>

<span data-ttu-id="d3039-104">이 항목에서는 개념적 모델에 연결할 때 사용하는 연결 문자열을 정의하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3039-104">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="d3039-105">이 항목은 [AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) 개념적 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3039-105">This topic is based on the [AdventureWorks Sales](/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="d3039-106">AdventureWorks Sales 모델은 Entity Framework 설명서의 작업 관련 항목 전체에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3039-106">The AdventureWorks Sales Model is used throughout the task-related topics in the Entity Framework documentation.</span></span> <span data-ttu-id="d3039-107">이 항목에서는 Entity Framework 이미 구성 되었으며 AdventureWorks Sales 모델을 정의한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3039-107">This topic assumes that you have already configured the Entity Framework and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d3039-108">자세한 내용은 [방법: 수동으로 모델 및 매핑 파일 정의](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3039-108">For more information, see [How to: Manually Define the Model and Mapping Files](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="d3039-109">이 항목의 절차는 [방법: Entity Framework 프로젝트 수동 구성](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))에도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3039-109">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="d3039-110">Visual Studio 프로젝트에서 엔터티 데이터 모델 마법사를 사용 하는 경우 자동으로 .edmx 파일이 생성 되 고 Entity Framework을 사용 하도록 프로젝트가 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3039-110">If you use the Entity Data Model Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the Entity Framework.</span></span> <span data-ttu-id="d3039-111">자세한 내용은 [방법: 엔터티 데이터 모델 마법사 사용](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3039-111">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="d3039-112">Entity Framework 연결 문자열을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="d3039-112">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="d3039-113">프로젝트의 애플리케이션 구성 파일(app.config)을 열고 다음 연결 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3039-113">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities"
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="d3039-114">프로젝트에 응용 프로그램 구성 파일이 없는 경우 **프로젝트** 메뉴에서 **새 항목 추가** 를 선택 하 고 **일반** 범주를 선택한 다음 **응용 프로그램 구성 파일** 을 선택 하 고 **추가** 를 클릭 하 여 프로젝트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3039-114">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3039-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3039-115">See also</span></span>

- <span data-ttu-id="d3039-116">[빠른 시작](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d3039-116">[Quickstart](/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="d3039-117">[방법: 새 .edmx 파일 만들기](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d3039-117">[How to: Create a New .edmx File](/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="d3039-118">[ADO.NET 엔터티 데이터 모델 도구](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d3039-118">[ADO.NET Entity Data Model  Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
