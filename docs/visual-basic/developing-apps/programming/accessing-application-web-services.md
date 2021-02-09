---
description: '자세한 정보: 애플리케이션 웹 서비스 액세스(Visual Basic)'
title: 애플리케이션 웹 서비스 액세스
ms.date: 07/20/2015
helpviewer_keywords:
- Web services [Visual Basic], My.WebServices object
- My.WebServices object
- applications [Visual Basic], Web services
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
ms.openlocfilehash: 4efd35ed7c8f4251a749b85a45242af299a51e6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797889"
---
# <a name="accessing-application-web-services-visual-basic"></a><span data-ttu-id="607a1-103">애플리케이션 웹 서비스 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="607a1-103">Accessing Application Web Services (Visual Basic)</span></span>

<span data-ttu-id="607a1-104">`My.WebServices` 개체는 현재 프로젝트에서 참조하는 각 웹 서비스의 인스턴스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="607a1-104">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="607a1-105">필요에 따라 각 인스턴스가 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="607a1-105">Each instance is instantiated on demand.</span></span> <span data-ttu-id="607a1-106">`My.WebServices` 개체의 속성을 통해 이러한 웹 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="607a1-106">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="607a1-107">속성 이름은 속성이 액세스하는 웹 서비스의 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="607a1-107">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="607a1-108"><xref:System.Web.Services.Protocols.SoapHttpClientProtocol>에서 상속되는 모든 클래스는 웹 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="607a1-108">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span>

## <a name="tasks"></a><span data-ttu-id="607a1-109">작업</span><span class="sxs-lookup"><span data-stu-id="607a1-109">Tasks</span></span>

<span data-ttu-id="607a1-110">다음 표에는 애플리케이션이 참조하는 웹 서비스에 액세스하는 가능한 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="607a1-110">The following table lists possible ways to access Web services referenced by an application.</span></span>

|<span data-ttu-id="607a1-111">대상</span><span class="sxs-lookup"><span data-stu-id="607a1-111">To</span></span>|<span data-ttu-id="607a1-112">참조 항목</span><span class="sxs-lookup"><span data-stu-id="607a1-112">See</span></span>|
|---|---|
|<span data-ttu-id="607a1-113">웹 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="607a1-113">Call a Web service</span></span>|[<span data-ttu-id="607a1-114">My.WebServices 개체</span><span class="sxs-lookup"><span data-stu-id="607a1-114">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)|
|<span data-ttu-id="607a1-115">비동기적으로 웹 서비스 호출 및 완료 시 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="607a1-115">Call a Web service asynchronously and handle an event when it completes</span></span>|[<span data-ttu-id="607a1-116">방법: 비동기적으로 웹 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="607a1-116">How to: Call a Web Service Asynchronously</span></span>](how-to-call-a-web-service-asynchronously.md)|

## <a name="see-also"></a><span data-ttu-id="607a1-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="607a1-117">See also</span></span>

- [<span data-ttu-id="607a1-118">My.WebServices 개체</span><span class="sxs-lookup"><span data-stu-id="607a1-118">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
