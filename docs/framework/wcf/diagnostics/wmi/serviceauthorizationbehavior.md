---
description: '자세한 정보: ServiceAuthorizationBehavior'
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: dc398621103774a04934aa23ae3d7208f4389717
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715589"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="6a083-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="6a083-103">ServiceAuthorizationBehavior</span></span>

<span data-ttu-id="6a083-104">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="6a083-104">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a083-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a083-105">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6a083-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6a083-106">Methods</span></span>  

 <span data-ttu-id="6a083-107">ServiceAuthorizationBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a083-107">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6a083-108">속성</span><span class="sxs-lookup"><span data-stu-id="6a083-108">Properties</span></span>  

 <span data-ttu-id="6a083-109">ServiceAuthorizationBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a083-109">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="6a083-110">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="6a083-110">ImpersonateCallerForAllOperations</span></span>  

 <span data-ttu-id="6a083-111">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="6a083-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="6a083-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6a083-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6a083-113">들어오는 메시지가 제공하는 자격 증명을 사용하여 서비스가 가장을 시도하는지 여부를 제어하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6a083-113">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="6a083-114">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="6a083-114">PrincipalPermissionMode</span></span>  

 <span data-ttu-id="6a083-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="6a083-115">Data type: string</span></span>  
  
 <span data-ttu-id="6a083-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6a083-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6a083-117">서버에서 작업을 수행할 때 사용되는 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="6a083-117">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="6a083-118">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="6a083-118">RoleProvider</span></span>  

 <span data-ttu-id="6a083-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="6a083-119">Data type: string</span></span>  
  
 <span data-ttu-id="6a083-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6a083-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6a083-121">ASP.NET 역할 공급자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6a083-121">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="6a083-122">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="6a083-122">ServiceAuthorizationManager</span></span>  

 <span data-ttu-id="6a083-123">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="6a083-123">Data type: string</span></span>  
  
 <span data-ttu-id="6a083-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="6a083-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6a083-125">사용자 지정 인증에 사용되는 권한 부여 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="6a083-125">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a083-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a083-126">Requirements</span></span>  
  
|<span data-ttu-id="6a083-127">MOF</span><span class="sxs-lookup"><span data-stu-id="6a083-127">MOF</span></span>|<span data-ttu-id="6a083-128">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a083-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6a083-129">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="6a083-129">Namespace</span></span>|<span data-ttu-id="6a083-130">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a083-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a083-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a083-131">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
