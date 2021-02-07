---
description: '자세한 정보: TransportBindingElement'
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: de08feaf8abec3a0dfee97e92d68d5223cd0de44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757113"
---
# <a name="transportbindingelement"></a><span data-ttu-id="9e20a-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9e20a-103">TransportBindingElement</span></span>

<span data-ttu-id="9e20a-104">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="9e20a-104">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e20a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e20a-105">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9e20a-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9e20a-106">Methods</span></span>  

 <span data-ttu-id="9e20a-107">TransportBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e20a-107">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9e20a-108">속성</span><span class="sxs-lookup"><span data-stu-id="9e20a-108">Properties</span></span>  

 <span data-ttu-id="9e20a-109">TransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e20a-109">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="9e20a-110">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="9e20a-110">ManualAddressing</span></span>  

 <span data-ttu-id="9e20a-111">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="9e20a-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="9e20a-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9e20a-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9e20a-113">사용자가 메시지 주소 지정을 제어하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9e20a-113">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="9e20a-114">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="9e20a-114">MaxBufferPoolSize</span></span>  

 <span data-ttu-id="9e20a-115">데이터 형식: sint64</span><span class="sxs-lookup"><span data-stu-id="9e20a-115">Data type: sint64</span></span>  
  
 <span data-ttu-id="9e20a-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9e20a-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9e20a-117">바인딩에 대한 최대 버퍼 풀 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9e20a-117">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="9e20a-118">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="9e20a-118">MaxReceivedMessageSize</span></span>  

 <span data-ttu-id="9e20a-119">데이터 형식: sint64</span><span class="sxs-lookup"><span data-stu-id="9e20a-119">Data type: sint64</span></span>  
  
 <span data-ttu-id="9e20a-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9e20a-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9e20a-121">이 바인딩에서 처리하는 메시지의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9e20a-121">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="9e20a-122">구성표</span><span class="sxs-lookup"><span data-stu-id="9e20a-122">Scheme</span></span>  

 <span data-ttu-id="9e20a-123">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9e20a-123">Data type: string</span></span>  
  
 <span data-ttu-id="9e20a-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9e20a-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9e20a-125">전송을 위한 URI 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="9e20a-125">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e20a-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e20a-126">Requirements</span></span>  
  
|<span data-ttu-id="9e20a-127">MOF</span><span class="sxs-lookup"><span data-stu-id="9e20a-127">MOF</span></span>|<span data-ttu-id="9e20a-128">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e20a-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9e20a-129">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9e20a-129">Namespace</span></span>|<span data-ttu-id="9e20a-130">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e20a-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e20a-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e20a-131">See also</span></span>

- <xref:System.ServiceModel.Channels.TransportBindingElement>
