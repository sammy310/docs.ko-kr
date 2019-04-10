---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: e0551e7b4b05151490625912742aa6b26ef0216e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145680"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="121b8-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="121b8-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="121b8-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="121b8-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="121b8-104">구문</span><span class="sxs-lookup"><span data-stu-id="121b8-104">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="121b8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="121b8-105">Methods</span></span>  
 <span data-ttu-id="121b8-106">BinaryMessageEncodingBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="121b8-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="121b8-107">속성</span><span class="sxs-lookup"><span data-stu-id="121b8-107">Properties</span></span>  
 <span data-ttu-id="121b8-108">BinaryMessageEncodingBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="121b8-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="121b8-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="121b8-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="121b8-110">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="121b8-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="121b8-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="121b8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="121b8-112">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="121b8-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="121b8-113">MaxSessionSize</span><span class="sxs-lookup"><span data-stu-id="121b8-113">MaxSessionSize</span></span>  
 <span data-ttu-id="121b8-114">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="121b8-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="121b8-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="121b8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="121b8-116">인코딩에 사용되는 버퍼의 크기(바이트)를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="121b8-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="121b8-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="121b8-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="121b8-118">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="121b8-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="121b8-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="121b8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="121b8-120">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="121b8-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="121b8-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="121b8-121">ReaderQuotas</span></span>  
 <span data-ttu-id="121b8-122">데이터 형식: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="121b8-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="121b8-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="121b8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="121b8-124">판독기의 할당량입니다.</span><span class="sxs-lookup"><span data-stu-id="121b8-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="121b8-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="121b8-125">Requirements</span></span>  
  
|<span data-ttu-id="121b8-126">MOF</span><span class="sxs-lookup"><span data-stu-id="121b8-126">MOF</span></span>|<span data-ttu-id="121b8-127">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="121b8-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="121b8-128">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="121b8-128">Namespace</span></span>|<span data-ttu-id="121b8-129">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="121b8-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="121b8-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="121b8-130">See also</span></span>

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
