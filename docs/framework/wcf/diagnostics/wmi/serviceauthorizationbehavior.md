---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: d3625865484568746888ef0638d9a8501e610bef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273206"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="438f1-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="438f1-102">ServiceAuthorizationBehavior</span></span>

<span data-ttu-id="438f1-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="438f1-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="438f1-104">구문</span><span class="sxs-lookup"><span data-stu-id="438f1-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="438f1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="438f1-105">Methods</span></span>  

 <span data-ttu-id="438f1-106">ServiceAuthorizationBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="438f1-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="438f1-107">속성</span><span class="sxs-lookup"><span data-stu-id="438f1-107">Properties</span></span>  

 <span data-ttu-id="438f1-108">ServiceAuthorizationBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="438f1-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="438f1-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="438f1-109">ImpersonateCallerForAllOperations</span></span>  

 <span data-ttu-id="438f1-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="438f1-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="438f1-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="438f1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="438f1-112">들어오는 메시지가 제공하는 자격 증명을 사용하여 서비스가 가장을 시도하는지 여부를 제어하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="438f1-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="438f1-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="438f1-113">PrincipalPermissionMode</span></span>  

 <span data-ttu-id="438f1-114">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="438f1-114">Data type: string</span></span>  
  
 <span data-ttu-id="438f1-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="438f1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="438f1-116">서버에서 작업을 수행할 때 사용되는 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="438f1-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="438f1-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="438f1-117">RoleProvider</span></span>  

 <span data-ttu-id="438f1-118">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="438f1-118">Data type: string</span></span>  
  
 <span data-ttu-id="438f1-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="438f1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="438f1-120">ASP.NET 역할 공급자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="438f1-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="438f1-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="438f1-121">ServiceAuthorizationManager</span></span>  

 <span data-ttu-id="438f1-122">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="438f1-122">Data type: string</span></span>  
  
 <span data-ttu-id="438f1-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="438f1-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="438f1-124">사용자 지정 인증에 사용되는 권한 부여 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="438f1-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="438f1-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="438f1-125">Requirements</span></span>  
  
|<span data-ttu-id="438f1-126">MOF</span><span class="sxs-lookup"><span data-stu-id="438f1-126">MOF</span></span>|<span data-ttu-id="438f1-127">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="438f1-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="438f1-128">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="438f1-128">Namespace</span></span>|<span data-ttu-id="438f1-129">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="438f1-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="438f1-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="438f1-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
