---
description: '자세히 알아보기: 방법: 데이터 서비스 참조 추가 (WCF Data Services)'
title: '방법: 데이터 서비스 참조 추가(WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 907ad9a7dc3710a6e565de55c74a0d279d20e159
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765753"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="67d23-103">방법: 데이터 서비스 참조 추가 (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="67d23-103">How to: Add a data service reference (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="67d23-104">Visual Studio의 **서비스 참조 추가** 대화 상자를 사용 하 여 WCF Data Services에 대 한 참조를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d23-104">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to WCF Data Services.</span></span> <span data-ttu-id="67d23-105">이렇게 하면 Visual Studio에서 개발하는 클라이언트 애플리케이션에서 데이터 서비스에 보다 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67d23-105">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="67d23-106">이 절차를 완료하면 데이터 서비스에서 가져온 메타데이터를 기준으로 데이터 클래스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d23-106">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="67d23-107">자세한 내용은 [데이터 서비스 클라이언트 라이브러리 생성](generating-the-data-service-client-library-wcf-data-services.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67d23-107">For more information, see [Generating the Data Service Client Library](generating-the-data-service-client-library-wcf-data-services.md).</span></span>

## <a name="add-a-data-service-reference"></a><span data-ttu-id="67d23-108">데이터 서비스 참조 추가</span><span class="sxs-lookup"><span data-stu-id="67d23-108">Add a data service reference</span></span>

1. <span data-ttu-id="67d23-109">(선택 사항) 데이터 서비스가 솔루션에 포함되어 있지 않고 실행 중이 아닌 경우 데이터 서비스를 시작하고 데이터 서비스의 URI를 적어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="67d23-109">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>

2. <span data-ttu-id="67d23-110">Visual Studio의 **솔루션 탐색기** 에서 클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음   >  **서비스 참조** 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d23-110">In Visual Studio, in **Solution Explorer**, right-click the client project and then select **Add** > **Service Reference**.</span></span>

3. <span data-ttu-id="67d23-111">데이터 서비스가 현재 솔루션의 일부인 경우 **검색** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d23-111">If the data service is part of the current solution, click **Discover**.</span></span>

     <span data-ttu-id="67d23-112">또는</span><span class="sxs-lookup"><span data-stu-id="67d23-112">-or-</span></span>

     <span data-ttu-id="67d23-113">**주소** 텍스트 상자에 데이터 서비스의 기본 URL (예:)을 입력 한 `http://localhost:1234/Northwind.svc` 다음 **이동** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="67d23-113">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>

4. <span data-ttu-id="67d23-114">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67d23-114">Select **OK**.</span></span>

     <span data-ttu-id="67d23-115">데이터 서비스 리소스에 액세스 하 고 상호 작용할 수 있는 데이터 클래스가 포함 된 새 코드 파일이 프로젝트에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67d23-115">A new code file that contains the data classes that can access and interact with data service resources is added to the project.</span></span>

## <a name="see-also"></a><span data-ttu-id="67d23-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67d23-116">See also</span></span>

- [<span data-ttu-id="67d23-117">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="67d23-117">Quickstart</span></span>](quickstart-wcf-data-services.md)
