---
title: 애플리케이션 웹 서비스 액세스
ms.date: 07/20/2015
helpviewer_keywords:
- Web services [Visual Basic], My.WebServices object
- My.WebServices object
- applications [Visual Basic], Web services
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
ms.openlocfilehash: cf9a0c9840b9228b59af9959cf3a4efb9a1d1ea0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410194"
---
# <a name="accessing-application-web-services-visual-basic"></a><span data-ttu-id="23618-102">애플리케이션 웹 서비스 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23618-102">Accessing Application Web Services (Visual Basic)</span></span>

<span data-ttu-id="23618-103">`My.WebServices` 개체는 현재 프로젝트에서 참조하는 각 웹 서비스의 인스턴스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23618-103">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="23618-104">필요에 따라 각 인스턴스가 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="23618-104">Each instance is instantiated on demand.</span></span> <span data-ttu-id="23618-105">`My.WebServices` 개체의 속성을 통해 이러한 웹 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23618-105">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="23618-106">속성 이름은 속성이 액세스하는 웹 서비스의 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="23618-106">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="23618-107"><xref:System.Web.Services.Protocols.SoapHttpClientProtocol>에서 상속되는 모든 클래스는 웹 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="23618-107">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span>

## <a name="tasks"></a><span data-ttu-id="23618-108">작업</span><span class="sxs-lookup"><span data-stu-id="23618-108">Tasks</span></span>

<span data-ttu-id="23618-109">다음 표에는 애플리케이션이 참조하는 웹 서비스에 액세스하는 가능한 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23618-109">The following table lists possible ways to access Web services referenced by an application.</span></span>

|<span data-ttu-id="23618-110">대상</span><span class="sxs-lookup"><span data-stu-id="23618-110">To</span></span>|<span data-ttu-id="23618-111">참조 항목</span><span class="sxs-lookup"><span data-stu-id="23618-111">See</span></span>|
|---|---|
|<span data-ttu-id="23618-112">웹 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="23618-112">Call a Web service</span></span>|[<span data-ttu-id="23618-113">My.WebServices 개체</span><span class="sxs-lookup"><span data-stu-id="23618-113">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)|
|<span data-ttu-id="23618-114">비동기적으로 웹 서비스 호출 및 완료 시 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="23618-114">Call a Web service asynchronously and handle an event when it completes</span></span>|[<span data-ttu-id="23618-115">방법: 비동기적으로 웹 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="23618-115">How to: Call a Web Service Asynchronously</span></span>](how-to-call-a-web-service-asynchronously.md)|

## <a name="see-also"></a><span data-ttu-id="23618-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23618-116">See also</span></span>

- [<span data-ttu-id="23618-117">My.WebServices 개체</span><span class="sxs-lookup"><span data-stu-id="23618-117">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
