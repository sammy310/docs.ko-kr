---
description: '자세히 알아보기: ServiceDebugBehavior'
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 3b384c209524267c72a12d96bc845b694144ba19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715537"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="f9f98-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="f9f98-103">ServiceDebugBehavior</span></span>

<span data-ttu-id="f9f98-104">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="f9f98-104">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9f98-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9f98-105">Syntax</span></span>  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f9f98-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f9f98-106">Methods</span></span>  

 <span data-ttu-id="f9f98-107">ServiceDebugBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9f98-107">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f9f98-108">속성</span><span class="sxs-lookup"><span data-stu-id="f9f98-108">Properties</span></span>  

 <span data-ttu-id="f9f98-109">ServiceDebugBehavior 클래스에는 다음 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9f98-109">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="f9f98-110">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="f9f98-110">HttpHelpPageEnabled</span></span>  

 <span data-ttu-id="f9f98-111">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="f9f98-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="f9f98-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="f9f98-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f9f98-113">`HttpGetUrl` 특성으로 제어되는 주소에서 서비스가 WSDL을 게시할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f9f98-113">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="f9f98-114">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="f9f98-114">HttpHelpPageUrl</span></span>  

 <span data-ttu-id="f9f98-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="f9f98-115">Data type: string</span></span>  
  
 <span data-ttu-id="f9f98-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="f9f98-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f9f98-117">HTTP를 사용한 검색을 위해 서비스 WSDL이 게시되는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9f98-117">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="f9f98-118">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="f9f98-118">HttpsHelpPageEnabled</span></span>  

 <span data-ttu-id="f9f98-119">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="f9f98-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="f9f98-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="f9f98-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f9f98-121">`HttpsGetUrl` 특성으로 제어되는 주소에서 서비스가 HTTPS를 통해 WSDL을 게시할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f9f98-121">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="f9f98-122">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="f9f98-122">HttpsHelpPageUrl</span></span>  

 <span data-ttu-id="f9f98-123">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="f9f98-123">Data type: string</span></span>  
  
 <span data-ttu-id="f9f98-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="f9f98-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f9f98-125">HTTPS를 사용한 검색을 위해 서비스 WSDL이 게시되는 위치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9f98-125">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="f9f98-126">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="f9f98-126">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="f9f98-127">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="f9f98-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="f9f98-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="f9f98-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f9f98-129">디버깅 목적으로 클라이언트에 반환되는 SOAP 오류 정보에 관리되는 예외 정보를 포함할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9f98-129">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9f98-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9f98-130">Requirements</span></span>  
  
|<span data-ttu-id="f9f98-131">MOF</span><span class="sxs-lookup"><span data-stu-id="f9f98-131">MOF</span></span>|<span data-ttu-id="f9f98-132">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9f98-132">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f9f98-133">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="f9f98-133">Namespace</span></span>|<span data-ttu-id="f9f98-134">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9f98-134">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9f98-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9f98-135">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
