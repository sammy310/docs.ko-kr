---
title: <soapProcessing>
ms.date: 03/30/2017
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
ms.openlocfilehash: 678b1f71ac15d3ad30df28cec5abbe403fb08c95
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937054"
---
# <a name="soapprocessing"></a><span data-ttu-id="e051a-101">\<soapProcessing></span><span class="sxs-lookup"><span data-stu-id="e051a-101">\<soapProcessing></span></span>

<span data-ttu-id="e051a-102">서로 다른 바인딩 형식과 메시지 버전 간에 메시지 마샬링을 위해 사용되는 클라이언트 엔드포인트 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-102">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>

<span data-ttu-id="e051a-103">**\<system.ServiceModel>**  </span><span class="sxs-lookup"><span data-stu-id="e051a-103">**\<system.ServiceModel>** </span></span>  
<span data-ttu-id="e051a-104">&nbsp;&nbsp; **\<behaviors>**  </span><span class="sxs-lookup"><span data-stu-id="e051a-104">&nbsp;&nbsp;**\<behaviors>** </span></span>  
<span data-ttu-id="e051a-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<endpointBehaviors>**  </span><span class="sxs-lookup"><span data-stu-id="e051a-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors>** </span></span>  
<span data-ttu-id="e051a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<behavior>**  </span><span class="sxs-lookup"><span data-stu-id="e051a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>** </span></span>  
<span data-ttu-id="e051a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<soapProcessing>**</span><span class="sxs-lookup"><span data-stu-id="e051a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="e051a-108">구문</span><span class="sxs-lookup"><span data-stu-id="e051a-108">Syntax</span></span>  
  
