---
description: '자세히 알아보기: XmlDictionaryReaderQuotas'
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: d1450051e7107e9b92f848d26e6b182bfd2f2340
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756866"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="fe306-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="fe306-103">XmlDictionaryReaderQuotas</span></span>

<span data-ttu-id="fe306-104">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="fe306-104">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe306-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe306-105">Syntax</span></span>  
  
```csharp
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fe306-106">메서드</span><span class="sxs-lookup"><span data-stu-id="fe306-106">Methods</span></span>  

 <span data-ttu-id="fe306-107">XmlDictionaryReaderQuotas 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe306-107">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fe306-108">속성</span><span class="sxs-lookup"><span data-stu-id="fe306-108">Properties</span></span>  

 <span data-ttu-id="fe306-109">XmlDictionaryReaderQuotas 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe306-109">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="fe306-110">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="fe306-110">MaxArrayLength</span></span>  

 <span data-ttu-id="fe306-111">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="fe306-111">Data type: sint32</span></span>  
  
 <span data-ttu-id="fe306-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fe306-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe306-113">허용된 최대 배열 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="fe306-113">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="fe306-114">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="fe306-114">MaxBytesPerRead</span></span>  

 <span data-ttu-id="fe306-115">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="fe306-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="fe306-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fe306-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe306-117">각 읽기에 대해 반환되는 최대 허용 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="fe306-117">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="fe306-118">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="fe306-118">MaxDepth</span></span>  

 <span data-ttu-id="fe306-119">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="fe306-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="fe306-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fe306-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe306-121">각 읽기에 대한 최대 중첩 노드 깊이입니다.</span><span class="sxs-lookup"><span data-stu-id="fe306-121">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="fe306-122">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="fe306-122">MaxNameTableCharCount</span></span>  

 <span data-ttu-id="fe306-123">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="fe306-123">Data type: sint32</span></span>  
  
 <span data-ttu-id="fe306-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fe306-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe306-125">표 이름에 허용된 최대 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fe306-125">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="fe306-126">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="fe306-126">MaxStringContentLength</span></span>  

 <span data-ttu-id="fe306-127">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="fe306-127">Data type: sint32</span></span>  
  
 <span data-ttu-id="fe306-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fe306-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe306-129">XML 요소 콘텐츠에 허용되는 최대 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fe306-129">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe306-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe306-130">Requirements</span></span>  
  
|<span data-ttu-id="fe306-131">MOF</span><span class="sxs-lookup"><span data-stu-id="fe306-131">MOF</span></span>|<span data-ttu-id="fe306-132">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe306-132">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fe306-133">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="fe306-133">Namespace</span></span>|<span data-ttu-id="fe306-134">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe306-134">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe306-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe306-135">See also</span></span>

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
