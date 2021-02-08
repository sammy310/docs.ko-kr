---
description: '자세히 알아보기: MtomMessageEncodingBindingElement'
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: f06e3d7266c4f7e6f9b4639f7d82941cbabb5dd3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803141"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="a58e9-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="a58e9-103">MtomMessageEncodingBindingElement</span></span>

<span data-ttu-id="a58e9-104">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="a58e9-104">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a58e9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a58e9-105">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a58e9-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a58e9-106">Methods</span></span>  

 <span data-ttu-id="a58e9-107">MtomMessageEncodingBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a58e9-107">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a58e9-108">속성</span><span class="sxs-lookup"><span data-stu-id="a58e9-108">Properties</span></span>  

 <span data-ttu-id="a58e9-109">MtomMessageEncodingBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a58e9-109">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="a58e9-110">Encoding</span><span class="sxs-lookup"><span data-stu-id="a58e9-110">Encoding</span></span>  

 <span data-ttu-id="a58e9-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="a58e9-111">Data type: string</span></span>  
  
 <span data-ttu-id="a58e9-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a58e9-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a58e9-113">바인딩에서 메시지를 내보낼 때 사용되는 문자 집합 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="a58e9-113">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="a58e9-114">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="a58e9-114">MaxReadPoolSize</span></span>  

 <span data-ttu-id="a58e9-115">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="a58e9-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="a58e9-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a58e9-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a58e9-117">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a58e9-117">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="a58e9-118">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="a58e9-118">MaxWritePoolSize</span></span>  

 <span data-ttu-id="a58e9-119">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="a58e9-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="a58e9-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a58e9-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a58e9-121">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a58e9-121">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="a58e9-122">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="a58e9-122">ReaderQuotas</span></span>  

 <span data-ttu-id="a58e9-123">데이터 형식: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="a58e9-123">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="a58e9-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="a58e9-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a58e9-125">판독기의 할당량입니다.</span><span class="sxs-lookup"><span data-stu-id="a58e9-125">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a58e9-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a58e9-126">Requirements</span></span>  
  
|<span data-ttu-id="a58e9-127">MOF</span><span class="sxs-lookup"><span data-stu-id="a58e9-127">MOF</span></span>|<span data-ttu-id="a58e9-128">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a58e9-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a58e9-129">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="a58e9-129">Namespace</span></span>|<span data-ttu-id="a58e9-130">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a58e9-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a58e9-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a58e9-131">See also</span></span>

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