```xml  
<soapProcessing processMessages="true|false" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e051a-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e051a-109">Attributes and elements</span></span>  
  
<span data-ttu-id="e051a-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e051a-111">특성</span><span class="sxs-lookup"><span data-stu-id="e051a-111">Attributes</span></span>  
  
|                   | <span data-ttu-id="e051a-112">설명</span><span class="sxs-lookup"><span data-stu-id="e051a-112">Description</span></span> |
| ----------------- | ----------- |
| `processMessages` | <span data-ttu-id="e051a-113">SOAP 메시지 버전 간에 메시지가 마샬링되어야 하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-113">A Boolean value that specifies whether messages should be marshaled between SOAP message versions.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="e051a-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e051a-114">Child elements</span></span>

<span data-ttu-id="e051a-115">없음</span><span class="sxs-lookup"><span data-stu-id="e051a-115">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e051a-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e051a-116">Parent elements</span></span>

|     | <span data-ttu-id="e051a-117">설명</span><span class="sxs-lookup"><span data-stu-id="e051a-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e051a-118"> **\<behavior>** </span><span class="sxs-lookup"><span data-stu-id="e051a-118">**\<behavior>**</span></span>](behavior-of-endpointbehaviors.md) | <span data-ttu-id="e051a-119">엔드포인트 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-119">Specifies an endpoint behavior.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e051a-120">설명</span><span class="sxs-lookup"><span data-stu-id="e051a-120">Remarks</span></span>

<span data-ttu-id="e051a-121">SOAP 처리는 메시지 버전 간에 메시지를 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-121">SOAP processing is the process where messages are converted between message versions.</span></span>

<span data-ttu-id="e051a-122">WCF (Windows Communication Foundation) 라우팅 서비스는 한 프로토콜에서 다른 프로토콜로 메시지를 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-122">The Windows Communication Foundation (WCF) Routing Service can convert messages from one protocol to another.</span></span> <span data-ttu-id="e051a-123">들어오는 메시지 버전과 나가는 메시지 버전이 다른 경우 올바른 버전의 새로운 메시지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-123">If the incoming and outgoing Message Versions are different, a new message of the correct version is created.</span></span> <span data-ttu-id="e051a-124">한 <xref:System.ServiceModel.Channels.MessageVersion>에서 다른 버전으로 메시지를 처리하는 작업은 들어오는 WCF 메시지의 본문 부분과 관련 헤더를 포함하는 새 WCF 메시지를 생성하는 방법으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-124">Processing messages from one <xref:System.ServiceModel.Channels.MessageVersion> to another is accomplished by constructing a new WCF message that contains the body part and relevant headers from the incoming WCF message.</span></span> <span data-ttu-id="e051a-125">주소 지정에만 사용되는 헤더나 라우터 수준에서 인식되는 헤더는 새 WCF 메시지 생성 중에 사용되지 않습니다. 이러한 헤더는 서로 다른 버전(주소 지정 헤더인 경우)이거나 클라이언트와 라우터 간의 통신의 일부로 처리되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-125">Headers that are specific to addressing, or that are understood at the router level, are not used during construction of the new WCF message because these headers are either of a different version (in the case of addressing headers) or have been processed as part of the communication between the client and the router.</span></span>

<span data-ttu-id="e051a-126">헤더가 아웃바운드 메시지에 배치되는지 여부는 들어오는 채널 계층을 통해 전달될 때 해당 헤더가 인식된 것으로 표시되었는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-126">Whether a header is placed in the outbound message is determined by whether or not it was marked as understood as it passed through the incoming channel layer.</span></span> <span data-ttu-id="e051a-127">사용자 지정 헤더 등과 같이 인식되지 않는 헤더는 제거되지 않고 아웃바운드 메시지에 복사되어 라우팅 서비스를 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-127">Headers that are not understood (such as custom headers) are not removed and so pass through the routing service by being copied to the outbound message.</span></span> <span data-ttu-id="e051a-128">메시지의 본문은 아웃바운드 메시지에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-128">The body of the message is copied to the outbound message.</span></span> <span data-ttu-id="e051a-129">그런 다음 메시지가 아웃바운드 채널로 전송되며 이때 해당 통신 프로토콜/전송에 대한 모든 헤더와 기타 봉투 데이터가 만들어지고 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-129">The message is then sent out the outbound channel, at which point all of the headers and other envelope data specific to that communication protocol/transport will be created and added.</span></span>

<span data-ttu-id="e051a-130">이러한 처리 단계는 SOAP 처리 동작이 지정될 때 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-130">Such processing steps take place when the SOAP processing behavior is specified.</span></span> <span data-ttu-id="e051a-131">[ 이\<soapProcessingExtension >](soapprocessing.md) 동작은 라우팅 서비스 시작 시 모든 클라이언트 (나가는) 끝점에 적용 되는 끝점 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-131">This [\<soapProcessingExtension>](soapprocessing.md) behavior is an endpoint behavior that is applied to all client (outgoing) endpoints when the Routing Service starts up.</span></span> <span data-ttu-id="e051a-132">기본적으로 [ \<라우팅 >](routing-of-servicebehavior.md) 동작은 각 클라이언트 끝점에 대해 `true` 를로 설정 하 여 `processMessages` 새 [ \<soapProcessingExtension >](soapprocessing.md) 동작을 만들고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-132">default, the [\<routing>](routing-of-servicebehavior.md) behavior creates and attaches a new [\<soapProcessingExtension>](soapprocessing.md) behavior with `processMessages` set to `true` for each client endpoint.</span></span> <span data-ttu-id="e051a-133">라우팅 서비스에서 인식하지 못하는 프로토콜을 사용하거나 기본 처리 동작을 재지정하려는 경우 전체 라우팅 서비스 또는 특정 엔드포인트에 대해 SOAP 처리를 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-133">If you have a protocol that the Routing Service does not understand, or wish to override the default processing behavior, you can disable SOAP processing either for the entire Routing Service or just for particular endpoints.</span></span>  <span data-ttu-id="e051a-134">모든 끝점에서 전체 라우팅 서비스에 대해 SOAP 처리를 사용 하지 않도록 설정 `soapProcessing` 하려면 [ \<라우팅 >](routing-of-servicebehavior.md) 동작의 특성을 `false`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-134">To disable SOAP processing for the entire routing service on all endpoints, set the `soapProcessing` attribute of the [\<routing>](routing-of-servicebehavior.md) behavior to `false`.</span></span> <span data-ttu-id="e051a-135">특정 엔드포인트에 대해 SOAP 처리를 해제하려면 이 동작을 사용하여 `processMessages` 특성을 `false`로 설정한 다음 이 동작을 기본 처리 코드가 실행되지 않도록 할 엔드포인트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e051a-135">To turn off SOAP processing for a particular endpoint, use this behavior and set its `processMessages` attribute to `false`, then attach this behavior to the endpoint you do not want the default processing code to run at.</span></span>  <span data-ttu-id="e051a-136">라우팅 > 동작에서 라우팅 서비스를 설정 하는 경우 끝점 동작이 이미 존재 하므로 다시 적용 하는 작업은 건너뜁니다. [ \<](routing-of-servicebehavior.md)</span><span class="sxs-lookup"><span data-stu-id="e051a-136">When the [\<routing>](routing-of-servicebehavior.md) behavior sets up the Routing Service, it will skip reapplying the endpoint behavior since one already exists.</span></span>
