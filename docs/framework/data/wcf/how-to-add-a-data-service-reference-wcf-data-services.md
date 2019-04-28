---
title: '방법: (WCF Data Services)는 데이터 서비스 참조 추가'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: fc1786e1c6102c702374989253cd3ce23e3f7b54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765533"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a><span data-ttu-id="a73a4-102">방법: (WCF Data Services)는 데이터 서비스 참조 추가</span><span class="sxs-lookup"><span data-stu-id="a73a4-102">How to: Add a data service reference (WCF Data Services)</span></span>

<span data-ttu-id="a73a4-103">사용할 수는 **서비스 참조 추가** WCF Data Services에 대 한 참조를 추가 하려면 Visual Studio에서 대화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a73a4-103">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to WCF Data Services.</span></span> <span data-ttu-id="a73a4-104">이렇게 하면 Visual Studio에서 개발하는 클라이언트 응용 프로그램에서 데이터 서비스에 보다 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a73a4-104">This enables you to more easily access a data service in a client application that you develop in Visual Studio.</span></span> <span data-ttu-id="a73a4-105">이 절차를 완료하면 데이터 서비스에서 가져온 메타데이터를 기준으로 데이터 클래스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a73a4-105">When you complete this procedure, data classes are generated based on metadata that is obtained from the data service.</span></span> <span data-ttu-id="a73a4-106">자세한 내용은 [데이터 서비스 클라이언트 라이브러리 생성](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a73a4-106">For more information, see [Generating the Data Service Client Library](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).</span></span>

## <a name="add-a-data-service-reference"></a><span data-ttu-id="a73a4-107">데이터 서비스 참조 추가</span><span class="sxs-lookup"><span data-stu-id="a73a4-107">Add a data service reference</span></span>

1. <span data-ttu-id="a73a4-108">(선택 사항) 데이터 서비스가 솔루션에 포함되어 있지 않고 실행 중이 아닌 경우 데이터 서비스를 시작하고 데이터 서비스의 URI를 적어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="a73a4-108">(Optional) If the data service is not part of the solution and is not already running, start the data service and note the URI of the data service.</span></span>

2. <span data-ttu-id="a73a4-109">Visual Studio에서의 **솔루션 탐색기**를 클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 선택 **추가** > **서비스 참조**합니다.</span><span class="sxs-lookup"><span data-stu-id="a73a4-109">In Visual Studio, in **Solution Explorer**, right-click the client project and then select **Add** > **Service Reference**.</span></span>

3. <span data-ttu-id="a73a4-110">데이터 서비스는 현재 솔루션의 일부 이면 클릭 **Discover**합니다.</span><span class="sxs-lookup"><span data-stu-id="a73a4-110">If the data service is part of the current solution, click **Discover**.</span></span>

     <span data-ttu-id="a73a4-111">또는</span><span class="sxs-lookup"><span data-stu-id="a73a4-111">-or-</span></span>

     <span data-ttu-id="a73a4-112">에 **주소** 텍스트 상자에 입력 데이터 서비스의 기본 URL 같은 `http://localhost:1234/Northwind.svc`를 클릭 하 고 **이동**합니다.</span><span class="sxs-lookup"><span data-stu-id="a73a4-112">In the **Address** text box, type the base URL of the data service, such as `http://localhost:1234/Northwind.svc`, and then click **Go**.</span></span>

4. <span data-ttu-id="a73a4-113">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a73a4-113">Select **OK**.</span></span>

     <span data-ttu-id="a73a4-114">에 액세스 하 고 데이터 서비스 리소스와 상호 작용할 수 있는 데이터 클래스를 포함 하는 새 코드 파일을 프로젝트에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a73a4-114">A new code file that contains the data classes that can access and interact with data service resources is added to the project.</span></span>

## <a name="see-also"></a><span data-ttu-id="a73a4-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="a73a4-115">See also</span></span>

- [<span data-ttu-id="a73a4-116">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="a73a4-116">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)