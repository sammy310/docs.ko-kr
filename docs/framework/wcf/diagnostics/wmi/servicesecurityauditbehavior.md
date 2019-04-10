---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 30679e1f67c6943bf674a6bbd8bf12be090765a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203511"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="5b02c-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="5b02c-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="5b02c-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="5b02c-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b02c-104">구문</span><span class="sxs-lookup"><span data-stu-id="5b02c-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5b02c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5b02c-105">Methods</span></span>  
 <span data-ttu-id="5b02c-106">ServiceSecurityAuditBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b02c-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5b02c-107">속성</span><span class="sxs-lookup"><span data-stu-id="5b02c-107">Properties</span></span>  
 <span data-ttu-id="5b02c-108">ServiceSecurityAuditBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b02c-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="5b02c-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="5b02c-109">AuditLogLocation</span></span>  
 <span data-ttu-id="5b02c-110">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="5b02c-110">Data type: string</span></span>  
  
 <span data-ttu-id="5b02c-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5b02c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5b02c-112">감사 로그의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="5b02c-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="5b02c-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="5b02c-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="5b02c-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="5b02c-114">Data type: string</span></span>  
  
 <span data-ttu-id="5b02c-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5b02c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5b02c-116">감사 이벤트 로깅에 사용되는 메시지 인증 수준의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5b02c-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="5b02c-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="5b02c-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="5b02c-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="5b02c-118">Data type: string</span></span>  
  
 <span data-ttu-id="5b02c-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5b02c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5b02c-120">감사 로그에 기록되는 권한 부여 이벤트의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5b02c-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="5b02c-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="5b02c-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="5b02c-122">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="5b02c-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="5b02c-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5b02c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5b02c-124">감사 로그 쓰기의 실패를 표시하지 않기 위한 동작을 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5b02c-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b02c-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b02c-125">Requirements</span></span>  
  
|<span data-ttu-id="5b02c-126">MOF</span><span class="sxs-lookup"><span data-stu-id="5b02c-126">MOF</span></span>|<span data-ttu-id="5b02c-127">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b02c-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5b02c-128">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="5b02c-128">Namespace</span></span>|<span data-ttu-id="5b02c-129">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b02c-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b02c-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="5b02c-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
