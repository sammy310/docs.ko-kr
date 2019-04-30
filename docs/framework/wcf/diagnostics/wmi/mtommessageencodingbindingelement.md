---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: aed65311d2b36a5dc764511de04e34c4bfb69d7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963257"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="5d914-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="5d914-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="5d914-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="5d914-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d914-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d914-104">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5d914-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5d914-105">Methods</span></span>  
 <span data-ttu-id="5d914-106">MtomMessageEncodingBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d914-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5d914-107">속성</span><span class="sxs-lookup"><span data-stu-id="5d914-107">Properties</span></span>  
 <span data-ttu-id="5d914-108">MtomMessageEncodingBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d914-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="5d914-109">인코딩</span><span class="sxs-lookup"><span data-stu-id="5d914-109">Encoding</span></span>  
 <span data-ttu-id="5d914-110">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="5d914-110">Data type: string</span></span>  
  
 <span data-ttu-id="5d914-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5d914-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d914-112">바인딩에서 메시지를 내보낼 때 사용되는 문자 집합 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="5d914-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="5d914-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="5d914-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="5d914-114">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="5d914-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="5d914-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5d914-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d914-116">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d914-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="5d914-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="5d914-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="5d914-118">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="5d914-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="5d914-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5d914-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d914-120">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d914-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="5d914-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="5d914-121">ReaderQuotas</span></span>  
 <span data-ttu-id="5d914-122">데이터 형식: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="5d914-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="5d914-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5d914-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5d914-124">판독기의 할당량입니다.</span><span class="sxs-lookup"><span data-stu-id="5d914-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d914-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d914-125">Requirements</span></span>  
  
|<span data-ttu-id="5d914-126">MOF</span><span class="sxs-lookup"><span data-stu-id="5d914-126">MOF</span></span>|<span data-ttu-id="5d914-127">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d914-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5d914-128">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="5d914-128">Namespace</span></span>|<span data-ttu-id="5d914-129">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d914-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d914-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d914-130">See also</span></span>

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
