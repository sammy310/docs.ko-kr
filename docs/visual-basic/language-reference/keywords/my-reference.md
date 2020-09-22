---
title: My 참조
ms.date: 07/20/2015
helpviewer_keywords:
- My feature
- My reference
ms.assetid: 6f803bd7-21ff-4569-b1fe-b00a6678b1e3
ms.openlocfilehash: 60dadc2918d4926c2b8bf1004a09d9b3a1ec56ab
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875580"
---
# <a name="my-reference-visual-basic"></a><span data-ttu-id="9ff90-102">My 참조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ff90-102">My Reference (Visual Basic)</span></span>

<span data-ttu-id="9ff90-103">`My`이 기능을 사용 하면 일반적으로 사용 되는 메서드, 속성 및 이벤트에 대 한 직관적인 액세스를 제공 하 여 더 빠르고 쉽게 프로그래밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-103">The `My` feature makes programming faster and easier by giving you intuitive access to commonly used methods, properties, and events.</span></span> <span data-ttu-id="9ff90-104">다음 표에서는에 포함 된 개체 `My` 와 각 개체에서 수행할 수 있는 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-104">This table lists the objects contained in `My`, and the actions that can be performed with each.</span></span>  
  
|<span data-ttu-id="9ff90-105">**동작**</span><span class="sxs-lookup"><span data-stu-id="9ff90-105">**Action**</span></span>|<span data-ttu-id="9ff90-106">**Object**</span><span class="sxs-lookup"><span data-stu-id="9ff90-106">**Object**</span></span>|  
|----------------|----------------|  
|<span data-ttu-id="9ff90-107">응용 프로그램 정보 및 서비스에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-107">Accessing application information and services.</span></span>|<span data-ttu-id="9ff90-108">`My.Application` 개체는 다음 클래스로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-108">The `My.Application` object consists of the following classes:</span></span><br /><br /> <span data-ttu-id="9ff90-109"><xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>는 모든 프로젝트에서 사용 가능한 멤버를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-109"><xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> provides members that are available in all projects.</span></span><br /><br /> <span data-ttu-id="9ff90-110"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>는 Windows Forms 애플리케이션에서 사용 가능한 멤버를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-110"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> provides members available in Windows Forms applications.</span></span><br /><br /> <span data-ttu-id="9ff90-111"><xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase>는 콘솔 애플리케이션에서 사용 가능한 멤버를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-111"><xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> provides members available in console applications.</span></span>|  
|<span data-ttu-id="9ff90-112">호스트 컴퓨터 및 해당 리소스, 서비스 및 데이터에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-112">Accessing the host computer and its resources, services, and data.</span></span>|<span data-ttu-id="9ff90-113">`My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>)</span><span class="sxs-lookup"><span data-stu-id="9ff90-113">`My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>)</span></span>|  
|<span data-ttu-id="9ff90-114">현재 프로젝트의 폼에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-114">Accessing the forms in the current project.</span></span>|[<span data-ttu-id="9ff90-115">My.Forms 개체</span><span class="sxs-lookup"><span data-stu-id="9ff90-115">My.Forms Object</span></span>](../objects/my-forms-object.md)|  
|<span data-ttu-id="9ff90-116">응용 프로그램 로그에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-116">Accessing the application log.</span></span>|<span data-ttu-id="9ff90-117">`My.Application.Log` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>)</span><span class="sxs-lookup"><span data-stu-id="9ff90-117">`My.Application.Log` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>)</span></span>|  
|<span data-ttu-id="9ff90-118">현재 웹 요청에 액세스 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-118">Accessing the current web request.</span></span>|[<span data-ttu-id="9ff90-119">My.Request 개체</span><span class="sxs-lookup"><span data-stu-id="9ff90-119">My.Request Object</span></span>](../objects/my-request-object.md)|  
|<span data-ttu-id="9ff90-120">리소스 요소에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-120">Accessing resource elements.</span></span>|[<span data-ttu-id="9ff90-121">My.Resources 개체</span><span class="sxs-lookup"><span data-stu-id="9ff90-121">My.Resources Object</span></span>](../objects/my-resources-object.md)|  
|<span data-ttu-id="9ff90-122">현재 웹 응답에 액세스 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-122">Accessing the current web response.</span></span>|[<span data-ttu-id="9ff90-123">My.Response 개체</span><span class="sxs-lookup"><span data-stu-id="9ff90-123">My.Response Object</span></span>](../objects/my-response-object.md)|  
|<span data-ttu-id="9ff90-124">사용자 및 응용 프로그램 수준 설정에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-124">Accessing user and application level settings.</span></span>|[<span data-ttu-id="9ff90-125">My.Settings 개체</span><span class="sxs-lookup"><span data-stu-id="9ff90-125">My.Settings Object</span></span>](../objects/my-settings-object.md)|  
|<span data-ttu-id="9ff90-126">현재 사용자의 보안 컨텍스트에 액세스 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-126">Accessing the current user's security context.</span></span>|<span data-ttu-id="9ff90-127">`My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>)</span><span class="sxs-lookup"><span data-stu-id="9ff90-127">`My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>)</span></span>|  
|<span data-ttu-id="9ff90-128">현재 프로젝트에서 참조 하는 XML Web services에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff90-128">Accessing XML Web services referenced by the current project.</span></span>|[<span data-ttu-id="9ff90-129">My.WebServices 개체</span><span class="sxs-lookup"><span data-stu-id="9ff90-129">My.WebServices Object</span></span>](../objects/my-webservices-object.md)|  
  
## <a name="see-also"></a><span data-ttu-id="9ff90-130">참조</span><span class="sxs-lookup"><span data-stu-id="9ff90-130">See also</span></span>

- [<span data-ttu-id="9ff90-131">Visual Basic 애플리케이션 모델 개요</span><span class="sxs-lookup"><span data-stu-id="9ff90-131">Overview of the Visual Basic Application Model</span></span>](../../developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
- [<span data-ttu-id="9ff90-132">My를 사용한 개발</span><span class="sxs-lookup"><span data-stu-id="9ff90-132">Development with My</span></span>](../../developing-apps/development-with-my/index.md)
