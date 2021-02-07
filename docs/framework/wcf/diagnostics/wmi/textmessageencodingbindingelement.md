---
description: '자세히 알아보기: TextMessageEncodingBindingElement'
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 9848f1660642f92c4bce3542fbd404f463b8c84d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757347"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="4f126-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="4f126-103">TextMessageEncodingBindingElement</span></span>

<span data-ttu-id="4f126-104">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="4f126-104">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f126-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f126-105">Syntax</span></span>  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4f126-106">메서드</span><span class="sxs-lookup"><span data-stu-id="4f126-106">Methods</span></span>  

 <span data-ttu-id="4f126-107">TextMessageEncodingBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f126-107">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4f126-108">속성</span><span class="sxs-lookup"><span data-stu-id="4f126-108">Properties</span></span>  

 <span data-ttu-id="4f126-109">TextMessageEncodingBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f126-109">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="4f126-110">Encoding</span><span class="sxs-lookup"><span data-stu-id="4f126-110">Encoding</span></span>  

 <span data-ttu-id="4f126-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="4f126-111">Data type: string</span></span>  
  
 <span data-ttu-id="4f126-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4f126-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f126-113">바인딩에서 메시지를 내보낼 때 사용되는 문자 집합 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="4f126-113">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="4f126-114">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="4f126-114">MaxReadPoolSize</span></span>  

 <span data-ttu-id="4f126-115">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="4f126-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="4f126-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4f126-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f126-117">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="4f126-117">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="4f126-118">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="4f126-118">MaxWritePoolSize</span></span>  

 <span data-ttu-id="4f126-119">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="4f126-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="4f126-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4f126-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f126-121">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="4f126-121">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="4f126-122">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="4f126-122">ReaderQuotas</span></span>  

 <span data-ttu-id="4f126-123">데이터 형식: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="4f126-123">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="4f126-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4f126-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f126-125">판독기의 할당량입니다.</span><span class="sxs-lookup"><span data-stu-id="4f126-125">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f126-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f126-126">Requirements</span></span>  
  
|<span data-ttu-id="4f126-127">MOF</span><span class="sxs-lookup"><span data-stu-id="4f126-127">MOF</span></span>|<span data-ttu-id="4f126-128">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f126-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4f126-129">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="4f126-129">Namespace</span></span>|<span data-ttu-id="4f126-130">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f126-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f126-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f126-131">See also</span></span>

- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
