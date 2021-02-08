---
description: '자세한 정보: 분석 추적 개요'
title: 분석 추적 개요
ms.date: 03/30/2017
helpviewer_keywords:
- analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
ms.openlocfilehash: 574236b364ab03afbf3c1f3dc3a63842220e38b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798864"
---
# <a name="analytic-tracing-overview"></a><span data-ttu-id="3ee31-103">분석 추적 개요</span><span class="sxs-lookup"><span data-stu-id="3ee31-103">Analytic tracing overview</span></span>

<span data-ttu-id="3ee31-104">[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] 의 분석 추적은 ETW(Event Tracing for Windows)를 기반으로 하는 고성능의 간단한 추적 기능 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-104">Analytic tracing in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] is a high performance and low verbosity tracing feature set on top of Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="3ee31-105">ETW는 커널 수준에서 실행되기 때문에 추적 작업의 오버헤드를 크게 줄이며,</span><span class="sxs-lookup"><span data-stu-id="3ee31-105">ETW runs at the kernel-level to greatly reduce the overhead of tracing operations.</span></span> <span data-ttu-id="3ee31-106">사용자 및 커널 모드 이벤트를 효율적으로 버퍼링하고 서비스를 다시 시작하지 않고도 동적으로 로깅을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-106">It efficiently buffers user- and kernel-mode events, and allows dynamic enabling of logging without requiring service restarts.</span></span> <span data-ttu-id="3ee31-107">추적 데이터는 내보내기와 받기 과정을 거친 후 이벤트 로그에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-107">The tracing data is available in the event logs after it has been emitted and received.</span></span>

