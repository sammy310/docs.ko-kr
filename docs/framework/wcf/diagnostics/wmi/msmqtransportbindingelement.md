---
description: '자세히 알아보기: MsmqTransportBindingElement'
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 4b6f363d979972c6ff0a2a378906feeece2ff6b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803154"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="6b3b9-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="6b3b9-103">MsmqTransportBindingElement</span></span>

<span data-ttu-id="6b3b9-104">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="6b3b9-104">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b3b9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b3b9-105">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6b3b9-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6b3b9-106">Methods</span></span>  

 <span data-ttu-id="6b3b9-107">MsmqTransportBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-107">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6b3b9-108">속성</span><span class="sxs-lookup"><span data-stu-id="6b3b9-108">Properties</span></span>  

 <span data-ttu-id="6b3b9-109">MsmqTransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-109">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="6b3b9-110">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="6b3b9-110">MaxPoolSize</span></span>  

 <span data-ttu-id="6b3b9-111">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="6b3b9-111">Data type: sint32</span></span>  
  
 <span data-ttu-id="6b3b9-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6b3b9-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b3b9-113">내부 MSMQ 메시지 개체가 포함된 풀의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-113">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="6b3b9-114">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="6b3b9-114">QueueTransferProtocol</span></span>  

 <span data-ttu-id="6b3b9-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="6b3b9-115">Data type: string</span></span>  
  
 <span data-ttu-id="6b3b9-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6b3b9-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b3b9-117">이 바인딩에서 사용하는 대기 중인 통신 채널 전송을 나타내는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-117">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="6b3b9-118">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="6b3b9-118">UseActiveDirectory</span></span>  

 <span data-ttu-id="6b3b9-119">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="6b3b9-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="6b3b9-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6b3b9-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6b3b9-121">Active Directory를 사용하여 큐 주소를 변환해야 하는지 여부를 나타내는 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-121">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b3b9-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b3b9-122">Requirements</span></span>  
  
|<span data-ttu-id="6b3b9-123">MOF</span><span class="sxs-lookup"><span data-stu-id="6b3b9-123">MOF</span></span>|<span data-ttu-id="6b3b9-124">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6b3b9-125">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="6b3b9-125">Namespace</span></span>|<span data-ttu-id="6b3b9-126">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b9-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b3b9-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b3b9-127">See also</span></span>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
