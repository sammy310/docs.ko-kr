---
description: '자세히 알아보기: ServiceMetadataBehavior'
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 1b1438013ec667b10b300d898687abf6f33f96fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715485"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="ad36c-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="ad36c-103">ServiceMetadataBehavior</span></span>

<span data-ttu-id="ad36c-104">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="ad36c-104">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad36c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad36c-105">Syntax</span></span>  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ad36c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ad36c-106">Methods</span></span>  

 <span data-ttu-id="ad36c-107">ServiceMetadataBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad36c-107">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ad36c-108">속성</span><span class="sxs-lookup"><span data-stu-id="ad36c-108">Properties</span></span>  

 <span data-ttu-id="ad36c-109">ServiceMetadataBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad36c-109">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="ad36c-110">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="ad36c-110">ExternalMetadataLocation</span></span>  

 <span data-ttu-id="ad36c-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="ad36c-111">Data type: string</span></span>  
  
 <span data-ttu-id="ad36c-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ad36c-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad36c-113">서비스가 메타데이터 요청을 리디렉션하는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad36c-113">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="ad36c-114">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="ad36c-114">HttpGetEnabled</span></span>  

 <span data-ttu-id="ad36c-115">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="ad36c-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="ad36c-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ad36c-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad36c-117">`HttpGetUrl` 특성으로 제어되는 주소에서 서비스가 WSDL을 게시할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ad36c-117">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="ad36c-118">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="ad36c-118">HttpGetUrl</span></span>  

 <span data-ttu-id="ad36c-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="ad36c-119">Data type: string</span></span>  
  
 <span data-ttu-id="ad36c-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ad36c-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad36c-121">HTTP를 사용한 검색을 위해 서비스 WSDL이 게시되는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad36c-121">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="ad36c-122">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="ad36c-122">HttpsGetEnabled</span></span>  

 <span data-ttu-id="ad36c-123">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="ad36c-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="ad36c-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ad36c-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad36c-125">`HttpsGetUrl` 특성으로 제어되는 주소에서 서비스가 HTTPS를 통해 WSDL을 게시할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ad36c-125">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="ad36c-126">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="ad36c-126">HttpsGetUrl</span></span>  

 <span data-ttu-id="ad36c-127">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="ad36c-127">Data type: string</span></span>  
  
 <span data-ttu-id="ad36c-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ad36c-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad36c-129">HTTPS를 사용한 검색을 위해 서비스 WSDL이 게시되는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad36c-129">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad36c-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad36c-130">Requirements</span></span>  
  
|<span data-ttu-id="ad36c-131">MOF</span><span class="sxs-lookup"><span data-stu-id="ad36c-131">MOF</span></span>|<span data-ttu-id="ad36c-132">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad36c-132">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ad36c-133">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="ad36c-133">Namespace</span></span>|<span data-ttu-id="ad36c-134">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad36c-134">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad36c-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad36c-135">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
