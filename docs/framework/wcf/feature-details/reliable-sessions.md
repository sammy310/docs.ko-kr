---
description: '자세히 알아보기: 신뢰할 수 있는 세션'
title: 신뢰할 수 있는 세션
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 86df4ccf9c1fd52d162ad7272ece5591f0ca7482
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632882"
---
# <a name="reliable-sessions"></a><span data-ttu-id="d9bbb-103">신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="d9bbb-103">Reliable Sessions</span></span>

<span data-ttu-id="d9bbb-104">이 섹션에서는 Windows Communication Foundation (WCF) 신뢰할 수 있는 세션의 정의, 사용 방법, 사용 방법, 사용 하는 방법 및 사용 시기, 구성 요소를 지 원하는 바인딩 구성 및 모범 사례에 대 한 포인터를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9bbb-104">This section describes what a Windows Communication Foundation (WCF) reliable session is, what it's used for, how and when to use one, what binding configurations support it, and pointers on best practices.</span></span> <span data-ttu-id="d9bbb-105">다음 표에서는 이 단원의 필수 사항 및 관련 항목에 대한 세부 정보를 요약하여 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d9bbb-105">The following table summarizes details about the essential points and related topics in this section.</span></span>

<span data-ttu-id="d9bbb-106">신뢰할 수 있는 세션 WCF는 끝점 간에 전송 되는 메시지가 SOAP 또는 전송 중개자를 통해 전송 되도록 하는 기능을 제공 하며,이를 보낸 순서와 동일 하 게 한 번만 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9bbb-106">The reliable session WCF provides features ensuring that messages sent between endpoints are transferred across SOAP or transport intermediaries and are delivered only once and, optionally, in the same order in which they were sent.</span></span>

<span data-ttu-id="d9bbb-107">WCF 응용 프로그램에서 신뢰할 수 있는 세션을 사용 하려면 기본적으로 또는 옵션으로 신뢰할 수 있는 세션을 지 원하는 WCF의 시스템 제공 바인딩 중 하나를 사용 하거나, 세션을 지 원하는 사용자 지정 바인딩을 직접 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9bbb-107">To use a reliable session with a WCF application, either use one of the system-provided bindings in WCF that support a reliable session by default or as an option, or create your own custom binding that supports the session.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d9bbb-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d9bbb-108">In This Section</span></span>

<span data-ttu-id="d9bbb-109">[신뢰할 수 있는 세션 개요](reliable-sessions-overview.md) 신뢰할 수 있는 세션, 사용 시기, 신뢰할 수 있는 세션을 지 원하는 다양 한 바인딩 및 작동 방식에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9bbb-109">[Reliable Sessions Overview](reliable-sessions-overview.md) Describes reliable sessions, when to use them, the different bindings that support reliable sessions, and how they work.</span></span>

<span data-ttu-id="d9bbb-110">[방법: 신뢰할 수 있는 세션 내에서 메시지 교환](how-to-exchange-messages-within-a-reliable-session.md) 구성에 지정 된 사용자 지정 바인딩을 사용 하 여 HTTP를 통해 신뢰할 수 있는 세션을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9bbb-110">[How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md) Describes how to create a reliable session over HTTP using a custom binding specified in the configuration.</span></span>

<span data-ttu-id="d9bbb-111">[방법: 신뢰할 수 있는 세션 내에서 메시지 보안](how-to-secure-messages-within-reliable-sessions.md) 신뢰할 수 있는 세션을 보호 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9bbb-111">[How to: Secure Messages within Reliable Sessions](how-to-secure-messages-within-reliable-sessions.md) Describes how to secure a reliable session.</span></span>

<span data-ttu-id="d9bbb-112">[방법: HTTPS를 사용 하 여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기](how-to-create-a-custom-reliable-session-binding-with-https.md) HTTPS를 통해 신뢰할 수 있는 세션을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9bbb-112">[How to: Create a Custom Reliable Session Binding with HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md) Describes how to create a reliable session over HTTPS.</span></span>

<span data-ttu-id="d9bbb-113">[신뢰할 수 있는 세션에 대 한 모범 사례](best-practices-for-reliable-sessions.md) 신뢰할 수 있는 세션을 사용 하는 것과 관련 된 몇 가지 모범 사례를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9bbb-113">[Best Practices for Reliable Sessions](best-practices-for-reliable-sessions.md) Describes some of the best practices associated with using a reliable session.</span></span>

## <a name="reference"></a><span data-ttu-id="d9bbb-114">참고</span><span class="sxs-lookup"><span data-stu-id="d9bbb-114">Reference</span></span>

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a><span data-ttu-id="d9bbb-115">참조</span><span class="sxs-lookup"><span data-stu-id="d9bbb-115">See also</span></span>

- [<span data-ttu-id="d9bbb-116">큐 및 신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="d9bbb-116">Queues and Reliable Sessions</span></span>](queues-and-reliable-sessions.md)
- [<span data-ttu-id="d9bbb-117">세션, 인스턴스 및 동시성</span><span class="sxs-lookup"><span data-stu-id="d9bbb-117">Sessions, Instancing, and Concurrency</span></span>](sessions-instancing-and-concurrency.md)
