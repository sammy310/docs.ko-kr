---
description: '자세히 알아보기: BinaryMessageEncodingBindingElement'
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: e2bc711416c61ca29a93fbf75e4e734137f2b4be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757880"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="adfbc-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="adfbc-103">BinaryMessageEncodingBindingElement</span></span>

<span data-ttu-id="adfbc-104">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="adfbc-104">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adfbc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="adfbc-105">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="adfbc-106">메서드</span><span class="sxs-lookup"><span data-stu-id="adfbc-106">Methods</span></span>  

 <span data-ttu-id="adfbc-107">BinaryMessageEncodingBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="adfbc-107">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="adfbc-108">속성</span><span class="sxs-lookup"><span data-stu-id="adfbc-108">Properties</span></span>  

 <span data-ttu-id="adfbc-109">BinaryMessageEncodingBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adfbc-109">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="adfbc-110">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="adfbc-110">MaxReadPoolSize</span></span>  

 <span data-ttu-id="adfbc-111">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="adfbc-111">Data type: sint32</span></span>  
  
 <span data-ttu-id="adfbc-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="adfbc-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="adfbc-113">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="adfbc-113">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="adfbc-114">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="adfbc-114">MaxSessionSize</span></span>  

 <span data-ttu-id="adfbc-115">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="adfbc-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="adfbc-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="adfbc-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="adfbc-117">인코딩에 사용되는 버퍼의 크기(바이트)를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="adfbc-117">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="adfbc-118">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="adfbc-118">MaxWritePoolSize</span></span>  

 <span data-ttu-id="adfbc-119">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="adfbc-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="adfbc-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="adfbc-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="adfbc-121">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="adfbc-121">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="adfbc-122">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="adfbc-122">ReaderQuotas</span></span>  

 <span data-ttu-id="adfbc-123">데이터 형식: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="adfbc-123">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="adfbc-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="adfbc-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="adfbc-125">판독기의 할당량입니다.</span><span class="sxs-lookup"><span data-stu-id="adfbc-125">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adfbc-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="adfbc-126">Requirements</span></span>  
  
|<span data-ttu-id="adfbc-127">MOF</span><span class="sxs-lookup"><span data-stu-id="adfbc-127">MOF</span></span>|<span data-ttu-id="adfbc-128">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adfbc-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="adfbc-129">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="adfbc-129">Namespace</span></span>|<span data-ttu-id="adfbc-130">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adfbc-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="adfbc-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="adfbc-131">See also</span></span>

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