<span data-ttu-id="3ee31-108">ETW에 대 한 자세한 내용은 [etw를 사용한 디버깅 및 성능 조정 개선](/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ee31-108">For more information about ETW, see [Improve Debugging and Performance Tuning with ETW](/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw).</span></span>

 <span data-ttu-id="3ee31-109">Windows 시스템, 보안 및 응용 프로그램 이벤트 로그를 사용 하 여 응용 프로그램을 분석 하는 것 외에도 Windows Vista 및 Windows Server 2008에서는 응용 프로그램 및 서비스 로그 최상위 노드 아래에 추가 로그를 도입 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-109">In addition to using the Windows System, Security, and Application event logs to analyze application, Windows Vista and Windows Server 2008 introduced additional logs under the Applications and Services Logs top-level node.</span></span> <span data-ttu-id="3ee31-110">이러한 새 로그의 목적은 보안 이벤트 로그에 기록될 수 있는 이벤트 형식처럼 시스템 전체에 영향을 주는 전역 이벤트가 아니라 특정 애플리케이션이나 구성 요소에 대한 이벤트를 저장하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-110">The purpose of these new logs is to store events for a particular application or specific component instead of global events that have a system-wide impact (such as the type of events that the Security event log might record).</span></span> [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] <span data-ttu-id="3ee31-111">는 WCF 추적 이벤트, WCF 메시지 로그 및 [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] 추적 레코드의 로깅을 응용 프로그램 및 서비스 로그와 통합 하 고 상관 관계를 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-111">unifies and correlates the logging of WCF Trace Events, WCF Message Logs, and [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] Tracking records to the Applications and Services Logs.</span></span>

<span data-ttu-id="3ee31-112">다음 섹션에서는 WCF 분석 추적에 적용 되는 개념 및 기능을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-112">The following sections cover concepts and capabilities that apply to WCF analytic tracing.</span></span>

## <a name="enable-wcf-diagnostics-settings"></a><span data-ttu-id="3ee31-113">WCF 진단 설정 사용</span><span class="sxs-lookup"><span data-stu-id="3ee31-113">Enable WCF Diagnostics Settings</span></span>

<span data-ttu-id="3ee31-114">WCF 진단은 구성 섹션 내에서 사용 하도록 설정 됩니다 `<system.serviceModel><diagnostics>` .</span><span class="sxs-lookup"><span data-stu-id="3ee31-114">WCF diagnostics are enabled within the `<system.serviceModel><diagnostics>` configuration section.</span></span>

```xml
<system.serviceModel>
  <diagnostics>
```

<span data-ttu-id="3ee31-115">웹 호스팅 IIS 가상 응용 프로그램에 대 한 WCF 진단 설정은 해당 *Web.config* 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-115">WCF diagnostic settings for a Web-hosted IIS virtual application are enabled in its *Web.config* file.</span></span> <span data-ttu-id="3ee31-116">또 다른 옵션은 응용 프로그램 내의 하위 디렉터리에 *Web.config* 파일을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-116">Another option is to create a *Web.config* file in a subdirectory within the application.</span></span> <span data-ttu-id="3ee31-117">이 옵션을 선택 하면 하위 디렉터리 내의 모든 서비스에 설정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-117">This choice applies the settings to all of the services within a subdirectory.</span></span> <span data-ttu-id="3ee31-118">진단 설정이 응용 프로그램 내의 모든 서비스에 대해 일관 되 게 초기화 되도록 하려면 설정이 응용 프로그램 내의 개별 하위 디렉터리 중 하나가 아니라 응용 프로그램 디렉터리의 *Web.config* 파일 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-118">To ensure that the diagnostics settings are initialized consistently for all services within the application, the settings should be within the *Web.config* file in the application directory and not in one of the individual subdirectories within the application.</span></span>

## <a name="channels"></a><span data-ttu-id="3ee31-119">채널</span><span class="sxs-lookup"><span data-stu-id="3ee31-119">Channels</span></span>

<span data-ttu-id="3ee31-120">ETW를 사용하면 소프트웨어 구성 요소에서 채널을 통해 추적 이벤트를 특정 대상에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-120">ETW allows software components to direct tracing events to a particular audience by use of channels.</span></span> <span data-ttu-id="3ee31-121">예를 들어, 시스템 관리자에 대 한 이벤트를 응용 프로그램 개발자가 다른 채널에 대해 중요 한 한 채널 및 이벤트에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-121">For example, you can send events for system administrators to one channel and events that application developers care about to another channel.</span></span> <span data-ttu-id="3ee31-122">채널은 이름이 지정 되어 Windows에 등록 되므로 소비자는 이벤트 뷰어를 사용 하 여 채널의 이벤트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-122">Channels are named and registered with Windows so that consumers can view a channel's events using Event Viewer.</span></span>

 <span data-ttu-id="3ee31-123">에서 WCF에 대 한 분석 추적 기능은 [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] Microsoft-Windows 응용 프로그램-서버-응용 프로그램 채널에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-123">The analytic tracing feature for WCF in [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] writes to the Microsoft-Windows-Application-Server-Applications channel.</span></span> <span data-ttu-id="3ee31-124">이 채널은 프로덕션 환경에서 WCF 서비스의 상태를 모니터링 하려는 사용자를 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-124">This channel is designed for users who want to monitor the health of WCF services in production.</span></span> <span data-ttu-id="3ee31-125">많은 상태 모니터링 및 문제 해결 시나리오에서 사용할 수 있는 작은 이벤트 집합을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-125">It defines a small set of events that can be used in many health monitoring and troubleshooting scenarios.</span></span>

 <span data-ttu-id="3ee31-126">메시지가 이벤트 로그에서 적절하게 디코딩되게 하기 위해 Windows용 이벤트 추적 매니페스트를 사용하도록 설정하려면 다음과 같이 명령줄에서 ServiceModelReg 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-126">To enable the Event Tracing for Windows manifest so that messages are decoded properly in the event log, use the ServiceModelReg tool on the command line as follows:</span></span>

 `ServiceModelReg.exe -i -c:etw`

## <a name="dynamic-configuration"></a><span data-ttu-id="3ee31-127">동적 구성</span><span class="sxs-lookup"><span data-stu-id="3ee31-127">Dynamic Configuration</span></span>

<span data-ttu-id="3ee31-128">ETW 인프라를 사용하면 표준 Windows 도구를 사용하여 동적으로 추적을 사용하도록 설정하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-128">The ETW infrastructure allows tracing to be enabled and configured dynamically using standard Windows tools.</span></span> <span data-ttu-id="3ee31-129">자세한 내용은 [분석 추적을 동적으로 사용](dynamically-enabling-analytic-tracing.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ee31-129">For more information, see [Dynamically Enabling Analytic Tracing](dynamically-enabling-analytic-tracing.md).</span></span>

## <a name="message-flow-tracing"></a><span data-ttu-id="3ee31-130">메시지 흐름 추적</span><span class="sxs-lookup"><span data-stu-id="3ee31-130">Message Flow Tracing</span></span>

<span data-ttu-id="3ee31-131">메시지 흐름 추적을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [메시지 흐름 추적 구성](configuring-message-flow-tracing.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ee31-131">For more information about how to enable message flow tracing, see [Configuring Message Flow Tracing](configuring-message-flow-tracing.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="3ee31-132">키워드</span><span class="sxs-lookup"><span data-stu-id="3ee31-132">Keywords</span></span>

<span data-ttu-id="3ee31-133">키워드는 추적 메시지를 필터링 하 고 이벤트를 내보낼 .NET Framework의 구성 요소를 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ee31-133">Keywords are used to filter trace messages and define which component of the .NET Framework emitted the event.</span></span> <span data-ttu-id="3ee31-134">자세한 내용은 [분석 추적을 동적으로 사용](dynamically-enabling-analytic-tracing.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ee31-134">For more information, see [Dynamically Enabling Analytic Tracing](dynamically-enabling-analytic-tracing.md).</span></span>
