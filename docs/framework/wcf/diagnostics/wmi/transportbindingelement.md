---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: bdb5ca7400a41dd724c2ad7fc76695a82874ded6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641621"
---
# <a name="transportbindingelement"></a><span data-ttu-id="412ab-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="412ab-102">TransportBindingElement</span></span>
<span data-ttu-id="412ab-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="412ab-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="412ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="412ab-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="412ab-105">메서드</span><span class="sxs-lookup"><span data-stu-id="412ab-105">Methods</span></span>  
 <span data-ttu-id="412ab-106">TransportBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="412ab-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="412ab-107">속성</span><span class="sxs-lookup"><span data-stu-id="412ab-107">Properties</span></span>  
 <span data-ttu-id="412ab-108">TransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="412ab-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="412ab-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="412ab-109">ManualAddressing</span></span>  
 <span data-ttu-id="412ab-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="412ab-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="412ab-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="412ab-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="412ab-112">사용자가 메시지 주소 지정을 제어하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="412ab-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="412ab-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="412ab-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="412ab-114">데이터 형식: sint64</span><span class="sxs-lookup"><span data-stu-id="412ab-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="412ab-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="412ab-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="412ab-116">바인딩에 대한 최대 버퍼 풀 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="412ab-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="412ab-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="412ab-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="412ab-118">데이터 형식: sint64</span><span class="sxs-lookup"><span data-stu-id="412ab-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="412ab-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="412ab-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="412ab-120">이 바인딩에서 처리하는 메시지의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="412ab-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="412ab-121">Scheme</span><span class="sxs-lookup"><span data-stu-id="412ab-121">Scheme</span></span>  
 <span data-ttu-id="412ab-122">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="412ab-122">Data type: string</span></span>  
  
 <span data-ttu-id="412ab-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="412ab-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="412ab-124">전송을 위한 URI 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="412ab-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="412ab-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="412ab-125">Requirements</span></span>  
  
|<span data-ttu-id="412ab-126">MOF</span><span class="sxs-lookup"><span data-stu-id="412ab-126">MOF</span></span>|<span data-ttu-id="412ab-127">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="412ab-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="412ab-128">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="412ab-128">Namespace</span></span>|<span data-ttu-id="412ab-129">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="412ab-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="412ab-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="412ab-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TransportBindingElement>
