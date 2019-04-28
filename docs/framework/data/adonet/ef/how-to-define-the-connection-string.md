---
title: '방법: 연결 문자열 정의'
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 7fb722acbb13b3502d004978581701cc70118ff8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606106"
---
# <a name="how-to-define-the-connection-string"></a><span data-ttu-id="8528e-102">방법: 연결 문자열 정의</span><span class="sxs-lookup"><span data-stu-id="8528e-102">How to: Define the Connection String</span></span>

<span data-ttu-id="8528e-103">이 항목에서는 개념적 모델에 연결할 때 사용하는 연결 문자열을 정의하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8528e-103">This topic shows how to define the connection string that is used when connecting to a conceptual model.</span></span> <span data-ttu-id="8528e-104">이 항목에 기반 합니다 [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) 개념적 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="8528e-104">This topic is based on the [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) conceptual model.</span></span> <span data-ttu-id="8528e-105">AdventureWorks Sales 모델은 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 문서의 작업 관련 항목 전체에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8528e-105">The AdventureWorks Sales Model is used throughout the task-related topics in the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] documentation.</span></span> <span data-ttu-id="8528e-106">이 항목에서는 이미 구성한 가정는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] AdventureWorks Sales 모델을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8528e-106">This topic assumes that you have already configured the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and defined the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8528e-107">자세한 내용은 [방법: 수동으로 모델을 정의 및 매핑 파일](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="8528e-107">For more information, see [How to: Manually Define the Model and Mapping Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).</span></span> <span data-ttu-id="8528e-108">이 항목의에서 절차에 에서도 나와 [방법: Entity Framework 프로젝트 수동 구성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="8528e-108">The procedures in this topic are also included in [How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="8528e-109">사용 하는 경우는 [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] 마법사는 Visual Studio 프로젝트에 자동으로.edmx 파일을 생성 하 고 사용 하도록 프로젝트를 구성 합니다 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8528e-109">If you use the [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] Wizard in a Visual Studio project, it automatically generates an .edmx file and configures the project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="8528e-110">자세한 내용은 [방법: 엔터티 데이터 모델 마법사 사용](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8528e-110">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))</span></span>

## <a name="to-define-the-entity-framework-connection-string"></a><span data-ttu-id="8528e-111">Entity Framework 연결 문자열을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="8528e-111">To define the Entity Framework connection string</span></span>

- <span data-ttu-id="8528e-112">프로젝트의 응용 프로그램 구성 파일(app.config)을 열고 다음 연결 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8528e-112">Open the project's application configuration file (app.config) and add the following connection string:</span></span>

```xml
<connectionStrings>
    <add name="AdventureWorksEntities" 
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

<span data-ttu-id="8528e-113">프로젝트에 응용 프로그램 구성 파일을 선택 하 여 하나를 추가할 수 있습니다 **새 항목 추가** 에서 합니다 **프로젝트** 메뉴에서 선택 하는 **일반** 범주 선택 **응용 프로그램 구성 파일**를 클릭 한 다음 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="8528e-113">If your project does not have an application configuration file, you can add one by selecting **Add New Item** from the **Project** menu, selecting the **General** category, selecting **Application Configuration File**, and then clicking **Add**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8528e-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="8528e-114">See also</span></span>

- <span data-ttu-id="8528e-115">[빠른 시작](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8528e-115">[Quickstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))</span></span>
- <span data-ttu-id="8528e-116">[방법: 새.edmx 파일 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8528e-116">[How to: Create a New .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))</span></span>
- <span data-ttu-id="8528e-117">[ADO.NET 엔터티 데이터 모델 도구](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8528e-117">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
