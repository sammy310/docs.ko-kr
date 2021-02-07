---
description: '자세히 알아보기: ServiceSecurityAuditBehavior'
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 5dfb3a70a80d5dea1ed360dcaf3a0db989bf671b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715472"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="091af-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="091af-103">ServiceSecurityAuditBehavior</span></span>

<span data-ttu-id="091af-104">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="091af-104">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="091af-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="091af-105">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="091af-106">메서드</span><span class="sxs-lookup"><span data-stu-id="091af-106">Methods</span></span>  

 <span data-ttu-id="091af-107">ServiceSecurityAuditBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="091af-107">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="091af-108">속성</span><span class="sxs-lookup"><span data-stu-id="091af-108">Properties</span></span>  

 <span data-ttu-id="091af-109">ServiceSecurityAuditBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="091af-109">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="091af-110">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="091af-110">AuditLogLocation</span></span>  

 <span data-ttu-id="091af-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="091af-111">Data type: string</span></span>  
  
 <span data-ttu-id="091af-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="091af-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="091af-113">감사 로그의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="091af-113">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="091af-114">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="091af-114">MessageAuthenticationAuditLevel</span></span>  

 <span data-ttu-id="091af-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="091af-115">Data type: string</span></span>  
  
 <span data-ttu-id="091af-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="091af-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="091af-117">감사 이벤트 로깅에 사용되는 메시지 인증 수준의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="091af-117">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="091af-118">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="091af-118">ServiceAuthorizationAuditLevel</span></span>  

 <span data-ttu-id="091af-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="091af-119">Data type: string</span></span>  
  
 <span data-ttu-id="091af-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="091af-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="091af-121">감사 로그에 기록되는 권한 부여 이벤트의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="091af-121">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="091af-122">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="091af-122">SuppressAuditFailure</span></span>  

 <span data-ttu-id="091af-123">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="091af-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="091af-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="091af-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="091af-125">감사 로그 쓰기의 실패를 표시하지 않기 위한 동작을 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="091af-125">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="091af-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="091af-126">Requirements</span></span>  
  
|<span data-ttu-id="091af-127">MOF</span><span class="sxs-lookup"><span data-stu-id="091af-127">MOF</span></span>|<span data-ttu-id="091af-128">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="091af-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="091af-129">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="091af-129">Namespace</span></span>|<span data-ttu-id="091af-130">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="091af-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="091af-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="091af-131">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
